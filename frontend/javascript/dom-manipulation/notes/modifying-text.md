# Modificar texto en HTML con JavaScript ✏️

Una de las funcionalidades más útiles del DOM es la capacidad de **modificar el contenido de los elementos HTML** de forma dinámica. Esto se hace a través de varias propiedades y métodos que JavaScript proporciona para interactuar con los nodos de texto.

### Propiedades clave para modificar texto

Las dos propiedades más comunes para modificar el contenido de un elemento HTML son:

- `innerText`: Cambia el texto dentro de un elemento, respetando la visibilidad del CSS. Si un texto está oculto por CSS (`display: none;`), `innerText` no lo incluirá.

- `textContent`: Cambia el texto dentro de un elemento, pero incluye todo el contenido de texto, incluso el que está oculto por CSS.

### Ejemplos:

- Usando `innerText`

```html
<!-- HTML -->
<h1 id="header">Texto original</h1>

<!-- JavaScript -->
<script>
  // Seleccionamos el elemento por su ID
  const header = document.getElementById("header");

  // Modificamos el texto del h1
  header.innerText = "¡Nuevo texto!";
</script>
```

En este ejemplo, el texto del encabezado cambiará a "¡Nuevo texto!".

- Usando `textContent`

```html
<!-- HTML -->
<p id="paragraph">Texto visible <span style="display: none;">Texto oculto</span></p>

<!-- JavaScript -->
<script>
  // Seleccionamos el párrafo por su ID
  const paragraph = document.getElementById("paragraph");

  // Cambiamos el contenido completo del párrafo, incluyendo el texto oculto
  paragraph.textContent = "Texto completamente nuevo.";
</script>
```

Este código reemplaza **todo** el contenido de texto del párrafo, independientemente de si el contenido está visible u oculto.
