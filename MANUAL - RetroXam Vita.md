# 🎮 MANUAL COMPLETO — Deja tu PS Vita PERFECTA con RetroXam (v3.5)

Con este manual tu PS Vita queda con:
- **El launcher RetroXam v3.5**: buscas el juego, pulsas X, se descarga y se abre solo. Con **carátulas**, iconos, temas y **AUTO-CONFIG** (bezels + shaders se instalan solos).
- **RetroArch** (build estándar, 132 cores) → NES, SNES, GB/GBC/GBA, Mega Drive, Mega CD, 32X, PSX, Neo Geo, CPS-1/2/3 y FBNeo.
- **DaedalusX64** → Nintendo 64 · **OpenBOR** → beats 'em up · **PSVitaAlive** → tienda de homebrew.
- **PSP** (vía **Adrenaline**, ¡NATIVO, no emulado!) y **Dreamcast** (vía **Flycast**, juegos compatibles).
- **~2.200 juegos** seleccionados (**18 sistemas**), con **prioridad a versiones en español**.

> 📖 **Este manual también existe en HTML con índice** (haz clic para saltar de sección): `MANUAL - RetroXam Vita.html`.

---

## ⚡ QUÉ HAY QUE HACER — el resumen

1. **¿La Vita no está liberada?** → Parte 0 (10 minutos, una vez en la vida).
2. **microSD + SD2Vita** montados con YAMT → Parte 1.
3. **Instalador del PC en 1 paso** — copia TODO solo (configs, BIOS, N64, carátulas, plugins): por **USB (rápido)** o **FTP** → Parte 2.
4. **REINICIA la consola UNA vez** (activa los plugins del Dreamcast).
5. **Instala los VPKs con X**, en orden → Parte 3.
6. **Abre RetroXam** (con WiFi) → se auto-configura → elige un juego → **X** → ¡a jugar! 🎉

> Los BIOS ya van incluidos por el instalador, y el "1 toque" de PSP o la tienda son extras opcionales. Nada más que hacer.

---

## 📦 Lo que necesitas

| Cosa | Detalle |
|---|---|
| PS Vita | Cualquier modelo. Si no está liberada → Parte 0 |
| microSD + SD2Vita | **Muy recomendado** (128 GB+). El kit + juegos no caben en la tarjeta oficial |
| PC Windows + cable USB | También vale por WiFi (FTP) |
| Kit RetroXam Vita | Escritorio: acceso directo **"Kit RetroXam Vita"**, o la carpeta `C:\Users\XAM-PC\VitaKit\apps` |

**Contenido del kit:**

