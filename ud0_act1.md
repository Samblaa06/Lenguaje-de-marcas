**Nombre** Samuel Piqueras Blanco

---

## Ejercicio 1: Observación de extensiones y comportamiento del navegador

* **Al abrir `textos.txt` en el navegador:**  
  El navegador lo interpreta como texto plano por lo que no procesa el código y muestra solo las etiquetas escritas.

* **Al renombrarlo a `textos.html` y volver a abrirlo:**  
  El navegador detecta la extensión `.html` y pasa a interpretarlo como un documento web estructurado (`text/html`). El motor de renderizado procesa las etiquetas `<h1>` y `<h3>`, mostrando el primer texto con formato de encabezado grande y el segundo de menor tamaño.

* **Conclusiones:**  
   Un archivo puede contener el mismo código fuente, pero solo se interpretará como un lenguaje de marcas estructurado si se especifica el tipo y formato en especifico.

---

## Ejercicio 2: Estructuración de módulos de DAM (`DAM.sgml`)

```xml
<dam>
    <modulo>
        <titulo>Lenguajes de Marcas</titulo>
        <contenido>
            <unidad>Introducción</unidad>
            <unidad>HTML</unidad>
            <unidad>CSS</unidad>
        </contenido>
    </modulo>
    <modulo>
        <titulo>Programación</titulo>
        <contenido>
            <unidad>Estructuras de control</unidad>
            <unidad>Programación orientada a objetos</unidad>
            <unidad>Colecciones y estructuras de datos</unidad>
        </contenido>
    </modulo>
    <modulo>
        <titulo>Bases de Datos</titulo>
        <contenido>
            <unidad>Modelo Entidad-Relación</unidad>
            <unidad>SQL DDL y DML</unidad>
            <unidad>Procedimientos y disparadores</unidad>
        </contenido>
    </modulo>
    <modulo>
        <titulo>Sistemas Informáticos</titulo>
        <contenido>
            <unidad>Gestión de hardware y sistemas operativos</unidad>
            <unidad>Configuración de redes locales</unidad>
            <unidad>Administración de servidores</unidad>
        </contenido>
    </modulo>
</dam>
```

---

## Ejercicio 3: Documento SGML para "Países del Mundo"

### Vocabulario
`paises`, `pais`, `nombre`, `capital`, `continente`, `idiomas`, `idioma`.

### Reglas
1. El elemento raíz es `<paises>` y contiene uno o varios elementos `<pais>`.
2. Cada `<pais>` contiene secuencialmente: `<nombre>`, `<capital>`, `<continente>` y `<idiomas>`.
3. El elemento `<idiomas>` contiene uno o más elementos `<idioma>`.
4. Los elementos terminales (`nombre`, `capital`, `continente`, `idioma`) solo pueden contener texto simple.

### Implementación
```xml
<paises>
    <pais>
        <nombre>España</nombre>
        <capital>Madrid</capital>
        <continente>Europa</continente>
        <idiomas>
            <idioma>Castellano</idioma>
            <idioma>Catalán / Valenciano</idioma>
            <idioma>Gallego</idioma>
            <idioma>Euskera</idioma>
        </idiomas>
    </pais>
    <pais>
        <nombre>Japón</nombre>
        <capital>Tokio</capital>
        <continente>Asia</continente>
        <idiomas>
            <idioma>Japonés</idioma>
        </idiomas>
    </pais>
    <pais>
        <nombre>Canadá</nombre>
        <capital>Ottawa</capital>
        <continente>América</continente>
        <idiomas>
            <idioma>Inglés</idioma>
            <idioma>Francés</idioma>
        </idiomas>
    </pais>
</paises>
```

---

## Ejercicio 4: Estructuración semántica de catálogo de libros

### Vocabulario
`biblioteca`, `libro`, `titulo`, `formato`, `isbn`, `autor`, `paginas`, `editorial`, `año`, `idioma`, `sinopsis`.

### Reglas
1. El elemento raíz es `<biblioteca>`, que agrupa uno o varios elementos `<libro>`.
2. Cada elemento `<libro>` debe contener obligatoriamente: `<titulo>`, `<formato>`, `<isbn>`, `<autor>`, `<editorial>` e `<idioma>`.
3. Los elementos `<paginas>`, `<año>` y `<sinopsis>` son opcionales.
4. Las etiquetas terminales solo contienen texto plano.

### Documento estructurado
```xml
<biblioteca>
    <libro>
        <titulo>Falcó</titulo>
        <formato>En papel</formato>
        <isbn>9788420419688</isbn>
        <autor>Arturo Pérez-Reverte</autor>
        <paginas>296</paginas>
        <editorial>Alfaguara</editorial>
        <idioma>Castellano</idioma>
    </libro>
    <libro>
        <titulo>Todo Alatriste</titulo>
        <formato>Ebook</formato>
        <isbn>9788420425528</isbn>
        <autor>Arturo Pérez-Reverte</autor>
        <editorial>Alfaguara</editorial>
        <idioma>Castellano</idioma>
    </libro>
    <libro>
        <titulo>Hombres buenos</titulo>
        <formato>En papel</formato>
        <isbn>9788466329804</isbn>
        <autor>Arturo Pérez-Reverte</autor>
        <editorial>Punto de Lectura</editorial>
        <año>2024</año>
        <sinopsis>La heroica aventura de quienes se atrevieron a cambiar el mundo con libros. En tiempos de oscuridad siempre hubo hombres buenos que lucharon para llevar las luces y el progreso. Y otros que procuraron impedirlo.</sinopsis>
    </libro>
</biblioteca>
```
