# Ejercicio 3: Tarjeta de producto y caja con scroll

## Parte A: Etiqueta sobre la tarjeta
- La tarjeta tiene 300 px de ancho, borde, esquinas redondeadas y padding.
- La etiqueta `-20%` usa `position: absolute` y sobresale 10 px por arriba y por la derecha.
- La tarjeta necesita `position: relative` para que la etiqueta se coloque respecto a ella.
- Con `overflow: hidden`, la parte de la etiqueta que queda fuera de los límites de la tarjeta se recorta.
- Para conservar la etiqueta completa, se puede dejar `overflow: visible` en la tarjeta. Si se necesita recortar el contenido interno, se puede poner ese contenido dentro de otro elemento con `overflow: hidden`, sin recortar la etiqueta.

## Parte B: Caja de comentarios
La caja mide 300 × 120 px y tiene más comentarios de los que caben.

- **`overflow: visible`:** el contenido que no cabe se muestra fuera de la caja.
- **`overflow: hidden`:** el contenido que sobresale queda recortado y no se muestra.
- **`overflow: scroll`:** aparecen barras de desplazamiento para poder recorrer el contenido.
- **`overflow: auto`:** el navegador añade barras de desplazamiento cuando son necesarias.

La caja queda configurada con `overflow: auto`, como bien se pedía.

## Parte C: `visibility: hidden` y `display: none`
- **`visibility: hidden`:** el elemento no se ve, pero conserva el espacio que ocupa en el diseño.
- **`display: none`:** el elemento no se muestra y tampoco reserva espacio en el diseño.
