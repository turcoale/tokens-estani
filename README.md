# Tokens de Estani

Temporizador de pantalla con tokens reutilizables de 15, 30 y 60 minutos. Sin servidor, dependencias ni instalación.

## Publicar en GitHub Pages

1. Subir el contenido de esta carpeta a la raíz de un repositorio.
2. En Settings → Pages, seleccionar Deploy from a branch, rama main y carpeta / (root).
3. Usar la dirección que indique GitHub Pages.

Los cuatro accesos directos son:

- https://USUARIO.github.io/REPOSITORIO/1/ (prueba de 1 minuto)
- https://USUARIO.github.io/REPOSITORIO/15/
- https://USUARIO.github.io/REPOSITORIO/30/
- https://USUARIO.github.io/REPOSITORIO/60/

Cada enlace se puede convertir en un QR reutilizable. Escanearlo prepara el token; tocar Empezar activa el reloj y el sonido. También se admite ?token=1, ?token=15, ?token=30 o ?token=60. No hay API ni backend: son cuatro páginas estáticas compatibles con GitHub Pages.

## Funcionamiento

El contador usa una hora de finalización y conserva el token en el navegador al recargar, si localStorage está disponible. Un token activo tiene prioridad sobre un enlace de otro tiempo, para evitar reiniciarlo accidentalmente. No se sincroniza entre dispositivos ni controla otras aplicaciones. Terminar antes pide confirmación. Al finalizar, la alarma repite pitidos hasta tocar Listo, terminé. No se controla si alguien copia un QR o reutiliza un token.

## Prueba en el dispositivo real

Probar el sonido y el volumen antes del uso. Dejar la página abierta. Se solicita mantener la pantalla encendida si el navegador permite Wake Lock. Al volver de otra aplicación, el contador se actualiza según la hora de finalización. El sistema puede suspender JavaScript o el audio cuando la página pasa a segundo plano o el dispositivo se bloquea; por eso la alarma NO está garantizada en esas condiciones. Tras recargar, tocar Probar el sonido para reactivarlo. Para medir tiempo mientras Estani usa otro dispositivo, dejar el temporizador visible en un teléfono aparte.

## Archivos

index.html es la fuente autocontenida; 1/index.html, 15/index.html, 30/index.html y 60/index.html son copias de esa fuente para los accesos directos. Si se modifica la fuente, copiarla de nuevo a las cuatro carpetas. No hace falta compilar. El cuarto token de 1 minuto está disponible también en la versión para publicar. La alarma usa cuatro pitidos alternados, más fuertes y sostenidos, y se repite hasta confirmarla.

## Contraste

Los cuatro tokens usan texto oscuro explícito, fondos diferenciados y contraste calculado superior a 7:1. Los tokens deshabilitados conservan su opacidad para mantener la legibilidad. La selección incluye un tilde además del borde. Prueba real reportada por el usuario: funciona en segundo plano en su celular, pero la alarma no suena con pantalla bloqueada. No se garantiza el funcionamiento en segundo plano en otros navegadores o dispositivos.