| Archivo | Qué es | Tamaño |
|---|---|---|
| `RetroXam_v3.5.vpk` | El launcher (**v3.5**: 18 sistemas + PSP/Dreamcast, listas estilo Apple y auto-config) | 5 MB |
| `RetroArch.vpk` | RetroArch build **estándar** (la recomendada: encuadre de fábrica) | ~690 MB |
| `RetroArch_piglet.vpk` | Alternativa **con shaders** (opcional; ver EXTRA 3) | ~473 MB |
| `PIBConfig.vpk` | Solo con la build piglet (se abre **una vez**) | 2 MB |
| `DaedalusX64.vpk` + `DaedalusX64-data.zip` | Emulador + datos de Nintendo 64 | 3 MB + 75 MB |
| `OpenBOR.vpk` | Motor Beats of Rage | 1 MB |
| `Adrenaline.vpk` + `661.PBP` | **PSP nativo** (el firmware se baja solo; 661.PBP es el plan B) | 0,5 + 31 MB |
| `Flycast.vpk` | Dreamcast (experimental — solo juegos compatibles) | 4,6 MB |
| `ShaRKBR33D.vpk` | Librería `libshacccg.suprx` que exigen Daedalus y Flycast (se abre **una vez**) | 1,5 MB |
| `Plugins\` | **kubridge + fd_fix** (¡imprescindibles para Flycast!) + AutoPlugin2 + iTLS-Enso — **el instalador los configura solo** | 15 MB |
| `PSVitaAlive.vpk` | **Tienda de homebrew** para la Vita (catálogo abierto; se actualiza sola) — opcional | 8 MB |
| `Config_RetroXam_Piglet.zip` | Ajustes por core + config de RetroArch (respaldo manual) | 0,7 MB |
| `RetroXamVita_Covers.zip` | Las 2.151 carátulas de todos los sistemas (opcional: se descargan solas) | 54 MB |
| `PSP_1toque\` | **Extra opcional**: lanzar juegos PSP directos desde RetroXam (ABM + AdrenalineLauncher + LEEME) | 11 MB |
| `INSTALAR VITA (USB - rapido).bat` | Instalador de PC en 1 paso por **USB** (la vía rápida) | — |
| `INSTALAR VITA.bat` | Instalador de PC en 1 paso por **FTP** (sin cable) | — |

---

## 🛠️ PARTE 0 — Liberar la Vita (solo si no lo está)

> Si ya tienes **Enso** instalado (se ve "HENkaku" en Ajustes), salta a la Parte 1.

1. Mira tu firmware: **Ajustes → Sistema → Información del sistema**.
   - HENlo funciona en **3.65, 3.68 y 3.74**. Si tienes otra versión, sigue la guía oficial **vita.hacks.guide** (te llevará a 3.65 igualmente).
2. En la Vita, abre el **navegador** y entra en: `http://jailbreak.psp2.dev`
3. Pulsa **"Unlock my Vita" → "Unlock"**. Si va bien, verás la pantalla **henlo-bootstrap**.
4. Pulsa **X en "Install henkaku" → X en "Install VitaDeploy" → X en "Exit"**.
5. **Ajustes → HENkaku Settings** → marca **"Enable Unsafe Homebrew"** → cierra Ajustes.
6. Hazla **permanente** (recomendado): abre **VitaDeploy → "Install a different OS" → "Quick 3.65 Install"** (necesita internet):
   - Espera a que descargue → **X** para confirmar → lee el aviso, espera 20 s → **X** otra vez.
   - ⚠️ No dejes que la consola se suspenda durante el proceso. Al terminar reinicia ya con CFW (**firmware 3.65 + Enso, para siempre**).
7. Instala **VitaShell** (tu gestor de archivos): **VitaDeploy → App Downloader → VitaShell** → descarga e instala.

> Referencia oficial (por si algo se tuerce): **vita.hacks.guide**

---

## 💾 PARTE 1 — SD2Vita (la memoria de verdad)

> Si hiciste "Quick 3.65 Install", **YAMT ya viene instalado** — salta al paso 1.

1. Mete el adaptador **SD2Vita con tu microSD** en la ranura de juegos.
2. **VitaDeploy → Miscellaneous → Format a storage device** → Target: `SD2Vita`, Filesystem: **`TexFAT`** → **"Format target storage"**.
3. Vuelve al menú → **Reboot**.
4. **Ajustes → Dispositivos → Dispositivos de almacenamiento** → activa **"Use YAMT"**:
   - Deja `ux0:` en `Default` y `uma0:` en `SD2Vita` → apaga y enciende la consola.
   - *(Solo si ya tenías cosas instaladas:)* en **VitaShell**, copia TODO de `ux0:` a `uma0:` (△ → Mark all → Copy → entrar en `uma0:` → △ → Paste).
5. Cambia a: **`ux0:` → `SD2Vita`** y `uma0:` → `Default` → apaga y enciende.
   → **ux0: (lo principal) ahora es tu microSD.** Todo lo que sigue va ahí.

---

## 📁 PARTE 2 — Instalar TODO desde el PC (1 paso) ⚡

> El instalador deja **cada cosa en su sitio, solo**. Elige la vía que prefieras:

### 🅰 USB — la vía rápida (recomendada, con cable) — ¡AHORA EN 2 PASOS! ⭐

**PASO 1 — las VPKs** (2 min):
1. En la Vita: **VitaShell → START → pon SELECT = USB → cierra con O → pulsa SELECT** → conecta el cable USB. La Vita aparece como **unidad** (puede ser `P:`, `F:`…).
2. En el PC: doble clic a **`PASO 1 - VPKs a la Vita (USB).bat`** → letra de la unidad (o **Enter = autodetectar**).
3. Desconecta el USB e **instala las VPKs** en la Vita (Parte 3) + abre **PIBConfig** y **ShaRKBR33D** una vez cada una.

