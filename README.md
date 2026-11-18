# Repaso de HTML y CSS

Apuntes de repaso de los conceptos principales de HTML y CSS.

---

## 1. HTML: estructura básica de una página

HTML define el contenido y la estructura de una página web. CSS define cómo se presenta visualmente.

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Mi página</title>
</head>
<body>
    <h1>Título principal</h1>
    <p>Este es un párrafo.</p>
</body>
</html>
```

- `<!DOCTYPE html>`: indica que usamos HTML5.
- `<html>`: contiene toda la página.
- `lang="es"`: indica el idioma del documento.
- `<head>`: información sobre la página.
- `<meta charset="UTF-8">`: permite mostrar correctamente caracteres como ñ y á.
- `<title>`: título que aparece en la pestaña del navegador.
- `<body>`: contenido visible de la página.

### Encabezados

```html
<h1>Título principal</h1>
<h2>Subtítulo</h2>
<h3>Subapartado</h3>
```

- `h1`: título principal.
- `h2`: apartado dentro del título principal.
- `h3`: apartado dentro de un `h2`.

Los encabezados se eligen por jerarquía, no solo por tamaño visual.

### Párrafos

```html
<p>Este es un párrafo.</p>
```

Cada `<p>` representa un párrafo.

---

## 2. HTML semántico

Estas etiquetas indican qué significa el contenido.

| Etiqueta | Significado |
|---|---|
| `<strong>` | Contenido importante. |
| `<em>` | Énfasis en una palabra o frase. |
| `<mark>` | Texto resaltado por su relevancia. |
| `<del>` | Texto eliminado. |
| `<ins>` | Texto añadido. |
| `<blockquote>` | Cita extensa. |
| `<br>` | Salto de línea. |
| `<hr>` | Separación temática. |

Ejemplo:

```html
<p>Esto es <strong>importante</strong>.</p>
<p>Esto tiene <em>énfasis</em>.</p>
<p>Precio anterior: <del>50 €</del></p>
<p>Precio actual: <ins>30 €</ins></p>
```

Diferencias:
- `<strong>` expresa importancia; `<b>` solo aplica negrita.
- `<em>` expresa énfasis; `<i>` puede representar texto en otro estilo o voz.

### Etiquetas adicionales

| Etiqueta | Para qué sirve | Ejemplo |
|---|---|---|
| `<abbr>` | Abreviatura | `<abbr title="Administración de Sistemas">ASIR</abbr>` |
| `<code>` | Código | `<code>print()</code>` |
| `<kbd>` | Entrada de teclado | `<kbd>Ctrl</kbd>` |
| `<dfn>` | Término definido | `<dfn>HTML</dfn>` |
| `<time>` | Fecha u hora | `<time datetime="2026-11-05">5 de noviembre</time>` |
| `<address>` | Información de contacto | Dirección o correo |
| `<sub>` | Subíndice | H<sub>2</sub>O |
| `<sup>` | Superíndice | 2<sup>3</sup> |

El atributo `datetime` proporciona una fecha u hora en formato legible por máquinas.

---

## 3. Imágenes

```html
<img src="imagenes/foto.jpg" alt="Descripción de la imagen">
```

- `src`: ruta de la imagen.
- `alt`: texto alternativo.
- `width`: ancho.
- `height`: alto.

Ejemplo:

```html
<img src="imagenes/logo.png" alt="Logo de mi web" width="200">
```

### Rutas

Ruta relativa:

```html
<img src="imagenes/foto.jpg">
```

Busca la carpeta `imagenes` desde la ubicación del documento.

Ruta absoluta:

```html
<img src="https://ejemplo.com/foto.jpg">
```

Busca la imagen en una dirección web.

### Bordes

```css
img {
    border: 2px solid black;
}
```

`border` define grosor, estilo y color del borde.

---

## 4. Enlaces

```html
<a href="https://www.google.com">Google</a>
```

- `<a>` crea un enlace.
- `href` indica el destino.

Abrir en otra pestaña:

```html
<a href="https://google.com" target="_blank">Google</a>
```

### Enlaces internos

```html
<a href="#contacto">Ir a contacto</a>

