# mail  
发送邮件，参考phpmailer/phpmailer  
#使用方法  
use Zzx\mail\PHPMailer;  
use Zzx\mail\Exception;  
引入vendor类  
实例化 $mail = new PHPMailer(true);  
```
	try {  
    		$mail->CharSet  = 'UTF-8'; //设定邮件编码，默认ISO-8859-1，如果发中文此项必须设置，否则乱码  
            //Server settings
            //Enable SMTP debugging
            // 0 = off (for production use)
            // 1 = client messages
            // 2 = client and server messages
            $mail->SMTPDebug = 0;                                
            $mail->isSMTP();                                      
            $mail->Host = 'smtp.163.com，stmo服务器';                           
            $mail->SMTPAuth = true;                              
            $mail->Username = '13302516724@163.com，登录邮箱的账号';              
            $mail->Password = '邮箱授权密码，与登录账号的密码不一样';                           
            $mail->SMTPSecure = 'ssl，使用安全协议';                           
            $mail->Port = 465;                                 

            //发送者  
            $mail->setFrom('13302516724@163.com', 'Mailer');  
            //接收者  
            $mail->addAddress('1064059707@qq.com', 'Joe User');    
            $mail->addAddress('1064059707@qq.com');               
            //接收者回复的邮箱  
            $mail->addReplyTo('info@example.com', 'Information');  
            //抄送邮箱  
            $mail->addCC('cc@example.com');  
            $mail->addBCC('bcc@example.com');  

            //发送文件  
//            $mail->addAttachment('/var/tmp/file.tar.gz');         
//            $mail->addAttachment('/tmp/image.jpg', 'new.jpg'); 

            //内容  
            $mail->isHTML(true);             
            $mail->Subject = '测试主题';  
            $mail->Body    = '会乱码吗，<b>会乱码吗</b>';  
            //$mail->AltBody = 'This is the body in plain text for non-HTML mail clients';  
            $mail->send();  
            echo 'Message has been sent';  
        } catch (Exception $e) {  
            echo 'Message could not be sent. Mailer Error: ', $mail->ErrorInfo;  
        }  

```

