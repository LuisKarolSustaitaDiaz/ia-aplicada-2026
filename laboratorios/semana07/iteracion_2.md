# Iteración 2 - Rol + contexto

Modelo: [nombre y versión]
Fecha: [fecha]

## Prompt usado

(Se reemplazó [ENTRADA] por cada una de las tres entradas, en una conversación nueva cada vez.)

```
Eres analista de seguridad de primer nivel en un centro de operaciones. Tu lector es un técnico que atenderá el incidente y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan usuarios sin conocimientos técnicos. Los tipos de incidente posibles son: acceso no autorizado, phishing, malware, pérdida de dispositivo, otro. Las severidades posibles son: baja, media, alta.

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

## Clasificación del incidente

- **Tipo de incidente:** Phishing.
- **Severidad:** Alta.
- **Fecha y hora del incidente:** Hoy, a las 9:15 a. m.
- **Activo afectado:** Cuenta de correo institucional.
- **Equipo involucrado:** Laptop de trabajo conectada al Wi-Fi de la oficina.

**Justificación:** El usuario recibió un correo falso que aparentaba ser de Recursos Humanos, hizo clic en un enlace e ingresó su usuario y contraseña institucionales. Esto indica un posible robo de credenciales. La contraseña aún no ha sido cambiada.

**Acciones recomendadas para el técnico:**
1. Contactar al usuario y confirmar el incidente.
2. Restablecer la contraseña y revocar sesiones o tokens activos.
3. Revisar los inicios de sesión recientes y detectar accesos sospechosos.
4. Bloquear o investigar el remitente y el enlace malicioso.
5. Revisar si hubo acceso no autorizado y evaluar la laptop.

**Nota:** Se clasifica como phishing de severidad alta por el riesgo inmediato sobre la cuenta institucional. La severidad es preliminar y debe confirmarse según el impacto y las evidencias encontradas. El robo de credenciales no confirma por sí solo que alguien ya haya accedido a la cuenta.

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

**Tipo de incidente:** Acceso no autorizado
**Severidad:** Media

**Justificación:** El usuario sospecha que alguien ingresó a su correo electrónico sin autorización. Ya cambió su contraseña, pero se desconoce si el atacante accedió a sus mensajes o si la cuenta sigue comprometida. No hay evidencia suficiente para confirmar robo de credenciales mediante phishing ni infección por malware.

**Acciones recomendadas:**
1. Revisar la actividad reciente y los dispositivos conectados a la cuenta.
2. Cerrar todas las sesiones activas y activar la autenticación multifactor.
3. Verificar las reglas de reenvío, los datos de recuperación y los mensajes enviados.
4. Escalar la severidad a alta si se confirma acceso indebido con exposición de información sensible o actividad maliciosa persistente.

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

**Tipo de incidente:** Pérdida de dispositivo
**Severidad:** Alta

**Justificación:** La laptop está desaparecida y existe la posibilidad de que haya sido robada. Contenía archivos del proyecto y no se ha confirmado si estaba cifrada. Además, se recibió un mensaje solicitando dinero para devolverla, lo que podría indicar un intento de extorsión. Se requiere verificar el incidente y evaluar el riesgo de exposición de información.

**Acción inmediata recomendada:** Reportar la pérdida al equipo de seguridad, bloquear o borrar remotamente el dispositivo si es posible y verificar si contenía información sensible. No pagar ni responder al mensaje hasta que se investigue su origen.
