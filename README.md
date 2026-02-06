# Jarvis PC (prototipo en Python)

Asistente por voz en español tipo "Jarvis" para automatizar tareas en una PC:

- Reconocimiento de voz por micrófono.
- Respuesta por voz (TTS).
- Apertura de aplicaciones y webs.
- Control básico de mouse/teclado.
- Ejecución de comandos del sistema con confirmación.
- Modo texto para pruebas sin micrófono.

> ⚠️ Este proyecto **no** replica todo lo de Jarvis de ficción. Es un punto de partida realista y ampliable para automatización local.

## Requisitos

- Python 3.10+
- Windows/macOS/Linux
- Micrófono (opcional si usas `--text-mode`)

## Instalación

```bash
python -m venv .venv
source .venv/bin/activate   # en Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

En Linux, `SpeechRecognition` puede requerir `portaudio` para `PyAudio`.

## Uso rápido

```bash
python jarvis_pc.py --wake-word jarvis
```

Modo texto (sin micrófono):

```bash
python jarvis_pc.py --text-mode
```

## Comandos de voz soportados (ejemplos)

- `jarvis abre navegador`
- `jarvis abre bloc de notas`
- `jarvis abre youtube`
- `jarvis escribe hola mundo`
- `jarvis mueve mouse arriba`
- `jarvis clic`
- `jarvis ejecuta comando dir`
- `jarvis ayuda`
- `jarvis salir`

## Seguridad

La ejecución de comandos del sistema pide confirmación por voz/texto. Puedes desactivarla con `--allow-unsafe`, pero **no se recomienda**.

## Personalización

Edita en `jarvis_pc.py`:

- `APP_ALIASES`: alias de apps locales.
- `SITE_ALIASES`: alias de sitios web.
- `parse_intent(...)`: reglas de comprensión de comandos.

## Próximos pasos recomendados

- Integrar motor offline robusto (Vosk/Whisper local).
- Añadir hotword dedicado.
- Crear capa de permisos por comando.
- Añadir memoria contextual y plugins.