**PASO 2 — todo lo demás + config automática** (5 min):
4. Vuelve a conectar el USB (mismo modo) y ejecuta **`PASO 2 - CONFIG (USB).bat`** → copia configs, BIOS, N64, carátulas, plugins… y **ajusta tu RetroArch solo** (driver `gl` para shaders, carpetas, combo del menú), con copia de seguridad `.retroxam.bak`.
5. Verás el progreso (por bloques y por MB). Al final **"=== TERMINADO ==="**.
6. Desconecta, **REINICIA la consola** y abre RetroXam.

*(¿Repetir es seguro? Sí: cada PASO salta lo que ya está = `+0 copiados`.)*

### 🅱 FTP — sin cable (por WiFi)

1. En la Vita: **VitaShell → pulsa SELECT** (modo FTP) → apunta la **IP** que sale en pantalla.
2. En el PC: doble clic a **`INSTALAR VITA.bat`** → escribe la IP.

### 📋 ¿Qué copia exactamente el instalador?

| A dónde | Qué |
|---|---|
| `ux0:/` | Los 11 VPKs + `661.PBP` (+ PSVitaAlive, iTLS, AutoPlugin2) |
| `ux0:/data/retroarch/` | Bezels + shaders + ajustes por core (v1.1) |
| `ux0:/data/retroarch/system/` | Los BIOS |
| `ux0:/data/DaedalusX64/` | Los datos del N64 (610 archivos) |
| `ux0:/data/retroxam/` | El ZIP completo de carátulas |
| `ux0:/tai/` | **kubridge + fd_fix** (Flycast) + añade las 2 líneas al `config.txt` (con copia de seguridad `.retroxam.bak`) |
| `ux0:/PSP_1toque/` | El extra del PSP "1 toque" |
| `ux0:/data/retroarch/retroarch.cfg` | **Se ajusta solo** (v3.5): driver `gl` para shaders, carpetas y combo del menú — con copia `.retroxam.bak` |

> 🔁 **Al terminar el PASO 2: REINICIA la consola UNA vez** (así se activan kubridge + fd_fix y los ajustes de RetroArch).

### ✍️ A mano (sin instalador)

1. Copia los VPKs + `661.PBP` a `ux0:/`.
2. `DaedalusX64-data.zip`: extráelo y copia la carpeta **`DaedalusX64`** a `ux0:/data/`.
3. Config/BIOS/carátulas: sigue el LEEME del pack (mismos destinos que la tabla de arriba).

---

## ⚙️ PARTE 3 — Instalar los VPKs

En **VitaShell**, ve a `ux0:/` y pulsa **X sobre cada .vpk** → confirma. **En este orden**:

> 💡 **Flujo 2 PASOS**: instala las VPKs **entre el PASO 1 y el PASO 2** (así el PASO 2 lo configura todo con RetroArch ya instalado).

1. `RetroXam_v3.5.vpk` — el launcher (v2.4)
2. `PIBConfig.vpk` — **ábrelo y pulsa X** (1 segundo; instala las librerías). Cierra.
3. `RetroArch.vpk` — la build **estándar** (sustituye a la que tuvieras; tus juegos y ajustes se quedan). *(¿Shaders CRT? Build alternativa en la carpeta 4 - Extras del pack.)*
4. `ShaRKBR33D.vpk` — **ábrelo una vez** (instala `libshacccg.suprx`, lo exigen Daedalus y los shaders). Tarda un minuto.
5. `DaedalusX64.vpk` — N64
6. `OpenBOR.vpk` — beats 'em up
7. `Adrenaline.vpk` — **ábrelo y pulsa X** (baja el firmware solo; necesita internet). PSP nativo.
8. `Flycast.vpk` — Dreamcast
9. `PSVitaAlive.vpk` — **opcional**: la tienda de homebrew
10. `iTLS-Enso.vpk` + `AutoPlugin2.vpk` — **opcionales**: internet moderno (tienda) y gestor de plugins

> Si alguna burbuja no aparece: en VitaShell pulsa **△ → Refresh livearea**.
>
> **N64**: los datos van **solos** con el instalador (queda `ux0:/data/DaedalusX64/`). Y ejecuta **ShaRKBR33D** UNA vez (sin su librería, Daedalus da el error **C2-12828-1**).

