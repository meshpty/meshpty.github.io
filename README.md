# MeshPTY

Sitio de la comunidad independiente de usuarios de Meshtastic en Panamá.

HTML y CSS puros. Sin build, sin dependencias, sin JavaScript. Subes los archivos y ya está.

## Archivos

```
index.html         Inicio — malla animada, bitácora de la red, casos de uso
comprar.html       Guía de compra — dos nodos, 915 vs 868, casillero, límite de 6 dBi
instalar.html      Firmware — flasher + configuración estándar MeshPTY
nodos-fijos.html   Infraestructura — hardware solar, CLIENT_BASE, posición fija, privacidad
roles.html         Roles de nodo — cuál poner y por qué
carta-azotea.html  Carta modelo para pedir permiso de azotea
mqtt.html          Guía MQTT
mapa.html          Registro de nodos y cobertura
sin-senal.html     Saturación, apagones y Bocas del Toro
legal.html         Regulación ASEP — PNAF, potencias, PIRE, fuentes
faq.html           Preguntas frecuentes
comunidad.html     Canales, radioaficionados, cómo ayudar
meetups.html       Quedadas — próxima fecha, qué llevar, historial

styles.css         Sistema visual completo
favicon.svg        Grafo de malla
og.png             1200×630 — la tarjeta que sale al compartir el link
img/               Capturas de la app (ver img/LEEME.md)
```

**El menú son cuatro grupos, no trece enlaces.** Un nav plano de trece elementos no es una jerarquía:

```
Empezar    → comprar · instalar
La red     → nodos-fijos · roles · mapa · carta-azotea · mqtt
Comunidad  → comunidad · meetups
Ayuda      → faq · sin-senal · legal
```

Los submenús se abren al pasar el mouse y al recibir foco con el teclado (`:hover` + `:focus-within`), sin una línea de JavaScript. En pantallas angostas la barra se parte en dos filas y el panel ocupa todo el ancho.

---

## Mantener la quedada al día

Tres sitios traen la fecha escrita a mano. Al cambiar de quedada hay que tocar los tres:

1. `meetups.html` → bloque `.ledger` de "Próxima quedada" (fecha, hora, lugar y enlace de mapa).
2. `index.html` y `comunidad.html` → la `<section class="aviso-quedada">`. **Cuando la fecha pase, se borra o se actualiza** — un aviso vencido en la portada es peor que ninguno.
3. `meetups.html` → tabla "Quedadas anteriores": una fila con fecha, lugar y qué salió de ahí.

---

## Estado: todo publicado

Los tres pendientes que había antes ya están resueltos:

- **Capturas de pantalla.** Las 8 imágenes están en `img/` y todas las referencias de los HTML apuntan a archivos que existen.
- **Enlace del grupo de WhatsApp.** Ya está activo en `comunidad.html`, dentro de "Dónde encontrarnos".
- **`og:image`.** Los 12 archivos apuntan a `https://meshpty.github.io/og.png`, que existe.

Único aviso si algún día cambias de dominio: hay que actualizar esa línea de `og:image` en los 12 HTML. Facebook y WhatsApp necesitan una URL absoluta — con una relativa, la tarjeta al compartir sale vacía.

---

## Datos que ya están en el sitio

| Dato | Valor |
|---|---|
| Región LoRa | `US` |
| Preset | `LONG_FAST` |
| Canal | `LongFast` (público) |
| Slot / frecuencia | 20 · 906.875 MHz (automático) |
| Grupo de Facebook | `facebook.com/groups/4256086874610786` |
| Contacto | Alvaro · alvaroenoht@gmail.com · nodos `Kmu` |

Si algo de esto cambia, está en todas las páginas — usa buscar y reemplazar.

---

## Publicar en GitHub Pages

```bash
git init
git add .
git commit -m "MeshPTY: sitio inicial"
git branch -M main
git remote add origin https://github.com/meshpty/meshpty.github.io.git
git push -u origin main
```

Luego en GitHub: **Settings → Pages → Source: `Deploy from a branch` → Branch: `main` / `root` → Save.**

En 1–2 minutos está en vivo.

### Sobre el nombre del repo

**Recomendado:** crea una **organización** de GitHub llamada `meshpty` y dentro un repo llamado `meshpty.github.io`. Con eso el sitio queda en **`https://meshpty.github.io`** — limpio, y el proyecto no cuelga de tu cuenta personal (importante si algún día quieres co-mantenedores o pasarle las llaves a alguien).

