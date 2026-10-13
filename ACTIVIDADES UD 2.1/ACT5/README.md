# Ejercicio 5: Reto de Colisiones y Refactorización

## Parte A — Análisis de Especificidad y Colisiones

### Tabla de predicción

| Elemento | Texto / Contenido | Color resultante | Regla ganadora | Especificidad (ID, Clase, Elemento) |
| :--- | :--- | :--- | :--- | :---: |
| `h1` | `Hola CSS` | **brown** | `#titulo { color: brown; }` | `(1, 0, 0)` |
| `p` (1) | `Texto 1` | **purple** | `p.aviso { color: purple; }` | `(0, 1, 1)` |
| `p` (2) | `Texto 2` | **black** | `#importante { color: black; }` | `(1, 0, 0)` |
| `p` (3) | `Texto 3` | **orange** | `div p { color: orange; }` | `(0, 0, 2)` |

---

### Justificación razonada de cada caso:

1. **`<h1>` (`Hola CSS`):**
   * Reglas que colisionan:
     * `h1 { color: gray; }` → `(0, 0, 1)`
     * `.grande { color: teal; }` → `(0, 1, 0)`
     * `#titulo { color: brown; }` → `(1, 0, 0)`
   * **Motivo:** El selector de ID (`#titulo`) tiene el nivel más alto de especificidad (`1, 0, 0`), superando a la clase y al elemento. El color final es **brown**.

2. **Primer párrafo (`Texto 1`):**
   * Reglas que colisionan:
     * `p { color: green; }` → `(0, 0, 1)` (tras pisar a `color: blue` por estar más abajo)
     * `.aviso { color: red; }` → `(0, 1, 0)`
     * `p.aviso { color: purple; }` → `(0, 1, 1)`
   * **Motivo:** `p.aviso` combina un selector de tipo (`p`) y una clase (`.aviso`), dando una especificidad de `(0, 1, 1)`. Supera a `.aviso` `(0, 1, 0)` y a `p` `(0, 0, 1)`. El color final es **purple**.

3. **Segundo párrafo (`Texto 2`):**
   * Reglas que colisionan:
     * `p { color: green; }` → `(0, 0, 1)`
     * `.aviso { color: red; }` → `(0, 1, 0)`
     * `p.aviso { color: purple; }` → `(0, 1, 1)`
     * `#importante { color: black; }` → `(1, 0, 0)`
   * **Motivo:** El selector `#importante` es un identificador con especificidad `(1, 0, 0)`. Gana sobre cualquier combinación de clases o etiquetas. El color final es **black**.

4. **Tercer párrafo (`Texto 3`):**
   * Reglas que colisionan:
     * `p { color: blue; }` → `(0, 0, 1)`
     * `p { color: green; }` → `(0, 0, 1)`
     * `div p { color: orange; }` → `(0, 0, 2)`
   * **Motivo:** El selector descendente `div p` cuenta con dos elementos de tipo (`div` y `p`), alcanzando una especificidad de `(0, 0, 2)`. Es más específico que los selectores simples `p` `(0, 0, 1)`. El color final es **orange**.