---

## 🎨 PARTE 4 — RetroArch en tu Vita (encuadre, marcos y shaders)

> ℹ️ **v3.5 — RetroArch va de fábrica**: build **estándar**, sin marcos, sin shaders y sin ventanas personalizadas → imagen **centrada y estable** (esto arregla el desplazamiento). Marcos y shaders siguen disponibles como opción (EXTRA 2 y EXTRA 3).

**No tienes que hacer nada**: el instalador ya copia la config, y ADEMÁS al abrir RetroXam por primera vez (con WiFi) el launcher **se auto-configura**: verás *"Instalando config RetroXam (bezels + shaders)..."* — una única vez.

- ✅ **Bezels**: marcos con el logo de cada consola y la seta 1-UP 🍄 en NES, SNES, GB/GBC, GBA, Mega Drive/CD, 32X, PSX, NeoGeo/Arcade y CPS-1/2 (el juego va dentro de su ventana exacta).
- ✅ **Shaders**: CRT para las de TV (crt-pi), LCD para Game Boy (lcd3x) y nitidez para GBA (sharp-bilinear). Se activan por core solos.
- **Respaldo manual** (solo si algo fallara): extraer `Config_RetroXam_Piglet.zip` en `ux0:/data/retroarch/` con VitaShell.
- **Cambiar shader a mano**: con un juego abierto → **Quick Menu → Shaders** (solo existe en la build piglet ✓) → elige otro → guarda con **Save Core Override**.
- ¿Imagen **desplazada** alguna vez (raro, le pasa a algún core)? **1º cierra y reabre el juego** (suele recentrarse solo). Si sigue: con el juego abierto **L + R + START + SELECT** = menú → **Ajustes → Vídeo → Escalado** → "Relación de aspecto: **Personalizada**" + viewport de su sistema (4:3 = 120/2/720/540 · GB/GBC = 240/56/480/432 · GBA = 156/56/648/432) → Quick Menu → Overrides → **Save Core Override**.

---

## 🧬 PARTE 5 — BIOS

Copia en **`ux0:/data/retroarch/system/`** (créala si no existe). **Con el instalador ya van incluidos**:

| Archivo | Para | ¿Obligatorio? |
|---|---|---|
| `SCPH1001.BIN` | PlayStation (pcsx_rearmed) | Muy recomendado |
| `bios_CD_E.bin` + `bios_CD_U.bin` + `bios_CD_J.bin` | Mega CD (genesis_plus_gx) | **Sí** para jugar Mega CD (una por región: EU/US/JAP) |
| `neogeo.zip` | Neo Geo | El launcher la baja sola la 1ª vez; mejor tenerla |
| `gba_bios.bin` | Game Boy Advance (mejor compatibilidad) | Opcional |

> Los BIOS se sacan de tu propia consola o de copias legales.

---

## 🚀 PARTE 6 — El launcher RetroXam (tu centro de juegos)

1. Abre **RetroXam** desde la pantalla de inicio.

> ✨ **Novedad v3.5**: interfaz **simplificada** (menos elementos, más limpia y legible): cabecera y pie ligeros, una barra blanca de selección, sin halos y fondo negro puro.
2. **Activa el WiFi**: la primera vez que entres a cada sistema baja su lista desde GitHub (luego queda guardada). Si te falta alguna lista, **SELECT → Actualizar listas**.
3. Controles:

| Botón | Acción |
|---|---|
| **X** | Descarga el juego (si falta) y lo abre en su emulador, ya cargado |
| **Cuadrado** | **Buscar** un juego por nombre (teclado en pantalla) |
| **Cuadrado (mantener ~1 s)** | Añadir/quitar el juego de **★ Favoritos** |
| **Triángulo** | Recargar la lista del sistema |
| **Triángulo (mantener ~1 s)** | **Borrar** el juego de la consola |
| **Arriba/Abajo** | Mover por la lista · **Izq/Der** = saltar 10 |
| **L / R** | Cambiar de sistema (consola) |
| **SELECT** | **Menú**: sistemas, buscar, favoritos, descargados, ajustes y prueba de red |
| **START** | Mostrar/ocultar la ayuda |
| **O** | Salir (o cancelar una descarga en curso) |

