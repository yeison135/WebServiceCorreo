CREATE TABLE SMB_PARAMETRO_CORREO (	
	"ASUNTO" VARCHAR2(200 BYTE), 
	"CORREO_DE" VARCHAR2(200 BYTE) NOT NULL ENABLE, 
	"MENSAJE" VARCHAR2(900 BYTE), 
	"CONTRASENA" VARCHAR2(20 BYTE), 
	"USUARIO" VARCHAR2(200 BYTE), 
	"HOST" VARCHAR2(100 BYTE), 
	"PUERTO" VARCHAR2(5 BYTE), 
	"REMITENTE" VARCHAR2(20 BYTE), 
	"AUTENTICACION" VARCHAR2(10 BYTE), 
	"TLS" VARCHAR2(10 BYTE), 
	"ID_CORREO" NUMBER, 
	"DESCRIPCION" VARCHAR2(200 BYTE)
   );

INSERT INTO smb_parametro_correo (
    asunto, correo_de, mensaje, 
    contrasena, usuario, host, puerto, 
    remitente, autenticacion, tls, 
    id_correo, descripcion
) 
VALUES (
    'SMD - Notificacion de 30 Accesos Registrados', 'tpicontrolyvigilancia@movilidadbogota.gov.co', 'El usuario ha completado 30 accesos durante el año',
    'alejandra2017', 'tpicontrolyvigilancia@movilidadbogota.gov.co', 'smtp.gmail.com', '25',
    'SDM', 'true', 'true',
    1, 'Notificacion 30 Accesos Registrados'
);

INSERT INTO smb_parametro_correo (
    asunto, correo_de, mensaje, 
    contrasena, usuario, host, puerto, 
    remitente, autenticacion, tls, 
    id_correo, descripcion
) 
VALUES (
    'SMD - Notificacion de 240 Accesos Registrados', 'tpicontrolyvigilancia@movilidadbogota.gov.co', 'El usuario ha completado 240 accesos durante el año',
    'alejandra2017', 'tpicontrolyvigilancia@movilidadbogota.gov.co', 'smtp.gmail.com', '25',
    'SDM', 'true', 'true',
    2, 'Notificacion 240 Accesos Registrados'
);

COMMIT;
 

create or replace PROCEDURE SMSP_CONSULTA_PARAMETRO_CORREO (
	P_ID_CORREO INT, 
	datos_salida out sys_refcursor
)
IS
-------------------------------------------------------------------------------------------------
-- DESCRIPCION: Este procedimiento consulta los PARAMETROS DEL ENVIO DE CORREO.
-- para armar el campo dirección
-- PARAMETROS:
-- MODIFICACIONES:
-- ANDRÉS MORALES
-- FECHA CREACION: 15/08/2017
-- FINALIDAD DE LA MODIFICACION
--------------------------------------------------------------------------------------------------
BEGIN
	open datos_salida for
	SELECT ASUNTO,
	  CORREO_DE,
	  MENSAJE,
	  CONTRASENA,
	  USUARIO,
	  HOST,
	  PUERTO,
	  REMITENTE,
	  AUTENTICACION,
	  TLS,
	  ID_CORREO,
	  DESCRIPCION
	FROM SMB_PARAMETRO_CORREO
	WHERE ID_CORREO = P_ID_CORREO;
END;