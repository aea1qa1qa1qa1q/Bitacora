# Bitácora del día

Rutina diaria organizada por bloques (mañana, día, tarde, noche) con racha, historial, notas y estadísticas. Es una PWA de un solo archivo: se instala en el móvil desde el navegador y funciona sin conexión. Todo se guarda en el dispositivo (`localStorage`).

## Cómo se usa

- **Marcar**: toca una actividad (o usa Espacio/Enter con el teclado).
- **⏭ Posponer**: mueve la actividad una hora (o al siguiente bloque) **solo por hoy**; tu rutina no cambia.
- **+ Surgió algo**: agrega un *imprevisto* que solo existe hoy y desaparece mañana (si lo hiciste, queda en el historial).
- **✎ Editar**: muestra las actividades de toda la semana para agregarlas, editarlas, reordenarlas o borrarlas.
- **Tipos**: *Normal*, *Protegida* (tiempo reservado, no se marca) e *Imprevisto*. Además pueden ser *Críticas* o *Side quest* (no cuentan en tu contra).
- **Historial**: últimos 7 días, mes y año. Toca un día para ver qué hiciste y tu nota.
- **Menú ☰**: estadísticas, historial por actividad, exportar CSV, backup/restaurar JSON y preferencias.

Las acciones que borran algo (eliminar, reiniciar el día, posponer…) se pueden **deshacer** desde el aviso que aparece abajo.

### Preferencias

- Sonido y vibración al marcar.
- Mensaje al completar el día (frase motivadora, dato curioso o chiste).
- **La madrugada cuenta como el día anterior**: el día cambia a las 5:00 am en lugar de a medianoche, para quienes se duermen tarde.

## Reglas de la racha

Un día cuenta como completo cuando marcas todas las actividades programadas para ese día (sin contar las protegidas ni las side quests). La racha sube al completar el día y se pierde si un día queda sin completar. Si desmarcas algo después de completar el día, la racha de hoy se descuenta.

## Publicarla

Sirve la carpeta en cualquier hosting estático con HTTPS (por ejemplo GitHub Pages). El service worker (`sw.js`) guarda la app en caché para usarla sin conexión y busca actualizaciones cada vez que la abres con internet.

## Archivos

| Archivo | Para qué sirve |
| --- | --- |
| `index.html` | Toda la app (HTML, CSS y JS) |
| `sw.js` | Service worker para uso sin conexión |
| `manifest.json` | Datos para instalarla como app |
| `icon-192.png`, `icon-512.png` | Íconos |