> 🆕 **v2.4 — PSP y Dreamcast + auto-config**: los sistemas nuevos salen en el menú (iconos oficiales). Al pulsar X en un juego **PSP** se baja a `ux0:/pspemu/ISO/` y — con el extra "1 toque" — **arranca directo**; sin el extra se abre Adrenaline para elegirlo. Los juegos de **Dreamcast** arrancan directos con Flycast. Y el launcher **se auto-configura** (bezels+shaders) la primera vez.

> 🆕 **v2.3 — descargas a prueba de balas**: descargas **por trozos**: progreso en vivo, **cancelar con O** (se conserva lo bajado) y **reanudar** donde iba al reintentar. Pantalla **Descargados** (míralo con su tamaño y borra). Al abrir un juego, RetroXam **se cierra solo**. Burbuja/fondo con la seta 1-UP 🍄.

4. Leyenda: **`+`** = ya en la Vita · **`-`** = pendiente · **`★`** = favorito · **`ES`** = versión en español · punto de color = WiFi. Arriba: reloj, batería y espacio libre.
5. **Carátulas**: el panel derecho muestra la portada del juego (se descarga sola con WiFi). ¿Todas de golpe? Descomprime `RetroXamVita_Covers.zip` en `ux0:/data/retroxam/`.
6. **Descargas robustas**: primero el **PUENTE del PC/Mac**, luego http/https directos. ¿Algo falla? Menú → **START** = prueba de red; **Ajustes → Ver registro** (`ux0:/data/retroxam/retroxam.log`).
7. Los juegos se guardan en `ux0:/data/retroxam/roms/<sistema>/` (los de PSP, en `ux0:/pspemu/ISO/`). Los multi-disco crean su `.m3u` solos (y el aviso te dice cuántos discos son).
8. **Sistemas incluidos (18)**: NES · SNES · GB · GBC · GBA · N64 · Mega Drive · Mega CD · 32X · PSX · Neo Geo · CPS-1 · CPS-2 · CPS-3 · FBNeo · OpenBOR · **PSP** · **Dreamcast** (~2.200 juegos).

---

## 🎮 PARTE 7 — PSP (Adrenaline: NATIVO)

La Vita lleva el chip de PSP dentro: Adrenaline lo usa directamente. Compatibilidad prácticamente total.

1. Si no lo has hecho: abre **Adrenaline** una vez → **X** (baja el firmware solo, ~1 min). *(Plan B sin internet: copia `661.PBP` a `ux0:/app/PSPEMUCFW/661.PBP` y abre Adrenaline.)*
2. En **RetroXam → PSP**: elige un juego → X. Se descarga a `ux0:/pspemu/ISO/` solo.
3. **Abrir directo ("1 toque", opcional)**: sigue `PSP_1toque\LEEME` (instala AdrenalineBubbleManager — pone los módulos sola — e instala `AdrenalineLauncher.vpk`). Con eso, X en RetroXam abre el juego **directo, sin menús**.
4. Sin el extra: RetroXam abre **Adrenaline** y eliges el juego en **Game → Memory Stick** (están todos en `ux0:/pspemu/ISO/`).
5. A mano también puedes copiar tus propios `.iso`/`.cso` a `ux0:/pspemu/ISO/`.

> Los juegos PSP pesan ~1,5 GB de media y son **216 GB** la lista completa: baja solo los que quieras (el launcher te avisa del tamaño).

---

## 🕹️ PARTE 8 — Dreamcast (Flycast, experimental)

1. En **RetroXam → Dreamcast**: elige un juego → X. Se descarga y **arranca directo** con Flycast.
2. La lista incluye **solo los juegos compatibles** con Flycast Vita (79, con nivel documentado: 32 fluidos / 43 jugables / 4 justos).
3. Los multidisco (Resident Evil CV, Skies of Arcadia) bajan todos los discos y crean su `.m3u`.
4. Es **experimental** en la Vita (~50%): empieza por los 2D, fighting y carreras ligeras. Si un juego va con tirones, no es tu Vita — es el emulador.

> 🔧 Flycast necesita **kubridge + fd_fix**: el instalador los deja configurados solos. Si algún día ves el error *"kubridge.skprx is outdated"*, pasa otra vez el instalador (pone la versión buena) y reinicia.

---

