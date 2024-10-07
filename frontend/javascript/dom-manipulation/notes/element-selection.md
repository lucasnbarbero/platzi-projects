# Selección y acceso a elementos del DOM 🔍

En JavaScript, seleccionar y acceder a los elementos del DOM es esencial para poder manipular el contenido de una página web. Ya sea que quieras cambiar el texto de un botón, agregar clases CSS a un elemento, o actualizar el contenido dinámico, todo esto se logra mediante la manipulación del DOM.

### ¿Por qué necesitamos seleccionar elementos del DOM?

Seleccionar elementos del DOM nos permite interactuar directamente con la estructura HTML. Gracias a esta selección, podemos:

- **Modificar el contenido**: Cambiar el texto o HTML dentro de un elemento.
- **Actualizar el estilo**: Agregar, quitar o modificar clases y estilos CSS.
- **Manejar eventos**: Capturar y responder a interacciones del usuario, como clics o envíos de formularios.
- **Crear y eliminar nodos**: Añadir nuevos elementos al DOM o eliminar los existentes.

### ¿Cómo seleccionamos elementos del DOM?

En JavaScript, existen varios métodos para seleccionar elementos del DOM. Los más utilizados son:

- **`document.getElementById('id')`**: Selecciona un elemento por su ID único.

```javascript
const myElement = document.getElementById("myElement");
```

- **`document.querySelector('selector')`**: Selecciona el primer elemento que coincida con el selector CSS proporcionado.

```javascript
const firstDiv = document.querySelector("div");
```

- **`document.querySelectorAll('selector')`**: Selecciona **todos** los elementos que coincidan con el selector CSS y devuelve una lista de nodos.

```javascript
const allButtons = document.querySelectorAll("button");
```

- **`document.getElementsByClassName('class')`**: Selecciona todos los elementos que tengan una clase específica.

```javascript
const myClassElements = document.getElementsByClassName("myClass");
```

- **`document.getElementsByTagName('tag')`**: Selecciona todos los elementos de un tipo de etiqueta específico.

```javascript
const allParagraphs = document.getElementsByTagName("p");
```

### Ejemplo básico de acceso y manipulación

```javascript
// Seleccionamos un elemento por su ID
const title = document.getElementById("title");

// Modificamos el texto de ese elemento
title.innerText = "¡Hola, Mundo!";

// Seleccionamos todos los botones
const buttons = document.querySelectorAll("button");

// Cambiamos el color de fondo del primer botón
buttons[0].style.backgroundColor = "blue";
```
