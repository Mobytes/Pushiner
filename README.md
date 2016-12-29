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

Nombre de parámetro | Tipo | Obligatorio | Descripcion
------------ | ------------- | ------------ | ----------
token_user | String | Si | Su clave de usuario. Puede encontrar su ``token_user`` en la sección de configuración de su aplicación                             dentro del portal de desarrolladores.
token_app | String | Si | Su clave de aplicación. Puede encontrar su ``token_user`` en la sección de configuración de su     aplicación dentro del portal de desarrolladores.
title | String | Si | El título de la notificación.
message | String | Si | El contenido de la notificación. Es el detalle de la notificación.

