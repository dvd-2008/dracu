# WhatsApp API ejemplo
Código ejemplo de Envío de Mensaje de WhatsApp a través de la API de Facebook.

Este código en PHP está diseñado para enviar un mensaje de WhatsApp a través de la API de Facebook. Permite configurar los datos del mensaje y los detalles de autenticación de la API para su uso en un entorno de producción.

Las variables necesarias estan agrupadas en 3 secciones:
1. Datos de la plantilla
2. Datos del mensaje
3. Datos del API de WhatsApp

### 1. Configuración de los datos de la plantilla 

- ``$template_name``: Nombre del plantilla de WhatsApp que se utilizará.
- ``$template_language_code``: Código del idioma para la plantilla (por ejemplo, "es" para español).

Para más detalles puede revisar nuestro artículo de como crear plantillas para WhatsApp API:
https://chatbuho.github.io/documentacion/mas-articulos/Plantillas-para-mensajes-masivos#5-crear-plantilla


### 2. Configuración de los datos del mensaje

- ``$whatsapp_to`` Número de teléfono del destinatario del mensaje de WhatsApp.
- ``$whatsapp_text`` Contenido del mensaje de WhatsApp.


### 3. Configuración de los datos del API de WhatsApp

- ``$ID_NUMBER`` Identificador de número de teléfono.
- ``$ID_WABA`` Identificador de la cuenta de WhatsApp Business.
- ``$TOKEN_API`` Token de autenticación de la API de Facebook, que debe mantenerse en secreto.


Para más detalles puede revisar nuestro artículo de como obtener los datos del API WhatsApp:
https://chatbuho.github.io/documentacion/herramientas-adicionales/Mensajes-masivos


Código de ejemplo:

```php
# Ejemplo en PHP

#1 Datos de la plantilla WhatsApp
$template_name = "bienvenida_hola";
$template_language_code = "es";

#2 Datos del mensaje
$whatsapp_to = 51999332222;
$whatsapp_text = "Mensaje de prueba";

#3 Datos del API de WhatsApp
$ID_NUMBER = XXXXXXXXXXXXX;
$ID_WABA = XXXXXXXXXXXXXX;
$TOKEN_API = 'TOKEN_API_XXXXXXXXXXXXXXXXXXXXXXXXXX';

$datos = [
    "messaging_product" => "whatsapp",
    "preview_url" => false,
    "recipient_type" => "individual",
    "to" => $whatsapp_to,
    "type" => "template",
            "template" => [
                "name" => $template_name,
                "language" => [
                    "code" => $template_language_code,
                    "policy" => "deterministic"
                ],
                "components" => [
                    [
                        "type" => "body",
                        "parameters" => [
                            [
                                "type" => "text",
                                "text" => $whatsapp_text
                            ]
                        ]
                    ]
                ]
            ]
];

$curl = curl_init();

curl_setopt_array($curl, array(
    CURLOPT_URL => 'https://graph.facebook.com/v16.0/'.$ID_NUMBER.'/messages',
    CURLOPT_RETURNTRANSFER => true,
    CURLOPT_ENCODING => '',
    CURLOPT_MAXREDIRS => 10,
    CURLOPT_TIMEOUT => 0,
    CURLOPT_FOLLOWLOCATION => true,
    CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
    CURLOPT_CUSTOMREQUEST => 'POST',
    CURLOPT_POSTFIELDS => json_encode($datos),
    CURLOPT_HTTPHEADER => array(
        'Authorization: Bearer '.$TOKEN_API,
        'WABA-ID: '.$ID_WABA,
        'Content-Type: application/json'
    ),
));

$response = curl_exec($curl);

curl_close($curl);

echo $response;
```


Si todo se configuró corectamente usted obtendrá una respuesta JSON similar al siguiente código:

```json
{
 messaging_product: "whatsapp",
 contacts: [
  {
   input: "51999332222",
   wa_id: "51999332222"
  }
 ],
 messages: [
  {
   id: "wamid.HBgLNTE5NjIzMzI4MjIVAgARGBI0NkQzRDY0N0FGNTUyNTVEQzMA",
   message_status: "accepted"
  }
 ]
}
```

:::note NOTA

Actualmente el ejemplo es solo para plantillas de texto, sin embargo puede seguir los mismos lineamientos para cualquier tipo de plantilla que contengan imagen, documentos, botones. etc. 

Para integraciones completas puede solicitar una reunión con nuestro equipo de soporte para evaluar su requerimiento.

:::