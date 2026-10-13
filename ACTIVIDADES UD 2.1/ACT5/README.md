# Ejercicio 5: Reto de colisiones y refactorización

## Parte A — Detective de colisiones

### Tabla de predicciones y resultados

| Elemento | Texto | Color final | Selector ganador | Especificidad | Razón |
| :--- | :--- | :--- | :--- | :---: | :--- |
| `h1` | `Hola CSS` | **brown** | `#titulo` | `(1, 0, 0)` | El ID `#titulo` gana por especificidad sobre la clase `.grande` (0,1,0) y la etiqueta `h1` (0,0,1). |
| `p` (1) | `Texto 1` | **purple** | `p.aviso` | `(0, 1, 1)` | `p.aviso` combina etiqueta + clase (0,1,1), superando a `.aviso` (0,1,0) y a `p` (0,0,1). |
| `p` (2) | `Texto 2` | **black** | `#importante` | `(1, 0, 0)` | El ID `#importante` tiene la mayor especificidad de todas las reglas en juego. |
| `p` (3) | `Texto 3` | **orange** | `div p` | `(0, 0, 2)` | El selector descendente suma dos etiquetas (0,0,2), ganando a `p` (0,0,1). |

---

## Parte B — Refactorización

* Se han eliminado todos los atributos en línea `style="..."` de la página anterior y se han centralizado en `estilos.css`.
* Se incluye una agrupación de selectores separados por comas (`body, h2, button`).
* El archivo `estilos.css` queda organizado por secciones comentadas (`/* ... */`).