Si lo pones en tu cuenta personal con el repo llamado `meshpty`, la URL sale como `https://TU-USUARIO.github.io/meshpty`. Funciona igual, pero se ve peor y te ata al proyecto.

### Dominio propio (opcional, después)

Los enlaces del sitio son relativos, así que **puedes migrar a un dominio propio en cualquier momento sin romper nada.** No dejes que la compra del dominio te frene hoy.

Cuando lo compres (Namecheap, Porkbun o Cloudflare; ~US$10–15/año — evita el `.pa`, es caro y burocrático):

1. Crea un archivo llamado `CNAME` (sin extensión) en la raíz del repo, con una sola línea:
   ```
   meshpty.org
   ```
2. En tu DNS, apunta el dominio a GitHub Pages siguiendo la [guía oficial](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).
3. **Settings → Pages → Custom domain** → pega el dominio → marca **Enforce HTTPS**.

---

## Listarse en meshtastic.org

Cuando el sitio esté en vivo, agrega Panamá a la [página de grupos locales](https://meshtastic.org/docs/community/local-groups/). Hoy **Panamá no existe en esa lista** — la estarías creando.

Es un PR sobre [`docs/community/local-groups.mdx`](https://github.com/meshtastic/meshtastic/blob/master/docs/community/local-groups.mdx), en orden alfabético entre `## Norway` y `## Poland`:

```markdown
## Panama

- [MeshPTY - Panama Meshtastic Community](https://meshpty.github.io)
```

### Por qué el nombre no es "Meshtastic Panamá"

Los [requisitos de marca](https://meshtastic.org/docs/legal/licensing-and-trademark/) para aparecer en esa lista:

- El nombre y el enlace del grupo **no pueden ser "Meshtastic [ciudad/país]"** — implicaría patrocinio oficial.
- El logo de Meshtastic solo puede usarse en **posición secundaria** respecto a la marca propia. Ante la duda, usar el logo M-Powered o un diseño propio.
- Los enlaces de invitación a Discord deben ser permanentes (no expirar).

El sitio ya incluye el descargo de responsabilidad requerido en el pie de todas las páginas.

Este es justamente el problema que MeshPTY resuelve: el grupo de Facebook se llama "Meshtastic Panama" y no lo administras tú, así que no se puede listar tal cual. MeshPTY sí se puede listar, y desde ahí se enlaza el grupo de Facebook. No hace falta el permiso de nadie.

---

## Regulación: resuelta y documentada

`legal.html` documenta la banda con base en el **PNAF de la ASEP**:

| Punto | Valor |
|---|---|
| Banda 902–928 MHz | Uso libre / no licenciado, aplicaciones ICM, centro en 915 MHz |
| Licencia | No requiere |
| Cánones | Exento |
| Potencia TX máx. | 30 dBm (1 W) |
| Ganancia de antena máx. | 6 dBi |
| PIRE máx. | 36 dBm (4 W) |
| Interferencias | Sin derecho a protección; obligación de no interferir |
| Homologación | Los equipos transmisores deben cumplir el procedimiento de la ASEP |
| Uso comercial | Requiere registrar cada estación transmisora |

**Fuentes citadas en el sitio:** [PNAF de la ASEP](https://asep.gob.pa/direcciones/telecomunicaciones/pnaf/) y la [Resolución AN No. 20335-Telco del 5 de mayo de 2025](https://asep.gob.pa/an-no-20335-telco-de-2025-05-05/) (Gaceta Oficial 30281), que actualiza el PNAF.

La página lleva un descargo claro: es divulgación hecha por aficionados, no asesoría legal, y si algo contradice al PNAF, manda el PNAF.

### Sigue pendiente (y es fácil)

Panamá **todavía no aparece** en la [tabla de regiones por país de Meshtastic](https://meshtastic.org/docs/configuration/region-by-country/). Ahora que tenemos la fuente, es un PR de una línea sobre [`region-by-country.mdx`](https://github.com/meshtastic/meshtastic/blob/master/docs/configuration/region-by-country.mdx):

```markdown
| Panama | US | [PNAF - ASEP](https://asep.gob.pa/direcciones/telecomunicaciones/pnaf/) |
```

Es una contribución pequeña con nombre y apellido de Panamá en la documentación oficial del proyecto.

---

## Licencia

Contenido libre de usar y adaptar por la comunidad.

Meshtastic® es una marca registrada de Meshtastic LLC. MeshPTY no está afiliado a Meshtastic LLC.
