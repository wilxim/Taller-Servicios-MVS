# 1. Justificaciones

Se plantea una solución basada en orquestacion de servicios permitiendo ser independiente de las tecnologías de cada proveedor  facilitando la inclusión de nuevos proveedores.
Una de los patrones aplicados en esta solución   es Capability composicion ya que proporcionara las capacidades de reutilización de lógica de diferentes servicios. Para mantener la centralizacion de un contrato que permita ingresar y eliminar nuevos convenios se baso el desarrollo implementando el patrón policy Centralization en donde basados en un contrato común para los diferentes proveedores de servicios. Para apoyar la orientación a servicios se aplicación los principios de diseño de la siguiente manera.

Contratos estandarizados: desacoplar la tecnología de los proveedores y definiendo las políticas de desarrollo de nuevos servicios potencializando la composición.


Se hace uso del  patrón de diseño utility abstraction y process abstraction el primero para definir una capa de utilidades para el servicios de autenticacion y para los servicios notificaciones, el segundo para la abstraccion de procesos de los servicios de pago.
Interoperabilidad, mediante la composición de servicios promueve la interoperabilidad



# 2.Artefactos

dispatcher: Encargado de la comunicación con los sistemas externos. Realiza transformaciones
WSDispatcherABC


Validacion del usuario hasta la notificacion del usuario.
      Se consumira los web service expuestos por SAP.

Notificacion
   Se utilizara el AS-400


Orquestador:
       Componente del control de proceso que determina que servicio se consume.
       Desde la composicion
WSOrquestadorABC


Enrutador:
     Con base en el proceso indica direcciona al  servicio lo va atender.

WSEnrutadorABC




CONTRATO

	 		   {
                            "typeService": "SOAP",
                            "soapService": {
                                    "wsdl": "http://localhost:8080/w1-soap-svr/ServicioPagos?wsdl",
                                    "functionToCall": "Cosultar",
                                    "args": {"}
                            },
                            "restService":{
                                "method": "GET",
                                "urlBase": "http://localhost:8080/servicios/pagos/v1/payments",
                                "urlParts": [],
                                "postBodyArgs": {}
                            }


WS PAGOS
WSPagoServicioABC
