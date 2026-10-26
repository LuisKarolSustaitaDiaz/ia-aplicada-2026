# Iteración 4 - Anterior + ejemplos (few-shot)

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

Ejemplo de entrada:
"Encontré una USB en el estacionamiento y la conecté a mi computadora de la oficina para ver de quién era. Ahora se abren ventanas solas y mis archivos tienen una extensión rara. Pasó hoy a las 3 pm."

Ejemplo de salida:
| Campo | Valor |
|---|---|
| Tipo de incidente | malware |
| Severidad | alta |
| Activo afectado | computadora de oficina y archivos almacenados en ella |
| Primera acción recomendada | desconectar el equipo de la red y avisar al área de seguridad |
| Información faltante | ninguna |

Ahora clasifica este reporte de incidente:

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
| Tipo de incidente | phishing |
| Severidad | alta |
| Activo afectado | Cuenta de correo institucional y laptop de trabajo conectada al wifi de la oficina |
| Primera acción recomendada | Cambiar inmediatamente la contraseña desde un dispositivo confiable, notificar al equipo de seguridad y solicitar la revocación de sesiones activas. |
| Información faltante | Confirmar si la cuenta presenta accesos no autorizados, si la contraseña se reutiliza en otros servicios y si se descargaron archivos o se ejecutaron aplicaciones desde el enlace. |

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
| Tipo de incidente | acceso no autorizado |
| Severidad | alta |
| Activo afectado | cuenta de correo electrónico y posibles mensajes personales o laborales |
| Primera acción recomendada | verificar las sesiones activas, cerrar las sesiones desconocidas, activar la autenticación multifactor y avisar al área de seguridad para revisar posibles accesos indebidos. |
| Información faltante | fecha y hora del aviso, proveedor de correo, detalles del inicio de sesión sospechoso, existencia de sesiones desconocidas y confirmación de si la cuenta sigue presentando actividad inusual después del cambio de contraseña. |

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
| Tipo de incidente | Pérdida de dispositivo |
| Severidad | Alta |
| Activo afectado | Laptop y archivos del proyecto almacenados en ella |
| Primera acción recomendada | Reportar inmediatamente la pérdida al área de seguridad, bloquear o localizar el dispositivo mediante herramientas autorizadas y revocar sus sesiones y accesos corporativos. |
| Información faltante | Ubicación y hora exactas de la última vez que se vio la laptop, confirmación de robo o pérdida, existencia de cifrado, sensibilidad de los archivos, presencia de respaldos y autenticidad del mensaje que solicita dinero. |
