# SendPush REST API
La API REST le permite interactuar con SendPush para cualquier cosa que pueda enviar una solicitud HTTP.
Por ejemplo:

* Enviar notificaciones a todos los ususarios de una aplicación
* Muy pronto muchas cosas más.

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

## Enviando notificaciones

### PHP
```php
curl_setopt_array($ch = curl_init(), array(
  CURLOPT_URL => "http://notify.mobytesac.com/api/v1/send_menssage/",
  CURLOPT_POSTFIELDS => array(
    "token_user" => "my_token_user",
    "token_app" => "my_token_app",
    "title" => "my_title",
    "message" => "hello world",
  ),
  CURLOPT_SAFE_UPLOAD => true,
));
curl_exec($ch);
curl_close($ch);
```

### Python
```py
#!/usr/bin/python 
import json,httplib 
connection = httplib.HTTPSConnection('http://notify.mobytesac.com', 443) 
connection.connect() 
connection.request('POST', '/api/v1/send_menssage/', json.dumps({ "token_user": "my_token_user", "token_app": "my_token_app", "title": "my_title", "message": "Your notification content."}), { "Content-Type": "application/json" } ) result = json.loads(connection.getresponse().read())
print result
```

### Ruby

```ruby
require "net/https"

url = URI.parse("https://api.pushover.net/1/messages.json")
req = Net::HTTP::Post.new(url.path)
req.set_form_data({
  :token => "abc123",
  :user => "user123",
  :message => "hello world",
})
res = Net::HTTP.new(url.host, url.port)
res.use_ssl = true
res.verify_mode = OpenSSL::SSL::VERIFY_PEER
res.start {|http| http.request(req) }
```
