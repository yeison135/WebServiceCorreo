/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package co.gov.aressoluciones.servicio;

import co.gov.aressoluciones.dto.MensajeDto;
import co.gov.aressoluciones.dto.PropiedadesServerDto;
import java.util.Properties;

import javax.activation.DataHandler;
import javax.activation.DataSource;
import javax.activation.FileDataSource;
import javax.mail.BodyPart;
import javax.mail.Message;
import javax.mail.MessagingException;
import javax.mail.Multipart;
import javax.mail.PasswordAuthentication;
import javax.mail.Session;
import javax.mail.Transport;
import javax.mail.internet.InternetAddress;
import javax.mail.internet.MimeBodyPart;
import javax.mail.internet.MimeMessage;
import javax.mail.internet.MimeMultipart;

/**
 *
 * @author CESAR CASANOVA
 * @email CCASANOVA@ARESSOLUCIONES.COM
 * @Company Ares Soluciones
 * @site www.aressoluciones.com
 *
 */
public class Email {

     public String EnviarMensaje(MensajeDto objMensajeDto,PropiedadesServerDto objPropiedadesServerDto) {
      // Recipient's email ID needs to be mentioned.
      String to = objMensajeDto.getA();

      // Sender's email ID needs to be mentioned
      String from = objMensajeDto.getDe();

      final String username = objPropiedadesServerDto.getUsuario();//change accordingly
      final String password = objPropiedadesServerDto.getContrasena();//change accordingly

      // Assuming you are sending email through relay.jangosmtp.net
      String host = objPropiedadesServerDto.getHost();

      Properties props = new Properties();
      props.put("mail.smtp.auth", "true");
      props.put("mail.smtp.starttls.enable", "true");
      props.put("mail.smtp.host", host);
      props.put("mail.smtp.port", objPropiedadesServerDto.getPuerto());
      props.put("mail.smtp.ssl.trust", host);

      // Get the Session object.
      Session session = Session.getInstance(props,
         new javax.mail.Authenticator() {
            protected PasswordAuthentication getPasswordAuthentication() {
               return new PasswordAuthentication(username, password);
            }
         });

      try {
         // Create a default MimeMessage object.
         Message message = new MimeMessage(session);
         // Set From: header field of the header.
         message.setFrom(new InternetAddress(from));
         // Set To: header field of the header.
         message.setRecipients(Message.RecipientType.TO,InternetAddress.parse(to));
         // Set Subject: header field
         message.setSubject(objMensajeDto.getAsunto());
         // Create the message part
         BodyPart messageBodyPart = new MimeBodyPart();
         // Now set the actual message
         messageBodyPart.setContent(objMensajeDto.getMensaje(),"text/html; charset=utf-8");
         // Create a multipar message
         Multipart multipart = new MimeMultipart();
         // Set text message part
         multipart.addBodyPart(messageBodyPart);
         // Part two is attachment
         /*messageBodyPart = new MimeBodyPart();
         String filename = "/home/manisha/file.txt";
         DataSource source = new FileDataSource(filename);
         messageBodyPart.setDataHandler(new DataHandler(source));
         messageBodyPart.setFileName(filename);
         multipart.addBodyPart(messageBodyPart);*/
         // Send the complete message parts
         message.setContent(multipart);
         // Send message
         Transport.send(message);
         return ("Mensaje enviado correctamente....");
      } catch (MessagingException e) {
         return ("Error enviado mensaje,"+e.getMessage() );
      }
   }
}
