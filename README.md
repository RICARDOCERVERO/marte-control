# Centro de control de Marte

Web en HTML y CSS para supervisar una misión a Marte. Incluye cabecera, imagen y cuatro indicadores: oxígeno, energía, temperatura y progreso. Hay un selector de tema claro y oscuro y un botón que simula nuevas lecturas.

## Modo educativo
Una barra inferior muestra en vivo el ancho de la ventana, la vista (móvil, tablet o escritorio), el número de columnas y el ancho de una tarjeta. El botón "Ver rejilla" dibuja los límites del Grid. Se puede ocultar todo con "Modo educativo".

## Archivos
- `index.html`: estructura y un script pequeño para el tema y los botones.
- `style.css`: estilos con CSS Grid y unidades relativas.
- `marte.svg`: imagen original dibujada en SVG.

## Unidades justificadas

### `rem` (escala de tipografía y espacios)
Todos los tamaños de texto y los huecos (`gap`, anchos mínimos) usan `rem`. Dependen del tamaño de letra base del navegador, así que si la persona usuaria amplía el texto por accesibilidad, la interfaz crece de forma coherente. Con `px` no ocurriría.

### `fr` (columnas flexibles con CSS Grid)
Los indicadores usan `repeat(auto-fit, minmax(14rem, 1fr))`. Cada tarjeta mide al menos `14rem` y `fr` reparte el espacio sobrante a partes iguales. El número de columnas se adapta solo, sin media queries para las tarjetas.

### Otras unidades usadas
- `%`: ancho del contenedor (`94%`) y de las barras de progreso.
- `em`: `padding` de tarjetas y botones, que escala con su propio texto.

## Validación

| Ancho | Resultado |
|-------|-----------|
| 360 px | Una columna, cabecera apilada, botón a todo el ancho. Sin scroll horizontal. |
| 1200 px | Cuatro tarjetas en una fila, contenedor centrado. Sin scroll horizontal. |

**¿Qué cambia y por qué?** El `grid` pasa de 4 columnas a 1 porque `minmax(14rem, 1fr)` no cabe más de una vez en 360 px. La clave: la interfaz se reorganiza sin perder claridad.

## Cómo probar
Abrir `index.html` en el navegador y redimensionar la ventana (F12 → modo dispositivo → 360 px y 1200 px).