## 🛰️ Usar RetroXam FUERA de casa (y compartirlo)

- **Los puentes de tu casa** (`192.168.2.…`) solo existen en tu red local: fuera **no se ven, y es normal**.
- Fuera quedan dos vías: el **acceso público del Mac** (`https://servi.tail31979d.ts.net:10000`, ya viene dentro de la app) — necesita el **Mac encendido** — y **archive.org directo** (solo si ese WiFi no lo bloquea; muchos proveedores españoles lo capan los findes de partido).
- **v3.5**: al empezar una descarga, el launcher **prueba los espejos y salta los que no responden** (la primera descarga tarda unos segundos más; después va directo a lo que funciona).
- **Para compartir**: el acceso público va dentro del pack → **otra Vita solo tiene que instalar y jugar**. (También puede poner su propio puente en **Ajustes → Puente**.)
- Truco: desde el móvil abre `https://servi.tail31979d.ts.net:10000/ping` → si responde, la puerta pública está abierta.

---

## 🔌 El PUENTE por PC (para redes que bloquean archive.org)

Tu red puede no dejar a la Vita conectar con archive.org (es lo que te pasaba). El **puente** lo resuelve: la Vita le pide el juego a tu **PC/Mac**, y él (que sí llega) hace de espejo.

- **Ya está montado y es automático**: el launcher prueba en orden el **Mac Mini** (siempre encendido), el **PC** y el **acceso público** del Mac. No hay que configurar nada.
- **Requisito**: que el Mac o el PC estén encendidos.
- Solo si quieres **cambiarlo**: **Ajustes → Puentes del PC/Mac**, o el archivo `ux0:/data/retroxam/puente.txt`.
- Comprobar: **SELECT → START** → debe poner `PC OK`.
- Registros: PC `C:\Users\XAM-PC\RetroXamTools\puente.log` · Mac `~/RetroXam/puente.log`.

---

## 💻 PARTE 9 — Descargar en masa desde el PC (opcional)

> Para lotes grandes (50 de PSX, toda la SNES…). Herramientas en `C:\Users\XAM-PC\RetroXamTools`.

```bat
cd C:\Users\XAM-PC\RetroXamTools

:: Bajar (reanudable; --flat deja los archivos planos, como los quiere el launcher)
python descargar_vita.py --repo https://github.com/servixam-max/RetroXamVita --out D:\VitaROMs --flat --systems nes,snes,megadrive,psp,dreamcast

:: Subirlas a la Vita directo por FTP (VitaShell en modo FTP; IP en su pantalla, puerto 1337)
python descargar_vita.py --repo https://github.com/servixam-max/RetroXamVita --out D:\VitaROMs --flat --ftp 192.168.1.50:1337 --ftp-dir /ux0:/data/retroxam/roms
```

- Si lo vuelves a lanzar, **salta lo ya descargado/subido**. Con `--limit 20` bajas solo 20 por sistema.

**Tamaños orientativos:**

| Sistema | Juegos | Peso | Sistema | Juegos | Peso |
|---|---|---|---|---|---|
| NES | 239 | 30 MB | CPS-1 | 38 | 82 MB |
| SNES | 239 | 364 MB | CPS-2 | 41 | 549 MB |
| GB | 96 | 21 MB | CPS-3 | 6 | 278 MB |
| GBC | 53 | 73 MB | FBNeo | 220 | 1,0 GB |
| GBA | 89 | 3,7 GB | Neo Geo | 110 | 2,0 GB |
| N64 | 119 | 1,8 GB | PSX | 238 | 86,7 GB |
| Mega Drive | 186 | 168 MB | Mega CD | 43 | 9,7 GB |
| 32X | 38 | 119 MB | OpenBOR | 120 | 17,1 GB |
| **PSP** | **225** | **~217 GB** | **Dreamcast** | **79** | **~35 GB** |

> Total retro ≈ **124 GB** — no hace falta todo. Gracias al `--flat`, el launcher las marcará como **`+`** y las abrirá al instante.

---

## ✨ PARTE 10 — Toques finales

