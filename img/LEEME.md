# Capturas de pantalla

Guarda aquí las capturas de la app de Meshtastic, **con estos nombres exactos**.
El sitio ya las está buscando — hasta que existan, vas a ver imágenes rotas en `nodos-fijos.html`.

| Nombre del archivo | Qué captura va aquí |
|---|---|
| `config-menu.png` | El menú principal de configuración (engranaje), con las secciones *Radio configuration* / *Device configuration* / *Module configuration*, y **Device configuration** resaltado. |
| `device-config.png` | El submenú con la lista **Device · Position · Power · Network · Display · Bluetooth**, con **Device** resaltado arriba. |
| `device-role.png` | La lista desplegable de **Device Role**: REPEATER, TRACKER, SENSOR, TAK, CLIENT_HIDDEN, LOST_AND_FOUND, TAK_TRACKER, ROUTER_LATE y **CLIENT_BASE**. |
| `position-menu.png` | El mismo submenú de *Device configuration*, pero con **Position** resaltado. |
| `gps-fijo.png` | La pantalla **Device GPS** con *Fixed Position* encendido, los campos Latitude / Longitude / Altitude, y el botón *Set from current phone location*. |
| `channels-menu.png` | El menú de configuración con **Channels** resaltado (bajo *Radio configuration*). |
| `canal-longfast.png` | El diálogo de edición del canal **LongFast**: PSK, Uplink/Downlink, **Position enabled**, **Precise location** y el deslizador de precisión (± 597 ft). |

## Formato

- **PNG** (si usas JPG, cambia la extensión en `nodos-fijos.html`).
- Las capturas de celular sirven tal cual — el sitio las escala a 280 px de ancho y las muestra con marco redondeado.
- No hace falta recortarlas ni editarlas.

## ⚠️ Antes de subirlas: revisa qué se ve

Estas capturas van a quedar **públicas en internet**. Antes de subirlas, mira si alguna muestra:

- Coordenadas reales de tu casa
- Nombres de nodos que prefieras no publicar
- La PSK de un canal privado (la del canal público `LongFast` no importa — es conocida)

Si algo de eso aparece, tápalo o vuelve a tomar la captura con datos de ejemplo.

## Si prefieres no poner imágenes

Borra los bloques `<figure class="shot">...</figure>` de `nodos-fijos.html`. Los tutoriales funcionan igual sin ellas — las capturas ayudan, pero no son imprescindibles.
