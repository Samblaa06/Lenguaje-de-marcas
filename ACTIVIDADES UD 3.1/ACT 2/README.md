# Ejercicio 2: Menú que se queda fijo

## Qué contiene:
- Un banner inicial con título y párrafo.
- Un menú con cuatro enlaces a secciones mediante anclas.
- Cuatro secciones con texto suficiente para hacer scroll.
- Un enlace `↑ Subir` fijo en la esquina inferior derecha.

## Observaciones:

- **`position: sticky`:** el menú ocupa su lugar normal al principio. Cuando al desplazarse llega al límite indicado por `top: 0`, se queda pegado arriba dentro de los límites de su contenedor.
- **`position: fixed`:** el menú se posiciona respecto a la ventana del navegador y sale del flujo normal. El contenido que iba debajo puede quedar detrás del menú porque ya no se reserva su espacio.
- **`z-index`:** hace que el menú quede por encima del texto que pasa por debajo.
- **`scroll-behavior: smooth`:** hace que los saltos a las secciones y al inicio sean suaves.

## Prueba
Cambia `position: sticky` por `position: fixed` en `.menu`. Observa que el menú deja de reservar espacio y puede tapar parte del contenido. Después vuelve a `sticky`.

## Si `sticky` no funciona
Comprueba que existe `top: 0` y que ningún elemento padre limita el desplazamiento con `overflow: hidden` o `overflow: auto`.