<section id="contacto">
    <h2>Contacto</h2>
</section>
```

`#contacto` apunta al elemento que tiene `id="contacto"`.

El `id` identifica un elemento concreto y debe ser único en la página.

---

## 5. Listas

### Lista desordenada

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

- `ul`: lista sin orden numérico.
- `li`: elemento de lista.

### Lista ordenada

```html
<ol>
    <li>Primero</li>
    <li>Segundo</li>
    <li>Tercero</li>
</ol>
```

`ol` genera una lista numerada.

### Menú de navegación

```html
<nav>
    <ul>
        <li><a href="#inicio">Inicio</a></li>
        <li><a href="#contacto">Contacto</a></li>
    </ul>
</nav>
```

`nav` representa una zona de navegación.

---

## 6. HTML y CSS: cómo se conectan

CSS significa **Cascading Style Sheets**. Se utiliza para modificar colores, tamaños, márgenes, posicionamiento, etc.

### CSS externo

En el HTML:

```html
<link rel="stylesheet" href="estilos.css">
```

En el CSS:

```css
p {
    color: red;
}
```

### CSS interno

```html
<style>
    p {
        color: red;
    }
</style>
```

Se escribe dentro de `head`.

### CSS en línea

```html
<p style="color: red;">Texto</p>
```

Se aplica directamente a un elemento. Generalmente se prefiere CSS externo para mantener el código organizado.

---

## 7. Anatomía de una regla CSS

```css
p {
    color: red;
    font-size: 20px;
}
```

- `p`: selector.
- `color`: propiedad.
- `red`: valor.
- `color: red;`: declaración.
- `{ }`: bloque de declaraciones.

Se puede leer como: “Selecciona todos los párrafos y ponles el texto rojo de 20 píxeles”.

---

## 8. Selectores CSS

Los selectores indican qué elementos HTML queremos modificar.

### Selector de etiqueta

```css
p {
    color: red;
}
```

Selecciona todos los párrafos.

### Selector de clase

HTML:

```html
<p class="destacado">Texto</p>
```

CSS:

```css
.destacado {
    color: red;
}
```

El punto `.` indica una clase. Una clase se puede reutilizar en varios elementos.

```html
<p class="destacado">Uno</p>
<p class="destacado">Dos</p>
```

### Selector de ID

HTML:

```html
<div id="cabecera">...</div>
```

CSS:

```css
#cabecera {
    background-color: black;
}
```

El símbolo `#` selecciona un `id`.

- `.clase`: puede aparecer muchas veces.
- `#id`: identifica un elemento único.

### Selector universal

```css
* {
    margin: 0;
}
```

Selecciona todos los elementos.

### Selector agrupado

```css
h1, h2, p {
    color: blue;
}
```

Aplica el mismo estilo a varios selectores.

### Selector descendiente

```css
nav a {
    color: red;
}
```

Selecciona todos los enlaces que estén dentro de `nav`, aunque haya elementos intermedios.

### Selector de hijo directo

```css
nav > a {
    color: red;
}
```

Selecciona solo los enlaces que son hijos directos de `nav`.

- `nav a`: cualquier descendiente.
- `nav > a`: solo hijos directos.

### Selectores de atributos

```css
[ejemplo] {
    color: red;
}
```

Selecciona elementos que tengan el atributo `ejemplo`, independientemente de su valor.

```html
<p ejemplo="hola">Texto</p>
```

Este párrafo sería seleccionado.

Para seleccionar un valor concreto:

```css
[ejemplo="hola"] {
    color: red;
}
```

Selecciona elementos cuyo atributo `ejemplo` tenga exactamente el valor `hola`.

