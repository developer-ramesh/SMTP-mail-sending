# SMTP-mail-sending
Sending mail via SMTP in PHP




require("PHPMailerAutoload.php"); // path to the PHPMailerAutoload.php file.
 
   $mail = new PHPMailer();
   
   $mail->IsSMTP();
   
   $mail->Mailer = "smtp";
   
   $mail->Host = "smtp.gmail.com";
   
   $mail->Port = "587"; // 8025, 587 and 25 can also be used. Use Port 465 for SSL.
   
   $mail->SMTPAuth = true;
   
   $mail->SMTPSecure = 'tls';
   
   $mail->Username = "developer.rameshraj@gmail.com";
   
   $mail->Password = "XXXXXXX";
    
   $mail->From     = "no-reply@demo.com";
   
   $mail->FromName = "Fake Corp";
   
   $mail->AddAddress("ramesh@gmail.com", "Ramesh");
   
   //$mail->AddReplyTo("Your Reply-to Address", "Sender's Name");
 
   $mail->Subject  = "Hi!";
   
   $mail->Body     = "Hi! How are you? <b>ppp</b>";
   
   $mail->WordWrap = 50;
   
   $mail->AddAttachment("/demo1/picture-6.jpg");         // add attachments
   
   $mail->AddAttachment("image.jpg", "new.jpg");    // optional name
   
   $mail->IsHTML(true);    
 
   if(!$mail->Send())
   {
   	echo 'Message was not sent.';
	echo 'Mailer error: ' . $mail->ErrorInfo;
	exit;
   } 
   else
   {
	 echo 'Message has been sent.';
   }
