# Iteración 1 - Rol

Modelo: [nombre y versión]
Fecha: [fecha]

## Prompt usado

(Se reemplazó [ENTRADA] por cada una de las tres entradas, en una conversación nueva cada vez.)

```
Eres analista de seguridad de primer nivel en un centro de operaciones. Tu lector es un técnico que atenderá el incidente y necesita información precisa.

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

# Clasificación del incidente de seguridad

**Severidad:** ALTA
**Tipo:** Phishing
**Estado:** Activo / Contención urgente

## 1. Resumen del incidente
Un empleado recibió un correo fraudulento que aparentaba provenir de Recursos Humanos, solicitando actualizar sus datos de nómina. El empleado abrió el enlace e ingresó su usuario y contraseña institucionales. Posteriormente detectó que el remitente era sospechoso.

## 2. Datos de clasificación

| Campo | Clasificación |
|---|---|
| Categoría | Phishing con posible robo de credenciales |
| Activo afectado | Cuenta de correo institucional |
| Equipo involucrado | Laptop de trabajo |
| Red involucrada | Wi-Fi de la oficina |
| Hora del incidente | 9:15 a. m. (fecha por confirmar) |
| Credenciales expuestas | Usuario y contraseña |
| Impacto confirmado | Exposición de credenciales |
| Impacto potencial | Acceso no autorizado, robo de información y movimiento lateral |

## 3. Acciones inmediatas para el técnico
1. **Contener el equipo:** Aislar la laptop de la red mediante el procedimiento de respuesta a incidentes. No apagarla ni borrar archivos sin indicación del equipo responsable.
2. **Proteger la cuenta:** Desde un dispositivo limpio, cambiar la contraseña y revocar sesiones o tokens activos. Revisar MFA y restablecerlo si existe sospecha de compromiso.
3. **Investigar el incidente:** Revisar inicios de sesión, reglas de reenvío, actividad de la cuenta, URL del enlace, registros del correo y alertas del endpoint.
4. **Erradicar y prevenir:** Bloquear el remitente, dominio o URL maliciosa según validación; buscar y retirar correos similares y notificar al equipo de seguridad.

## 4. Información pendiente de verificar
- ¿La página era falsa y se confirmó la captura de credenciales?
- ¿Hubo accesos exitosos desde ubicaciones o dispositivos desconocidos?
- ¿La laptop descargó o ejecutó algún archivo?
- ¿La cuenta tiene MFA habilitado?
- ¿Se reutilizó la contraseña en otros servicios?

## 5. Prioridad de atención
Prioridad P1 (alta, provisional): atender inmediatamente debido a la exposición de credenciales institucionales y a que la contraseña continúa sin cambiarse.

La severidad deberá ajustarse según los hallazgos. El clic por sí solo no confirma infección del equipo, y el robo de credenciales no demuestra todavía que la cuenta haya sido comprometida por un tercero.

**Nota para el técnico:** preservar evidencias y documentar horas, acciones realizadas y resultados de la investigación.

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

# Clasificación del incidente de seguridad

**Prioridad:** Alta
**Tipo:** Sospecha de compromiso de cuenta

1. **Clasificación:** Posible acceso no autorizado al correo electrónico institucional o personal. Se requiere investigación para confirmar si la cuenta fue comprometida.
2. **Severidad:** Alta (provisional), debido al posible acceso a mensajes e información confidencial. La severidad definitiva depende de la evidencia y del tipo de cuenta afectada.
3. **Indicadores detectados:**
   - Aviso de seguridad inusual.
   - Sospecha de inicio de sesión no autorizado.
   - Contraseña cambiada por el usuario.
   - Posible exposición de mensajes.
   - Dispositivos y ubicaciones de acceso variados.
   - Fecha de inicio y vector de ataque desconocidos.
4. **Acciones recomendadas para el técnico:**
   1. Revisar los registros de inicio de sesión, ubicaciones, dispositivos, IP y alertas de seguridad.
   2. Revocar las sesiones activas y los tokens de acceso, según las capacidades de la plataforma.
   3. Verificar y eliminar reglas de reenvío, filtros, aplicaciones conectadas y métodos de recuperación desconocidos.
   4. Confirmar que la contraseña se cambió desde un dispositivo confiable y activar MFA (autenticación multifactor).
   5. Preservar evidencias y revisar accesos a mensajes, cambios de configuración y posibles envíos de correos maliciosos.
   6. Confirmar con el usuario si reutilizó la contraseña en otros servicios y protegerlos si es necesario.
5. **Datos pendientes de confirmar:**
   - ¿Qué aviso recibió y cuándo?
   - ¿El correo es institucional o personal?
   - ¿Hay inicios de sesión desconocidos o cambios no autorizados?
   - ¿La cuenta tiene MFA habilitado?

**Conclusión:** Tratar como un posible compromiso de cuenta de correo, mantener la investigación abierta y aplicar medidas de contención mientras se confirma el acceso no autorizado. No se debe afirmar que hubo robo de información sin evidencia.

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

# Clasificación del incidente de seguridad

**Prioridad:** Alta
**Tipo:** Pérdida o posible robo de equipo

1. **Clasificación:** Posible pérdida o robo de laptop con riesgo de exposición de información y posible intento de extorsión.
2. **Severidad:** Alta (provisional). Puede aumentar a crítica si se confirma que el equipo contenía información sensible, no estaba cifrado o tenía accesos corporativos activos.
3. **Indicadores detectados:**
   - Laptop desaparecida desde ayer.
   - Lugar de pérdida o robo sin confirmar.
   - Archivos de un proyecto almacenados en el equipo.
   - Estado del cifrado desconocido.
   - Mensaje solicitando dinero para devolver el equipo, de autenticidad no confirmada.
4. **Acciones recomendadas para el técnico:**
   1. Reportar y registrar el incidente inmediatamente; confirmar último lugar y hora donde se vio el equipo.
   2. Identificar número de serie, usuario asignado y datos corporativos almacenados.
   3. Revocar sesiones, tokens y accesos corporativos asociados al equipo; bloquearlo o aplicar borrado remoto si está autorizado y corresponde.
   4. Verificar el cifrado del disco, estado de bloqueo y existencia de información sensible.
   5. Preservar el mensaje de solicitud de dinero, incluyendo remitente, hora y evidencia. No pagar ni confrontar al remitente sin autorización.
   6. Evaluar notificación a responsables de seguridad, privacidad y autoridades, según las políticas aplicables.
5. **Datos pendientes de confirmar:**
   - ¿La laptop realmente fue robada o quedó en la oficina?
   - ¿Qué información contenía y qué tan sensible era?
   - ¿Tenía cifrado completo del disco y contraseña/PIN?
   - ¿El mensaje proviene de una fuente verificable?
   - ¿El equipo tenía VPN, correo o sesiones corporativas abiertas?

**Conclusión:** Tratar como un incidente de pérdida o posible robo de activo tecnológico con riesgo de fuga de información y posible extorsión. Mantenerlo abierto hasta confirmar la ubicación del equipo, el alcance de la exposición y la autenticidad del mensaje. No asumir que hubo filtración de datos ni que el robo está confirmado.