Diferencia entre:

```css
[class="destacado"]
```

Selecciona elementos con ese valor exacto de `class`.

```css
.destacado
```

Selecciona elementos que tengan la clase `destacado`, incluso si también tienen otras clases:

```html
<p class="destacado grande">Texto</p>
```

---

## 9. Colores, texto y propiedades básicas

### Colores

```css
color: red;
background-color: yellow;
```

- `color`: color del texto.
- `background-color`: color del fondo.

También se puede usar hexadecimal:

```css
color: #2f5d46;
```

O `rgba()`:

```css
background-color: rgba(162, 179, 188, 0.5);
```

`rgba(red, green, blue, alpha)`:
- R: rojo.
- G: verde.
- B: azul.
- A: transparencia.

El último valor va de 0 a 1:
- `0`: completamente transparente.
- `0.5`: semitransparente.
- `1`: completamente opaco.

### Texto

```css
font-family: Arial, sans-serif;
font-size: 20px;
font-weight: bold;
font-style: italic;
text-align: center;
text-decoration: underline;
line-height: 1.5;
```

| Propiedad | Función |
|---|---|
| `font-family` | Tipo de letra. |
| `font-size` | Tamaño. |
| `font-weight` | Grosor. |
| `font-style` | Estilo, como cursiva. |
| `text-align` | Alineación del texto. |
| `text-decoration` | Subrayado, tachado, etc. |
| `line-height` | Altura de línea. |

### Importar fuentes

```css
@import url('https://fonts.googleapis.com/css2?family=Nunito&display=swap');
```

Después:

```css
body {
    font-family: Nunito, sans-serif;
}
```

---

## 10. Modelo de caja: width, height, margin, padding y border

Cada elemento HTML se comporta como una caja.

```css
div {
    width: 300px;
    height: 200px;
    padding: 20px;
    border: 5px solid black;
    margin: 10px;
}
```

| Propiedad | Qué significa |
|---|---|
| `width` | Ancho del contenido. |
| `height` | Alto del contenido. |
| `padding` | Espacio entre contenido y borde. |
| `border` | Borde de la caja. |
| `margin` | Espacio exterior entre elementos. |

Orden desde dentro hacia fuera:

**Contenido → padding → border → margin**

### Margin y padding

- `padding`: espacio interior.
- `margin`: espacio exterior.

### Centrar con margin

```css
.contenedor {
    width: 960px;
    margin: 0 auto;
}
```

Esto centra horizontalmente un elemento de ancho definido.

- `0`: margen superior e inferior.
- `auto`: el navegador distribuye el margen izquierdo y derecho.

### box-sizing

```css
box-sizing: border-box;
```

Con el valor normal (`content-box`), `width` solo mide el contenido.

Con `border-box`, el ancho incluye contenido, padding y borde. Esto facilita controlar el tamaño total de la caja.

---

## 11. Display: comportamiento de los elementos

`display` define cómo se muestra un elemento.

### `display: block`

```css
div {
    display: block;
}
```

Un elemento de bloque:
- Ocupa normalmente todo el ancho disponible.
- Comienza en una nueva línea.
- Puede tener `width` y `height`.

Ejemplos: `div`, `p`, `section`.

### `display: inline`

```css
span {
    display: inline;
}
```

Un elemento en línea:
- No empieza una nueva línea.
- Se coloca junto a otros elementos.
- `width` y `height` no funcionan como en un bloque.

Ejemplos: `span`, `a`, `strong`.

### `display: inline-block`

```css
article {
    display: inline-block;
    width: 270px;
}
```

Combina características:
- Se coloca junto a otros elementos, como `inline`.
- Permite establecer ancho y alto, como `block`.

Sirve para poner tarjetas una al lado de otra.

### `display: none`

```css
.elemento {
    display: none;
}
```

El elemento desaparece y no ocupa espacio.

### `visibility: hidden`

