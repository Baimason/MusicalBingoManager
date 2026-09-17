# Bingo Musical

Herramienta web para armar y manejar bingos musicales: carga una lista de canciones, reproduce una playlist de YouTube Music, canta canciones al azar llevando el control de cuáles ya salieron, y genera los cartones en PDF listos para imprimir con tu propio diseño.

Es un solo archivo (`bingo_control.html`), no necesita instalación ni backend, corre entera en el navegador.

## Uso

Abrí [La URL de GitHub Pages de este repo)](https://baimason.github.io/MusicalBingoManager/) y desde el botón **Configuración**:

1. Pegá tu lista de canciones, una por línea, en formato `Artista - Título`.
2. Pegá el link de tu playlist de YouTube Music (tiene que estar en visibilidad **No listado**, y el orden de las canciones ahí tiene que coincidir con el de la lista pegada arriba).

Con eso ya podés usar **Cantar canción aleatoria** para jugar, el tablero marca solas las que van saliendo y el progreso queda guardado en el navegador.

## Generar los cartones para imprimir

Desde el botón **Generar cartones**:

1. Si todavía no tenés una plantilla diseñada, descargá la **plantilla guía** de referencia, marca dónde va cada una de las 25 celdas.
2. Diseñá tu cartón (en Photopea, Figma, lo que uses) respetando esa guía, y exportalo como PNG sin texto en las celdas.
3. Subí esa plantilla, opcionalmente imágenes para el centro de cada cartón, elegí cuántos cartones y cuántos por hoja.
4. Generar PDF arma el archivo listo para imprimir, con las canciones y números sacados de la lista configurada.

## Notas técnicas

- El reproductor usa la YouTube IFrame API, por eso necesita servirse desde una dirección http (GitHub Pages, o `python3 -m http.server` en local), abrir el archivo directo (`file://`) tira un Error 153.
- Todo el estado (lista de canciones, playlist, progreso) se guarda en `localStorage` del navegador, no hay servidor ni base de datos.
- Pensada para pantalla grande o proyector durante el evento, no está optimizada para celular.
