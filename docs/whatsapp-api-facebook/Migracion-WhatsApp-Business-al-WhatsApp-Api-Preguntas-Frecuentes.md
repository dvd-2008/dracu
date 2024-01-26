# Migración WhatsApp Business al WhatsApp Api : Preguntas Frecuentes

La API de WhatsApp Business es una solución para las empresas que quieren tener acceso a la plataforma para varios usuarios y mejorar las capacidades de mensajería.

WhatsApp Business API es solo una API. No tiene una interfaz, por lo que debe conectarse a una plataforma de mensajería empresarial como **[Chat Búho](https://buho.la/chat)**, para utilizar las funciones de WhatsApp Cloud API.

## ¿Que requisitos necesito cumplir para comenzar a usar WhatsApp Api?
El número de teléfono de tu empresa debe ser un número de teléfono válido que cumpla con los siguientes criterios:

* Ser de tu propiedad.
* Cumplir con las políticas de negocio de WhatsApp. **[Leer artículo](/docs/whatsapp-api-facebook/Productos-o-servicios-ilegales-que-no-aplican-para-WhatsApp-API.md)**
* Incluir un código de país y un código de área como el que tienen los números de teléfono de línea y de celular **(Ejem. +51926798150)**.
* Poder recibir llamadas de voz o SMS.
* No se debe haber usado anteriormente en la Plataforma de WhatsApp Business,esto quiere decir que no debe tener cuenta vinculada o la aplicación instalada.

## ¿Si el número que deseo implementar en la integración ya esta siendo usado en la app de WhatsApp Business, que debo hacer?

Es importante conocer que Facebook - Meta, solicita como requisito que el número que se usará para la implementación de  WhatsApp Business API, no debe tener cuenta con otra app relacionada a WhatsApp.

Para **[eliminar la cuenta](https://faq.whatsapp.com/2138577903196467/?cms_platform=android&helpref=platform_switcher)** y dejarlo liberado, puedes seguir estos pasos:

* Abre WhatsApp.
* Toca el ícono de más opciones **(3 puntos verticales)  > Ajustes > Cuenta > Eliminar mi cuenta.**
* Ingresa tu número de teléfono en **[formato internacional completo](https://faq.whatsapp.com/640432094208718?helpref=faq_content)** para confirmar acción y toca **ELIMINAR MI CUENTA**.
* En el menú desplegable, selecciona el motivo por el que quieres eliminar tu cuenta.
* Toca **ELIMINAR MI CUENTA**.

## ¿Qué pasará cuando migre mi número de WhatsApp Business a WhatsApp Api?
Al migrar, ocurrirá lo siguiente:
* Se eliminará tu cuenta de WhatsApp.
* Se eliminará tu historial de mensajes.
* Se te eliminará de todos tus grupos de WhatsApp.
* Se eliminará la copia de seguridad de Google Drive

:::info RECUERDA:
La integración será desde 0, por requisito de Facebook,asimismo una vez creada la cuenta WhatsApp API no será posible invertir el proceso y volver a utilizar el mismo número en una cuenta de WhatsApp instalada en un celular.  **[Más información](/docs/whatsapp-api-facebook/Migracion-WhatsApp-Business-al-WhatsApp-Api-Preguntas-Frecuentes.md)**
:::

## ¿Que opciones tengo para mantener el historial de mis chats?
Podemos sugerirle 2 opciones:

1. **Capturar pantalla a los chats más importantes.**
2. **Cambiar de número en el mismo dispositivo:**
   
Si deseas cambiar el número de teléfono y usar el mismo dispositivo, primero debes insertar la nueva tarjeta SIM con el nuevo número en el dispositivo. De esta manera podrás mantener tu historial de conversaciones. Sigue estos pasos:

* Abre **WhatsApp.**
* Toca el ícono de **más opciones > Ajustes > Cuenta > Cambiar número > SIGUIENTE.**
* Ingresa el número de teléfono antiguo en el primer campo y el nuevo en el segundo, **[ambos en el formato internacional completo.](https://faq.whatsapp.com/1294841057948784?helpref=faq_content)**
* Toca **SIGUIENTE.**
    *Si activas **Notificar contactos**, puedes elegir si quieres notificar a **Todos los contactos**, **Contactos con los que tengo un chat o Personalizar...** Si seleccionas **Personalizar...**, deberás buscar o seleccionar los contactos a los que quieres notificar, luego, toca el ícono de **tic (✔️)** 
* Tus grupos serán notificados cuando cambies el número de teléfono, independientemente de si activas o no la opción para notificar a los contactos.
* Toca **OK.**
* Luego, se te indicará que registres el nuevo número de teléfono. Obtén más información en este **[artículo](https://faq.whatsapp.com/684051319521343?cms_platform=android&helpref=faq_content).**

:::info RECUERDA:
Que el chip que se usará para la integración con WhatsApp API Cloud, deberás colocarlo en otro dispositivo móvil, asimismo podrás recibir llamadas u otros códigos importantes para el proceso de integración.

:::