```css
.elemento {
    visibility: hidden;
}
```

El elemento se vuelve invisible, pero mantiene el espacio que ocupaba.

| Propiedad | Invisible | Conserva espacio |
|---|---|---|
| `display: none` | Sí | No |
| `visibility: hidden` | Sí | Sí |

### `display: flex`

```css
.contenedor {
    display: flex;
}
```

Convierte el elemento en un contenedor flexible y permite organizar sus hijos en filas o columnas. En algunos ejercicios estaba prohibido utilizar flex, grid y float, por lo que se resolvía con `inline-block` y posicionamiento.

---

## 12. Float y clear

### `float`

```css
img {
    float: left;
    margin-right: 20px;
}
```

Hace que el elemento flote a la izquierda o derecha, permitiendo que el texto se coloque a su alrededor.

```css
float: left;
float: right;
```

### `clear`

```css
footer {
    clear: both;
}
```

Evita que el elemento quede al lado de elementos flotantes anteriores.

Valores:
- `clear: left`
- `clear: right`
- `clear: both`

`clear: both` evita flotantes tanto de izquierda como de derecha.

---

## 13. Overflow

`overflow` controla qué pasa cuando el contenido supera las dimensiones de su caja.

```css
.caja {
    width: 200px;
    height: 100px;
    overflow: auto;
}
```

| Valor | Comportamiento |
|---|---|
| `visible` | El contenido sobresale. Es el valor predeterminado. |
| `hidden` | Oculta el contenido que sobresale. |
| `scroll` | Añade barras de desplazamiento. |
| `auto` | Añade barras cuando hacen falta. |

Ejemplo:

```css
.opinion {
    height: 170px;
    overflow: auto;
}
```

Si el texto es demasiado largo, aparecerá una barra de desplazamiento dentro de la opinión.

- `scroll`: fuerza la zona de desplazamiento.
- `auto`: solo la muestra cuando es necesaria.

---

## 14. Position: static, relative, absolute, fixed y sticky

La propiedad `position` determina cómo se posiciona un elemento.

### `position: static`

```css
div {
    position: static;
}
```

Es el posicionamiento normal por defecto. El elemento aparece donde le corresponde según el flujo HTML.

### `position: relative`

```css
.caja {
    position: relative;
    top: 10px;
    left: 20px;
}
```

El elemento se mueve respecto a su posición original.

- `top: 10px`: baja 10px.
- `bottom: 10px`: sube 10px.
- `left: 10px`: se desplaza 10px hacia la derecha.
- `right: 10px`: se desplaza 10px hacia la izquierda.

El elemento conserva el espacio que ocupaba originalmente.

### `position: absolute`

```css
.etiqueta {
    position: absolute;
    top: 10px;
    right: 10px;
}
```

El elemento se coloca respecto a su contenedor de referencia.

Para posicionarlo dentro de un contenedor:

```css
.tarjeta {
    position: relative;
}

.etiqueta {
    position: absolute;
    top: 10px;
    right: 10px;
}
```

- `.tarjeta` crea el punto de referencia.
- `.etiqueta` se posiciona respecto a `.tarjeta`.

Si el padre no tiene un posicionamiento adecuado, el elemento absoluto puede posicionarse respecto a otro ancestro o al bloque inicial de la página.

El elemento absoluto sale del flujo normal y no reserva espacio como un elemento normal.

### `position: fixed`

```css
.boton-subir {
    position: fixed;
    bottom: 20px;
    right: 20px;
}
```

El elemento queda fijado respecto a la ventana del navegador. Aunque hagas scroll, permanece en el mismo lugar de la pantalla.

### `position: sticky`

```css
nav {
    position: sticky;
    top: 0;
}
```

El elemento se comporta normalmente hasta alcanzar la posición indicada y entonces se queda pegado durante el scroll.

### Diferencias

