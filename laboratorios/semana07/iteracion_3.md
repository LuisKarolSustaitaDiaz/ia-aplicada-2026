# Iteración 3 - Rol + contexto + formato

Modelo: [nombre y versión]
Fecha: [fecha]

## Prompt usado

(Se reemplazó [ENTRADA] por cada una de las tres entradas, en una conversación nueva cada vez.)

```
Eres analista de seguridad de primer nivel en un centro de operaciones. Tu lector es un técnico que atenderá el incidente y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan usuarios sin conocimientos técnicos. Los tipos de incidente posibles son: acceso no autorizado, phishing, malware, pérdida de dispositivo, otro. Las severidades posibles son: baja, media, alta.

Responde únicamente con esta tabla en Markdown, sin texto adicional:

| Campo | Valor |
|---|---|
| Tipo de incidente | |
| Severidad | |
| Activo afectado | |
| Primera acción recomendada | |
| Información faltante | |

Si un campo no puede determinarse a partir del texto, escribe "NO ESPECIFICADO" en Valor y explica qué falta en la fila "Información faltante".

Clasifica este reporte de incidente:

[ENTRADA]
```

---

## Entrada 1

```
"Buenas tardes. Hoy a las 9:15 am recibí un correo que parecía ser de
Recursos Humanos, pidiendo que actualizara mis datos de nómina en un enlace.
Hice clic y escribí mi usuario y contraseña del correo institucional.
Después me di cuenta de que el remitente era una dirección rara, no la de la
empresa. Estaba usando mi laptop de trabajo, conectada al wifi de la oficina.
Todavía no he cambiado mi contraseña."
```

## Respuesta a Entrada 1

| Campo | Valor |
|---|---|
| Tipo de incidente | Phishing |
| Severidad | Alta |
| Activo afectado | Cuenta de correo institucional y laptop de trabajo. Se ingresaron credenciales en un enlace sospechoso; no se confirma infección del equipo. |
| Primera acción recomendada | Cambiar inmediatamente la contraseña del correo institucional desde un dispositivo confiable y notificar al equipo de seguridad para que revoque las sesiones activas, revise accesos sospechosos y evalúe la cuenta. |
| Información faltante | NO ESPECIFICADO: URL del enlace, dirección exacta del remitente, si la cuenta tiene autenticación multifactor, si hubo accesos no autorizados posteriores, si se reutiliza la contraseña en otros servicios y si la laptop presenta indicios de infección. |

---

## Entrada 2

```
"Hola, creo que alguien entró a mi correo porque me llegó un aviso raro.
No sé desde cuándo está pasando esto. Ya cambié la contraseña, pero me da
miedo que hayan visto mis mensajes. No recuerdo si abrí algún enlace
sospechoso estos días. Uso el correo desde mi celular y a veces desde otra
computadora. ¿Qué hago?"
```

## Respuesta a Entrada 2

| Campo | Valor |
|---|---|
| Tipo de incidente | Acceso no autorizado |
| Severidad | Media |
| Activo afectado | Cuenta de correo electrónico; acceso desde celular y otra computadora. |
| Primera acción recomendada | Verificar los inicios de sesión recientes, cerrar todas las sesiones activas, activar la autenticación multifactor (MFA) y revisar los métodos de recuperación de la cuenta. La contraseña ya fue cambiada. |
| Información faltante | NO ESPECIFICADO: fecha y hora del aviso, remitente o contenido del aviso, inicios de sesión desconocidos, posible exposición de mensajes, servicios vinculados a la cuenta y confirmación de si se abrió algún enlace sospechoso. |

---

## Entrada 3

```
"Mi laptop se perdió ayer, bueno, creo que me la robaron en el camión,
aunque igual la dejé en la oficina y ya no estaba. Tenía todos mis archivos
del proyecto, pero la verdad no sé si eran importantes o solo copias. Dicen
que está cifrada, otros dicen que no. Hoy me llegó un mensaje pidiendo dinero
para devolverla, aunque no sé si es en serio o es broma de un compañero."
```

## Respuesta a Entrada 3

| Campo | Valor |
|---|---|
| Tipo de incidente | pérdida de dispositivo |
| Severidad | alta |
| Activo afectado | Laptop con archivos del proyecto; estado del cifrado no confirmado. |
| Primera acción recomendada | Reportar inmediatamente la pérdida al equipo de seguridad, solicitar el bloqueo o borrado remoto del equipo si es posible y verificar el cifrado. |
| Información faltante | Ubicación y última conexión conocidas de la laptop; confirmación de robo o pérdida accidental; estado real del cifrado; sensibilidad de los archivos almacenados; identidad y autenticidad del remitente del mensaje que solicita dinero. |
