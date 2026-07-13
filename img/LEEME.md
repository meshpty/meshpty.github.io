# Capturas de pantalla

Las 7 capturas ya están puestas (formato `.jpg`). `nodos-fijos.html` las busca aquí.
Si vuelves a tomar alguna, **conserva el nombre exacto** o el sitio la verá rota.

| Nombre del archivo | Qué captura va aquí |
|---|---|
| `config-menu.jpg` | El menú principal de configuración (engranaje), con las secciones *Radio configuration* / *Device configuration* / *Module configuration*, y **Device configuration** resaltado. |
| `device-config.jpg` | El submenú con la lista **Device · Position · Power · Network · Display · Bluetooth**, con **Device** resaltado arriba. |
| `device-role.jpg` | La lista desplegable de **Device Role**: REPEATER, TRACKER, SENSOR, TAK, CLIENT_HIDDEN, LOST_AND_FOUND, TAK_TRACKER, ROUTER_LATE y **CLIENT_BASE**. |
| `position-menu.jpg` | El mismo submenú de *Device configuration*, pero con **Position** resaltado. |
| `gps-fijo.jpg` | La pantalla **Device GPS** con *Fixed Position* encendido, los campos Latitude / Longitude / Altitude, y el botón *Set from current phone location*. |
| `channels-menu.jpg` | El menú de configuración con **Channels** resaltado (bajo *Radio configuration*). |
| `canal-longfast.jpg` | El diálogo de edición del canal **LongFast**: PSK, Uplink/Downlink, **Position enabled**, **Precise location** y el deslizador de precisión (± 597 ft). |

## Formato

- **JPG** (los `<img src>` de `nodos-fijos.html` apuntan a `.jpg`; si cambias a PNG, cambia también la extensión ahí).
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