| Posición | Referencia |
|---|---|
| `static` | Flujo normal. |
| `relative` | Su posición original. |
| `absolute` | Contenedor de referencia. |
| `fixed` | Ventana del navegador. |
| `sticky` | Flujo normal hasta quedarse pegado durante el scroll. |

### `z-index`

```css
.caja {
    position: relative;
    z-index: 2;
}
```

Controla qué elemento aparece delante de otro cuando se superponen.

- Un valor mayor suele aparecer delante de uno menor.
- `z-index` también depende de los contextos de apilamiento.

---

## 15. Transform y transition

### `transform`

```css
img:hover {
    transform: scale(1.1);
}
```

Modifica visualmente el elemento.

| Función | Resultado |
|---|---|
| `scale(1.1)` | Aumenta el tamaño un 10%. |
| `scale(0.9)` | Reduce el tamaño un 10%. |
| `translateX(20px)` | Mueve horizontalmente. |
| `translateY(-10px)` | Mueve verticalmente hacia arriba. |
| `rotate(10deg)` | Gira 10 grados. |

Ejemplo:

```css
.tarjeta:hover {
    transform: translateY(-12px);
}
```

La tarjeta se desplaza visualmente hacia arriba.

### `transition`

```css
img {
    transition: transform 0.3s;
}
```

Hace que el cambio de una propiedad sea gradual.

- `transform`: cambia visualmente la posición, tamaño o rotación.
- `transition`: suaviza el cambio entre estados.

---

## 16. Pseudoclases: estados de un elemento

Una pseudoclase selecciona un elemento según su estado o posición.

Se escribe con un solo dos puntos:

```css
selector:pseudoclase
```

### `:hover`

```css
a:hover {
    color: orange;
}
```

Se activa cuando el cursor pasa por encima.

### `:focus`

```css
input:focus {
    border: 2px solid blue;
}
```

Se activa cuando el elemento recibe el foco, por ejemplo al hacer clic en un campo o llegar a él mediante el teclado.

### `:required`

```css
input:required {
    background-color: lightyellow;
}
```

Selecciona campos que tienen el atributo `required`.

### `:disabled`

```css
input:disabled {
    background-color: gray;
}
```

Selecciona campos deshabilitados.

### `:read-only`

```css
input:read-only {
    background-color: lightgray;
}
```

Selecciona campos de solo lectura.

Diferencias:
- `disabled`: el campo está deshabilitado.
- `readonly`: se puede ver, pero no modificar.

### `:checked`

```css
input:checked {
    accent-color: green;
}
```

Selecciona un checkbox o radio marcado.

### `:not()`

```css
p:not(.especial) {
    color: red;
}
```

Selecciona los párrafos que no tengan la clase `especial`.

También:

```css
input:not(:disabled)
```

Selecciona inputs que no estén deshabilitados.

### `:nth-child()`

Selecciona elementos según su posición entre los hijos de su padre.

```css
li:nth-child(2) {
    color: red;
}
```

Selecciona el segundo hijo que sea `li`.

Importante: `nth-child()` cuenta la posición entre todos los hijos, no solo entre los elementos que coincidan con el selector.

### `odd` y `even`

```css
li:nth-child(odd)
```

Selecciona posiciones impares: 1, 3, 5, 7…

```css
li:nth-child(even)
```

Selecciona posiciones pares: 2, 4, 6, 8…

### Fórmulas de `nth-child`

```css
li:nth-child(3n)
```

Selecciona cada tercer elemento: 3, 6, 9, 12…

```css
li:nth-child(3n + 1)
```

Selecciona 1, 4, 7, 10…

- `n` representa una secuencia de números.
- `3n` significa múltiplos de 3.
- `+1` desplaza la secuencia una posición.

### Combinar pseudoclases

```css
input:hover:focus {
    background-color: yellow;
}
```

Selecciona un input que tenga el cursor encima y además esté enfocado. Ambas condiciones deben cumplirse.

