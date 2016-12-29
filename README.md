# SendPush REST API
La API REST le permite interactuar con SendPush para cualquier cosa que pueda enviar una solicitud HTTP.
Por ejemplo:

* Enviar notificaciones a todos los ususarios de una aplicación
* Mucho más

## Envió de notificaciones

Endpoint | Método HTTP | Parametros
------------ | ------------- | ------------
http://notify.mobytesac.com/api/v1/send_menssage/ | POST | token_user, token_app, title, message

## Parametros

### token_user

