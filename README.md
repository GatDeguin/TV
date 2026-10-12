# Springfield · La televisión de casa

Diorama 3D interactivo inspirado en la sala y el comedor de Los Simpson, con TV CRT violeta y reproductor de archivos locales.

## Uso

Abrí `index.html` en un navegador con JavaScript y WebGL2 habilitados. El archivo contiene el programa completo, sin dependencias, CDN, modelos, fuentes ni servicios externos. También puede servirse como sitio estático.

Tocá la pantalla para acercarte y elegí **CARGAR VIDEOS**, o presioná **VHS** en el control remoto. Cada video seleccionado se convierte en un canal. Los archivos permanecen en tu dispositivo.

**No incluye capítulos comerciales, enlaces de descarga ni integración con plataformas de streaming.** El canal 00 contiene una señal original de prueba, identificada como tal. Para ver capítulos, seleccioná tus propios archivos.

## Controles

- Arrastrar: girar la cámara. Rueda o pellizco: acercar o alejar.
- `V`: sala / TV. `R`: control remoto. `L`: cargar videos. `H`: ayuda.
- Espacio: reproducir / pausar. `P`: encender / apagar. `M`: silencio.
- Flechas izquierda / derecha: retroceder / avanzar 10 segundos. Arriba / abajo: volumen.
- PageUp / PageDown: canales. `N`: noche. `C`: efecto CRT. `F`: pantalla completa cuando esté disponible.
- Escape: cerrar menú o volver a la sala. Shift invierte la acción de las perillas.

Los controles visuales están modelados dentro de la escena. Hay controles semánticos adicionales para lectores de pantalla y un selector nativo de archivos. El menú del CRT incluye videoteca, subtítulos SRT/VTT, lámpara, noche, calidad, movimiento reducido, encuadre, captura PNG y expulsión de cinta.

## Video y almacenamiento

Selector para MP4, M4V, WebM, OGV y MOV: la compatibilidad real depende del códec admitido por el navegador. Probado con MP4 H.264 y AAC. Si no comienza, tocá PLAY. Hasta 100 videos por sesión; subtítulos hasta 2 MB. Al cambiar de canal, seleccioná sus subtítulos.

La lista de archivos no se conserva al recargar: hay que seleccionarlos de nuevo. Preferencias y posiciones de reproducción se guardan localmente cuando el navegador permite localStorage. No hay seguimiento, telemetría ni subida de videos.

## Implementación y verificación

Motor WebGL2 propio, geometrías y texturas procedimentales, sombreado aproximado de materiales, sombras PCF, vidrio CRT curvo, líneas de barrido e iluminación de ambiente y TV. 138.852 triángulos y 37 objetivos interactivos. Es una recreación con aspecto de maqueta: no utiliza fotogrametría ni path tracing y no se afirma equivalencia con una fotografía.

Verificación local: siete pruebas unitarias y 28 comprobaciones funcionales aprobadas, incluyendo reproducción MP4, textura de video, pausa, volumen, canales, subtítulos, clics en controles 3D y menú CRT, manejo de archivos inválidos y redimensionamiento vertical. Cero errores JavaScript no capturados y cero solicitudes HTTP/HTTPS durante la prueba.

Entorno: Chromium, SwiftShader y Xvfb. El HTML se inyectó en un documento por restricciones de navegación del entorno; no se verificó allí la apertura mediante file://. No se probaron Safari/iOS, teléfonos físicos, pantalla completa, captura PNG ni recuperación de contexto WebGL. No se garantiza una tasa de FPS.

El código está completo y sin ofuscar dentro de `index.html`. La creación del repositorio no implica que GitHub Pages esté activado.

Proyecto independiente, no afiliado a los titulares de Los Simpson. Los nombres y referencias pertenecen a sus respectivos titulares.