### `:checked + label`

```css
input:checked + label {
    color: green;
}
```

Significa:
1. Busca un input.
2. Comprueba que esté marcado.
3. Selecciona el `label` que esté inmediatamente después.

HTML:

```html
<input type="checkbox" id="acepto">
<label for="acepto">Acepto</label>
```

El símbolo `+` es el combinador de hermano adyacente: selecciona al siguiente hermano inmediato.

---

## 17. Pseudoelementos: partes de un elemento

Los pseudoelementos se escriben normalmente con dos dos puntos:

```css
selector::pseudoelemento
```

- Pseudoclase: selecciona un elemento según su estado.
- Pseudoelemento: selecciona o crea una parte específica de ese elemento.

### `::first-letter`

```css
p::first-letter {
    font-size: 30px;
    color: red;
}
```

Selecciona la primera letra del párrafo.

### `::first-line`

```css
p::first-line {
    font-weight: bold;
}
```

Selecciona la primera línea del párrafo. La línea depende del ancho disponible y puede cambiar si se modifica el tamaño de la caja.

### `::selection`

```css
p::selection {
    background-color: orange;
    color: white;
}
```

Modifica la apariencia del texto cuando el usuario lo selecciona.

### `::before`

```css
h2::before {
    content: "★ ";
}
```

Inserta contenido antes del contenido del elemento.

### `::after`

```css
h2::after {
    content: " ✓";
}
```

Inserta contenido después del contenido del elemento.

### La propiedad `content`

Es importante para `::before` y `::after`.

```css
p::before {
    content: "Nota: ";
}
```

Sin `content`, estos pseudoelementos normalmente no muestran contenido generado.

Se puede utilizar:

```css
content: "Texto";
content: "★";
content: "";
```

`content: ""` crea el pseudoelemento sin añadir texto visible.

### Diferencia entre pseudoclase y pseudoelemento

| Selector | Qué selecciona |
|---|---|
| `:hover` | Elemento con el cursor encima. |
| `:focus` | Elemento enfocado. |
| `:checked` | Control marcado. |
| `:nth-child(2)` | Elemento según su posición. |
| `::first-letter` | Primera letra. |
| `::first-line` | Primera línea. |
| `::before` | Contenido generado antes. |
| `::after` | Contenido generado después. |
| `::selection` | Texto seleccionado. |

Truco: pseudoclase = estado; pseudoelemento = parte.

---

## 18. Tablas HTML

```html
<table>
    <tr>
        <th>Hora</th>
        <th>Lunes</th>
        <th>Martes</th>
    </tr>
    <tr>
        <th>8:00</th>
        <td>HTML</td>
        <td>CSS</td>
    </tr>
</table>
```

| Etiqueta | Función |
|---|---|
| `<table>` | Tabla. |
| `<tr>` | Fila. |
| `<th>` | Celda de encabezado. |
| `<td>` | Celda normal. |
| `<caption>` | Título de la tabla. |

CSS típico:

```css
table {
    border-collapse: collapse;
    width: 100%;
}

th, td {
    border: 1px solid black;
    padding: 10px;
}
```

`border-collapse: collapse` hace que los bordes de las celdas se junten en uno solo.

---

## 19. Formularios HTML

Los formularios permiten recoger información del usuario.

```html
<form>
    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre">

    <input type="submit" value="Enviar">
</form>
```

### Etiquetas y atributos

| Elemento/atributo | Función |
|---|---|
| `<form>` | Contenedor del formulario. |
| `<label>` | Etiqueta descriptiva de un campo. |
| `<input>` | Campo de entrada. |
| `<textarea>` | Campo de texto de varias líneas. |
| `<select>` | Lista desplegable. |
| `<option>` | Opción de una lista. |
| `type="text"` | Texto. |
| `type="email"` | Correo electrónico. |
| `type="password"` | Contraseña. |
| `type="checkbox"` | Casilla de selección. |
| `type="radio"` | Opción de selección única. |
| `type="submit"` | Botón de envío. |
| `required` | Campo obligatorio. |
| `disabled` | Campo deshabilitado. |
| `readonly` | Campo no editable. |
| `placeholder` | Texto de ayuda dentro del campo. |