- **RetroArch**: no hace falta tocar nada — el launcher le pasa el core correcto y los ajustes se guardan solos. *(Tu config de bezels/shaders la mantiene la v2.4 sola.)*
- **DaedalusX64**: no todos los juegos de N64 van finos en la Vita (es normal). También puedes meter ROMs a mano en `ux0:/data/DaedalusX64/roms/`.
- **OpenBOR**: los `.pak` se copian solos a `ux0:/data/openbor/paks/`.
- **Mandos**: la Vita usa sus controles; en RetroArch puedes reasignar en Settings → Input.

---

## 🛍️ EXTRA — PSVitaAlive (la tienda de homebrew)

- **Qué es**: un catálogo abierto de homebrew para la Vita ("Keep PlayStation Vita Alive") — descubres e instalas apps desde la propia consola. Se **actualiza sola**.
- **Instalarla**: `PSVitaAlive.vpk` (X → Install). Es opcional pero muy chula.
- **Necesita internet moderno**: instala también **iTLS-Enso.vpk** (el instalador ya lo sube) y reinicia. Sin él, el catálogo puede no cargar.

---

## 🧾 Resumen: qué emulador usa cada sistema

| Sistema | Emulador | Core |
|---|---|---|
| NES | RetroArch | fceumm |
| SNES | RetroArch | snes9x2005_plus |
| GB / GBC | RetroArch | gambatte |
| GBA | RetroArch | gpsp |
| Mega Drive / Mega CD | RetroArch | genesis_plus_gx |
| 32X | RetroArch | picodrive |
| PSX | RetroArch | pcsx_rearmed |
| Neo Geo | RetroArch | fbneo |
| CPS-1 / CPS-2 | RetroArch | mame2003_plus |
| CPS-3 / FBNeo | RetroArch | fbneo |
| N64 | DaedalusX64 | — |
| OpenBOR | OpenBOR | — |
| **PSP** | **Adrenaline** (nativo) | — |
| **Dreamcast** | **Flycast** (experimental) | — |

---

## 🔧 Problemas típicos

| Problema | Solución |
|---|---|
| "No hay juegos cargados" | Sin WiFi o listas sin bajar: activa WiFi y **SELECT → Actualizar listas** |
| Un juego no arranca | Bórralo de su carpeta (mantén **Triángulo** en el launcher) y vuelve a descargarlo |
| Sin espacio | El launcher muestra el libre arriba; borra juegos o pon una microSD mayor |
| La burbuja no aparece | VitaShell → **△ → Refresh livearea** |
| Las descargas fallan | Que el Mac o el PC estén encendidos y SELECT → START diga `PC OK`. Diagnóstico: **Ajustes → Ver registro** |
| **Instalador USB**: ¿está haciendo algo? | Ahora muestra progreso (bloques y MB). Si en una 2ª pasada todo dice `+0 copiados, ya estaban` = ya está todo ✓. El "pulsa una tecla" final es solo cerrar |
| **USB**: la Vita no aparece como unidad | VitaShell → START → SELECT = **USB** → O → SELECT, cable de datos, y espera; si no, usa la vía **FTP** |
| Sale la imagen **desplazada** de su marco (le pasa a veces a algún core, p. ej. NES) | **Lo más rápido**: cierra RetroArch (botón PS → cierra su tarjeta) y reabre el juego desde RetroXam → vuelve centrado. **A mano**: con el juego abierto pulsa **L + R + START + SELECT** a la vez (menú) → **Ajustes → Vídeo → Escalado** → "Relación de aspecto: **Personalizada**" → pon los números de su sistema (Parte 4) → Quick Menu → Overrides → **Save Core Override**. **Reparar la config sin PC**: en VitaShell borra `ux0:/data/retroarch/retroxam_cfg_ver.txt` y abre RetroXam (verás "Instalando config RetroXam…") |
| **PSP**: no arranca directo desde RetroXam | Es lo normal sin el extra: se abre Adrenaline y eliges el juego. Para el "1 toque": instala el extra de `PSP_1toque\LEEME` |
| **PSP**: un juego no aparece en Adrenaline | Debe estar en `ux0:/pspemu/ISO/` (el launcher lo pone ahí solo). Refresca con O → volver a entrar |
| **Flycast**: "kubridge.skprx is outdated" | Pasa otra vez el instalador (pone la versión correcta) y **reinicia** la consola |
| **PSVitaAlive** no carga el catálogo | Instala **iTLS-Enso.vpk** (kit) y reinicia |
| Los **shaders** no se notan | El pack pone el driver `gl` solo (v3.5): tras instalar, abre RetroXam una vez (aplica el ajuste) y reinicia RetroArch. Necesita PIBConfig + ShaRKBR33D hechos (una vez). |
| ¿Quieres los **bezels (marcos)** de vuelta? | En la v3.5 vienen desactivados de serie. Pídemelo, o cambia `input_overlay_enable` a `true` en los `config/<Core>/<Core>.cfg` y reinicia RetroArch |
| **Sigo viendo los bezels** tras actualizar | Abre RetroXam una vez (instala la config sola) o pasa el PASO 2; después cierra y reabre RetroArch |
| Quiero otro tema o textos más grandes | **SELECT → Ajustes** → Tema / Texto (se guarda solo) |
| Quiero borrar juegos para hacer sitio | Mantén **Triángulo** sobre el juego y confirma con **X** |
| Error **0x8010113D** al instalar la VPK | Usa las VPKs actualizadas del kit (iconos 128×128 8-bit ya corregidos) |
| El launcher no ve la SD | Repasa la Parte 1 (YAMT + ux0 → SD2Vita + reinicio) |
| **Daedalus** da error **C2-12828-1** | Falta `libshacccg.suprx`: ejecuta **ShaRKBR33D** (kit), reinicia y comprueba `ur0:/data/libshacccg.suprx`. Comprueba también `ux0:/data/DaedalusX64/` |
| RetroArch no muestra **Shaders** en el menú | Es normal: la build estándar no los trae. La build **piglet** (carpeta 4 - Extras) sí — con PIBConfig + ShaRKBR33D |
| Un juego sale **sin marco** (bezel) | Es lo normal desde la v3.5 (marcos desactivados de fábrica). ¿Los quieres de vuelta? Mira el EXTRA 2 |

