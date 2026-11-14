# 🎵 NowPlaying

Mostrá en tu stream (o flotando en tu pantalla) la canción que estás escuchando. Funciona con Spotify, SoundCloud, YouTube Music, Apple Music, Deezer, VLC y cualquier app o navegador que muestre los controles de música de Windows.

**Generador de overlays:** https://musica.zorginta.workers.dev

---

## ¿Cómo funciona?

Son dos partes:

1. **Now Playing Bridge** (el programa): corre en tu PC, lee lo que está sonando y lo ofrece solo para vos, en tu propia computadora.
2. **El generador** (la página web): ahí elegís cómo se ve tu overlay y copiás la URL para ponerla en OBS, o lo activás como superposición en pantalla.

Todo pasa en tu PC. No se sube nada a ningún servidor y no hace falta crear una cuenta.

---

## 🚀 Instalación (3 pasos)

1. **Descargá** el `.zip` de la última versión desde [Releases](https://github.com/Zorginta/NowPlaying/releases/latest), descomprimilo y abrí `NowPlayingBridge.exe`.
2. Si Windows muestra **"Windows protegió su PC"**: tocá **"Más información"** y después **"Ejecutar de todas formas"**. Aparece porque el programa no está firmado digitalmente (firmar cuesta dinero), no porque tenga algo malo. El código está abierto en este repositorio para que lo revises.
3. Aparece un ícono verde cerca del reloj. Hacé clic derecho → **"Abrir el generador de overlays"**.

> Si el navegador pregunta por acceso a la red local, tocá **"Permitir"**.

Por defecto el programa se inicia solo con Windows (se puede apagar desde el menú del ícono).

---

## ✨ Qué incluye

- **11 estilos** de overlay (Compact, Standard, Classic, Card, Matte, Burbuja estilo Discord, Vinilo giratorio, Ondas, etc.).
- **Colores automáticos** sacados de la carátula de cada canción, o colores personalizados.
- **Fuentes** a elección: Google Fonts o cualquiera que tengas instalada en Windows.
- **Filtro por aplicación**: incluí solo ciertas apps o excluí otras (por ejemplo `chrome.exe`, `brave.exe`).
- **Visualizer de audio real** (opcional): barras, LED, espejo u onda. Podés elegir qué salida de audio escuchar (útil con SteelSeries Sonar o mezcladores virtuales). Si no lo activás, no consume nada.
- **Animaciones** de entrada y salida, y opción de mostrarlo solo al cambiar de canción.
- **Superposición en pantalla (experimental)**: mostrá el overlay flotando sobre tu pantalla, sin necesitar OBS.

---

## 🎥 Usarlo en OBS

1. Armá tu overlay en el generador.
2. Copiá la **URL de tu overlay**.
3. En OBS: **Fuentes → + → Navegador** → pegá la URL y poné el ancho y alto que indica el generador.

El overlay se muestra solo cuando hay música sonando.

---

## 🖥️ Superposición en pantalla (sin OBS) — experimental

En el generador, tarjeta **"Superposición en pantalla"**: elegí posición, distancia a los bordes, tamaño y si querés que aparezca solo al cambiar de canción. Después tocá **"Mostrar superposición"**. También se enciende y apaga desde el menú del ícono.

- Necesita **WebView2 Runtime** de Microsoft (viene con Windows 11 y con Edge en Windows 10).
- No se ve sobre juegos en **pantalla completa exclusiva**. Usá modo ventana o ventana sin bordes.
- Es una función nueva: si algo se ve raro, avisá abriendo un [Issue](https://github.com/Zorginta/NowPlaying/issues).

---

## 📋 Requisitos

- Windows 10 (versión 1809 o más nueva) o Windows 11, 64 bits.
- No hace falta instalar .NET: el programa ya lo trae incluido.

---

## 🔒 Privacidad y seguridad

- El programa solo escucha en tu propia PC (`127.0.0.1`, puerto `5757`), no está abierto a internet.
- Solo responde a la página del generador, para que otras webs no puedan ver qué escuchás.
- El visualizer solo captura audio mientras alguien lo pide y se apaga solo a los pocos segundos.

---

## 🛠️ Compilarlo vos mismo

1. Instalá el **SDK de .NET** (no el Runtime) desde https://dotnet.microsoft.com/download
2. Abrí `build.bat` (hace falta internet la primera vez).
3. El programa queda en la carpeta `dist`.

---

## ❓ Problemas comunes

| Problema | Solución |
|---|---|
| El generador dice "No detecto la app" | Abrí `NowPlayingBridge.exe` y permití el acceso a la red local en el navegador. |
| El puerto 5757 está ocupado | Cerrá el otro programa que lo usa y abrí el Bridge de nuevo. |
| El visualizer no muestra nada | Elegí en el generador la salida de audio por donde suena tu música. |
| Aparece la música de un navegador que no quiero | Usá "Excluir estas apps" (por ejemplo `chrome.exe`). |

---

Hecho con cariño por [Zorginta](https://github.com/Zorginta) 💚