### Relación entre label e input

```html
<label for="correo">Correo:</label>
<input type="email" id="correo">
```

El atributo `for` del label debe coincidir con el `id` del input. Al pulsar sobre la etiqueta, se activa el campo correspondiente.

---

## 20. Elementos semánticos de estructura

| Etiqueta | Función |
|---|---|
| `<header>` | Cabecera de una página o sección. |
| `<nav>` | Menú de navegación. |
| `<main>` | Contenido principal. |
| `<section>` | Sección temática. |
| `<article>` | Contenido independiente. |
| `<aside>` | Contenido complementario. |
| `<footer>` | Pie de página o sección. |
| `<div>` | Contenedor genérico sin significado semántico propio. |
| `<span>` | Contenedor genérico en línea. |

### Diferencia entre `div` y `section`

`div` es un contenedor genérico.

`section` representa una sección temática del documento.

Ejemplo:

```html
<section id="rutas">
    <h2>Rutas</h2>

    <article>
        <h3>Ruta de montaña</h3>
        <p>Descripción...</p>
    </article>
</section>
```

Una tarjeta de ruta puede ser un `article` porque representa contenido independiente dentro de la sección.

---

## 21. CSS: cascada, especificidad e herencia

La cascada determina qué estilo gana cuando varias reglas afectan al mismo elemento.

```css
p {
    color: red;
}

p {
    color: blue;
}
```

El párrafo será azul, porque ambas reglas tienen la misma especificidad y la última prevalece.

### Especificidad

Si las reglas tienen distinta especificidad, no siempre gana la última.

Orden general de fuerza:
1. Estilos en línea (`style="..."`).
2. Selectores de ID (`#id`).
3. Selectores de clase, atributos y pseudoclases (`.clase`, `[type]`, `:hover`).
4. Selectores de etiqueta (`p`, `h1`).
5. Selector universal (`*`).

Ejemplo:

```css
p {
    color: red;
}

.destacado {
    color: blue;
}
```

```html
<p class="destacado">Texto</p>
```

El texto será azul, porque el selector de clase tiene más especificidad que el selector de etiqueta.

### Herencia

Algunas propiedades se heredan de los elementos padres.

```css
body {
    color: blue;
    font-family: Arial;
}
```

Normalmente, los párrafos y encabezados dentro del `body` heredarán el color y la fuente.

No todas las propiedades se heredan. Por ejemplo, `margin`, `padding` y `border` normalmente no se heredan.

---

## 22. Patrones de los ejercicios finales

### Contenedor centrado

```css
.contenedor {
    width: 960px;
    margin: 0 auto;
}
```

Define un ancho y centra el contenedor horizontalmente.

### Página a pantalla completa

```css
.pagina {
    width: 100%;
    min-height: 100vh;
}
```

- `width: 100%`: ocupa todo el ancho disponible.
- `min-height: 100vh`: como mínimo, ocupa toda la altura de la ventana.

`100vh` significa el 100% de la altura de la ventana del navegador.

### Tarjetas una al lado de otra

```css
.tarjeta {
    display: inline-block;
    width: 270px;
}
```

Permite colocar tarjetas horizontalmente sin usar flex o grid.

### Tarjeta central elevada

```css
.tarjeta-central {
    position: relative;
    top: -12px;
}
```

La tarjeta se desplaza hacia arriba 12px sin perder su espacio original.

### Menú pegajoso

```css
nav {
    position: sticky;
    top: 0;
}
```

El menú acompaña al usuario durante el scroll.

### Sello colocado en una esquina del header

