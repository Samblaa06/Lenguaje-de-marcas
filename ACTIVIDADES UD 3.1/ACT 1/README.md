# Ejercicio 1: Laboratorio de position

## Qué contiene:
- `index.html`: estructura de los tres cuadros.
- `estilos.css`: estilos y ejemplos de `position` y `z-index`.

## Observaciones:

- **Base:** el contenedor tiene un borde y 300 px de ancho. Los cuadros miden 100 × 100 px, tienen un margen inferior de 10 px y colores distintos.
- **`static`:** es el valor predeterminado. Si añado `left: 50px` a un elemento con `position: static`, no se desplaza porque las propiedades `top`, `right`, `bottom` y `left` no actúan sobre elementos estáticos.
- **`relative`:** con `position: relative`, `top: 20px` y `left: 50px`, el cuadro se desplaza desde su posición original, pero conserva el espacio que ocupaba en el flujo normal.
- **`absolute`:** el cuadro sale del flujo normal y se coloca usando las coordenadas indicadas. Si el contenedor tiene `position: relative`, se coloca respecto a ese contenedor; si no, busca otro ancestro posicionado o usa el bloque contenedor inicial.
- **Hueco de `absolute`:** los demás elementos se distribuyen como si el cuadro absoluto no estuviera ahí, porque no reserva espacio en el flujo normal.
- **`z-index`:** permite controlar qué elemento queda por delante cuando se solapan. En este ejemplo, `c1` tiene un `z-index` mayor que `c2`, por lo que aparece por encima.
