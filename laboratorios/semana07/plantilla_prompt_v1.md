# Plantilla: clasificación de incidente v1

# Variables: {ROL_LECTOR}, {CATEGORIAS}, {SEVERIDADES}, {ENTRADA}

Eres analista de seguridad de primer nivel en un centro de operaciones. Tu lector es {ROL_LECTOR} y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan usuarios sin conocimientos técnicos. Los tipos de incidente posibles son: {CATEGORIAS}. Las severidades posibles son: {SEVERIDADES}.

Responde únicamente con esta tabla en Markdown, sin texto adicional:

| Campo | Valor |
|---|---|
| Tipo de incidente | |
| Severidad | |
| Activo afectado | |
| Primera acción recomendada | |
| Información faltante | |

Si un campo no puede determinarse a partir del texto, escribe "NO ESPECIFICADO" en Valor y explica qué falta en la fila "Información faltante".

Texto a clasificar:

{ENTRADA}

---

## Instrucciones de uso

### Qué poner en cada variable

| Variable | Qué poner | Ejemplo |
|---|---|---|
| `{ROL_LECTOR}` | Quién leerá la salida | un técnico que atenderá el incidente |
| `{CATEGORIAS}` | Lista cerrada de tipos de incidente, separados por comas | acceso no autorizado, phishing, malware, pérdida de dispositivo, otro |
| `{SEVERIDADES}` | Lista cerrada de niveles de severidad | baja, media, alta |
| `{ENTRADA}` | El texto del usuario, completo y sin editar | "Hola, creo que alguien entró a mi correo..." |

### Cómo usarla

1. Copia el bloque de la plantilla (desde "Eres analista..." hasta `{ENTRADA}`).
2. Reemplaza las cuatro variables, incluidas las llaves.
3. Pégalo en una **conversación nueva** para cada reporte, para que el modelo no arrastre casos anteriores.

### Modelo probado

[Escribe aquí el modelo y la versión, por ejemplo: ChatGPT / Gemini / Deepseek, versión y fecha de prueba]

### Puntaje obtenido

- Iteración 3 (esta plantilla): **18/18** en las tres entradas originales (C1 = 6, C2 = 6, C3 = 6).
- Prueba de robustez con una cuarta entrada: [escribe aquí el puntaje sobre 6 y si cayó más de 2 puntos respecto al promedio].

### Por qué esta versión y no otra

Se adoptó la iteración 3 (rol + contexto + formato) porque obtuvo el máximo puntaje y es la más corta. El ejemplo (iteración 4) bajó C3 en la Entrada 2, y el análisis previo (iteración 5) rompió el formato "sin texto adicional" (C2).

### Limitaciones conocidas

- Los criterios se saturaron en la iteración 3, así que la mejora de las técnicas 4 y 5 no pudo medirse bien.
- La severidad es una estimación provisional del modelo y debe confirmarla una persona.
- Solo se probó con cuatro entradas, de tipo correo y laptop, y con un solo modelo.
- Si cambias las categorías por otras muy distintas, vuelve a probar la plantilla.
- Si el modelo cambia de versión, repite la evaluación con las mismas entradas y criterios.
