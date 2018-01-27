/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package co.gov.aressoluciones.servicio;

import co.gov.aressoluciones.dto.AutenticacionDto;
import co.gov.aressoluciones.dto.MensajeDto;
import co.gov.aressoluciones.dto.PropiedadesServerDto;
import java.util.Date;
import javax.jws.WebService;
import javax.jws.WebMethod;
import javax.jws.WebParam;

/**
 *
 * @author CESAR CASANOVA  
 * @email CCASANOVA@ARESSOLUCIONES.COM
 * @Company Ares Soluciones 
 * @site www.aressoluciones.com
 * 
 */
@WebService(serviceName = "ServiceEnvioEmail")
public class ServiceEnvioEmail {

    /**
     * This is a sample web service operation
     */
    @WebMethod(operationName = "TestHora")
    public Date TestHora() {
        
        Date FechaHora = new  Date();        
        return FechaHora;
    }
    
    @WebMethod(operationName = "EnvioEmail")
     public String EnvioEmail(MensajeDto objMensajeDto,PropiedadesServerDto objPropiedadesServerDto) {
        Email objEmail = new Email();
        return objEmail.EnviarMensaje(objMensajeDto,objPropiedadesServerDto);        
    }
    
}