```css
header {
    position: relative;
}

.sello {
    position: absolute;
    top: 16px;
    right: 16px;
}
```

El `header` es el contenedor de referencia para el sello.

### Etiqueta sobre una imagen

```css
.foto {
    position: relative;
    overflow: hidden;
}

.etiqueta {
    position: absolute;
    top: 10px;
    right: 10px;
}
```

La etiqueta se posiciona encima de la foto. `overflow: hidden` evita que el contenido sobresalga de los límites de la foto.

### Polaroids superpuestas

```css
.polaroid {
    position: absolute;
}

.polaroid-central {
    z-index: 2;
}
```

El posicionamiento absoluto permite superponerlas. `z-index` determina cuál aparece delante.

### Polaroid que pasa al frente al pasar el ratón

```css
.polaroid:hover {
    z-index: 10;
}
```

Al pasar el cursor, aumenta su nivel de apilamiento y aparece delante de las demás.

### Opiniones con scroll

```css
.opinion {
    height: 170px;
    overflow: auto;
}
```

Limita la altura y permite desplazarse por el contenido.

### Botón fijo para volver arriba

```css
.subir {
    position: fixed;
    bottom: 20px;
    right: 20px;
}
```

Se mantiene en la misma posición de la pantalla mientras haces scroll.

---

## 23. Diferencias que suelen confundir

| Conceptos | Diferencia |
|---|---|
| `class` / `id` | Clase reutilizable; ID único. |
| `.clase` / `[clase]` | Clase CSS; atributo llamado `clase`. |
| `margin` / `padding` | Exterior / interior. |
| `block` / `inline` | Nueva línea / misma línea. |
| `inline-block` / `inline` | Permite ancho y alto / no funciona como un bloque. |
| `display: none` / `visibility: hidden` | Elimina espacio / conserva espacio. |
| `relative` / `absolute` | Se desplaza desde su lugar / se coloca respecto a un contenedor. |
| `fixed` / `sticky` | Fijo a la ventana / se pega durante el scroll. |
| `overflow: hidden` / `auto` | Recorta / permite scroll si hace falta. |
| `transform` / `transition` | Cambia visualmente / suaviza el cambio. |
| `:hover` / `:focus` | Cursor encima / elemento enfocado. |
| `:checked` / `:disabled` | Marcado / deshabilitado. |
| `:nth-child()` / `:not()` | Posición / exclusión. |
| Pseudoclase / pseudoelemento | Estado / parte del elemento. |
| `::before` / `::after` | Contenido generado antes / después. |
| `float` / `position` | Hace flotar el elemento / define su posicionamiento. |
| `z-index` | Controla el orden de superposición. |

---

## 24. Diez conceptos fundamentales

1. HTML estructura la página; CSS la presenta.
2. `class` se selecciona con `.` y `id` con `#`.
3. `margin` es exterior y `padding` interior.
4. `block` ocupa una línea; `inline` comparte línea; `inline-block` permite ambas cosas.
5. `relative` conserva su espacio; `absolute` sale del flujo normal.
6. `fixed` se queda fijado a la ventana; `sticky` se pega durante el scroll.
7. `overflow` controla qué ocurre cuando el contenido no cabe.
8. `:hover`, `:focus`, `:checked` y `:nth-child()` son pseudoclases.
9. `::before`, `::after`, `::first-letter` y `::first-line` son pseudoelementos.
10. `z-index` decide qué elemento aparece delante cuando se superponen.

## 25. Cómo leer una regla CSS

No basta con memorizar propiedades. Es útil poder traducir una regla a lenguaje normal.

```css
article:hover {
    position: relative;
    top: -10px;
    z-index: 2;
}
```

Se lee:

“Cuando pase el cursor sobre el artículo, desplázalo 10 píxeles hacia arriba y colócalo por delante de los elementos con menor nivel de apilamiento”.

Entender esa traducción ayuda a comprender CSS y a identificar qué hace cada regla.
