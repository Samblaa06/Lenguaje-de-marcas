# UD 2.4 · Ejercicio: Construir con `<div>`, margin, padding y display

Práctica centrada en el modelo de caja, flujo de elementos y propiedades de visualización (`block`, `inline`, `inline-block`, `flex` y `none`).

---

## Decisiones de diseño y maquetación

### Elección de visualización para las tarjetas (`inline-block` vs `flex`)
Para la disposición de las tarjetas en fila se ha optado finalmente por **`display: flex`** en el contenedor `.contenido` por las siguientes razones:

1. **Gestión de espacios en blanco:** A diferencia de `display: inline-block`, Flexbox no interpreta los saltos de línea e indentaciones del código HTML como espacios de texto fantasma (~4-5px extra entre elementos).
2. **Control de distribución y alineación:** Con propiedades como `justify-content` (por ejemplo, `space-around` o `space-between`) y `align-items`, el contenedor distribuye y centra automáticamente los elementos hijos sin necesidad de recalcular márgenes manualmente.
3. **Mantenibilidad:** El diseño resulta más flexible y adaptable ante cambios de resolución o si se añaden más tarjetas en el futuro.

---

## Cuestionario teórico

### 1. ¿Qué diferencia hay entre `margin` y `padding`?
* **`padding` (relleno interno):** Es el espacio interior que separa el contenido del elemento respecto a su propio borde. Adopta el color de fondo asignado a la caja.
* **`margin` (margen externo):** Es la separación exterior que existe entre el borde del elemento y las demás cajas adyacentes del documento. Es transparente y no forma parte del área activa del elemento.

---

### 2. ¿Por qué saltaba la tercera tarjeta de línea?
Bajo el modelo de caja estándar (`box-sizing: content-box`), el espacio horizontal total ocupado por una caja se calcula con la fórmula:

$$\text{Ancho total} = \text{width} + \text{padding (izq + der)} + \text{border (izq + der)} + \text{margin (izq + der)}$$

Aplicando los valores asignados a cada tarjeta:
* **Width:** 220px
* **Padding:** 15px + 15px = 30px
* **Border:** 5px + 5px = 10px
* **Margin:** 10px + 10px = 20px
* **Total por tarjeta:** $220 + 30 + 10 + 20 = \mathbf{280\text{ px}}$

Dado que el contenedor principal `.pagina` tiene un ancho de **800px** (y su espacio interior disponible es de **760px** al restar sus 20px de padding por lado), las tres tarjetas suman **840px** (más los espacios en blanco propios de `inline-block`). Al sobrepasar con creces el espacio disponible, la tercera tarjeta no cabe y se desplaza automáticamente a la siguiente línea.

---

### 3. ¿Qué propiedades ignoraba el `<span>` y por qué?
* **Propiedades ignoradas:** Ignoraba **`width`** (100px), **`height`** (40px) y los márgenes verticales (**`margin-top`** y **`margin-bottom`**). Solo aplicaba el color de fondo y el margen horizontal.
* **Motivo:** Por defecto, la etiqueta `<span>` tiene un comportamiento en línea (`display: inline`). Los elementos en línea fluyen dentro del texto y su tamaño viene fijado exclusivamente por su contenido, por lo que el navegador no les permite definir dimensiones fijas ni empujar verticalmente a otros elementos. Al cambiar su valor a `display: inline-block`, pasa a admitir dimensiones de bloque manteniéndose alineado en el flujo horizontal.

---

### 4. ¿Qué hace `display: none` con el espacio que ocupaba la caja?
Al aplicar `display: none`, el elemento es retirado por completo del árbol de renderizado visual del navegador. **No reserva ningún hueco**: el espacio desaparece y el resto de los elementos del documento se reordenan automáticamente ocupando la posición libre (a diferencia de `visibility: hidden`, que oculta el elemento pero conserva su espacio en blanco).