---

## 🖼️ EXTRA 2 — Bezels estilo RetroXam (opcional — la v3.5 los desactiva de serie)

Los marcos con el logo de cada consola y la seta 🍄 **se instalan solos con la v2.4**. Referencia:

- **Archivo**: `Config_RetroXam_Piglet.zip` (o `Bezels_RetroXam_Vita.zip` solo-marcos) → **X → Extract** en `ux0:/data/retroarch/`.
- Cobertura: NES, SNES, GB/GBC, GBA, Mega Drive/Mega CD, 32X, PSX, NeoGeo/Arcade y CPS-1/2. N64 (Daedalus) y OpenBOR no pasan por RetroArch: sin marco.
- ¿A mano? Con un juego abierto: RetroArch → Ajustes → Pantalla en pantalla → Overlay Preset → `retroxam/<sistema>.cfg` → Quick Menu → Overrides → **Save Core Override**.
- Vita 1000 (OLED): el arte es oscuro y estático; con brillo alto horas y horas podría quedar marca (mismo aviso que otros packs).

---

## 🌈 EXTRA 3 — Shaders (scanlines CRT / LCD) — referencia

- **La build piglet** (carpeta 4 - Extras) + `PIBConfig` + `ShaRKBR33D` = menú **Shaders** activo dentro de RetroArch.
- **El pack lo deja TODO listo** (v3.5): el driver `gl`, la carpeta de shaders y los presets por core se configuran **solos** al instalar / abrir RetroXam.
- **A mano**: **Quick Menu → Shaders → Load Shader Preset** → `crt/crt-pi.glslp` (TV) o `lcd/lcd3x.glslp` (Game Boy). Los pesados (crt-geom) van lentos: quédate con `crt-pi`, `lcd3x` o `sharp-bilinear-simple`. Fija el que te guste con **Save Core Override**.
- **La v2.4 ya deja elegidos los mejores por core** (CRT para consolas de TV, LCD para GB/GBC, nitidez para GBA). No hay que tocar nada.

---

*MANUAL - RetroXam Vita — launcher v3.5 · 18 sistemas · ~2.200 juegos · RetroArch (estándar) + DaedalusX64 + OpenBOR + Adrenaline + Flycast + PSVitaAlive*
*Listas: `github.com/servixam-max/RetroXamVita` · Carátulas: `github.com/servixam-max/RetroXamVitaCovers`*
