# 📝 Notas del curso de JavaScript: Manipulación de DOM

## ¿Qué es el DOM?

El **DOM** (Document Object Model) es una representación estructurada en forma de árbol de un documento HTML. Proporciona una interfaz para acceder y manipular los elementos del documento, como etiquetas, atributos y contenido. El DOM permite a los desarrolladores web interactuar con los elementos de una página web y realizar cambios dinámicos en **tiempo real**.

## El Objeto Window 🌍

El objeto **Window** es el objeto global en el navegador web y representa la ventana del navegador que contiene el documento HTML. Proporciona propiedades y métodos para controlar y manipular la ventana del navegador, tales como:

- Redireccionar a otra página.
- Abrir nuevas ventanas.
- Manejar eventos.
- Obtener información sobre el tamaño y posición de la ventana.

Estas funcionalidades permiten a los desarrolladores tener un mayor control sobre la experiencia del usuario en la web.

### Detalles adicionales sobre el objeto Window

El objeto **Window** no solo controla la ventana del navegador, sino que también es **el objeto global** en el entorno del navegador. ¡Eso significa que todas las variables y funciones globales que declaras se convierten en propiedades y métodos de `window` automáticamente! 😮

Por ejemplo, algunos de los métodos más comunes que podemos encontrar son:

- `setTimeout()`: Ejecuta código después de un tiempo definido.
- `setInterval()`: Ejecuta código repetidamente en intervalos de tiempo.

Además, el objeto **Window** contiene sub-objetos muy útiles, como:

- **`history`**: Controla el historial de navegación.
- **`location`**: Proporciona información sobre la URL actual.
- **`navigator`**: Da acceso a información sobre el navegador y el sistema.
- Y, uno de los más importantes... **`document`** 📄.

## El Objeto Document 📄

El **document** es una propiedad del objeto `window` que representa el documento HTML (árbol DOM) que está cargado en la ventana del navegador.

El objeto **Document** nos proporciona una serie de métodos y propiedades para acceder y manipular los elementos del DOM. Algunos ejemplos muy útiles incluyen:

- **`getElementById()`**: Selecciona un elemento por su ID.
- **`querySelector()`**: Selecciona el primer elemento que coincide con el selector.
- **`createElement()`**: Crea un nuevo elemento HTML.
- **`innerHTML`**: Permite leer o modificar el contenido HTML dentro de un elemento.

## Selección y acceso a elementos del DOM 🔍

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

## Jerarquías de nodos en el DOM 🌳

El DOM está estructurado como un árbol de nodos, lo que significa que los elementos tienen **relaciones jerárquicas**: algunos elementos son "padres", otros son "hijos", y algunos son "hermanos". Esto es clave para navegar y manipular el DOM de manera eficiente. En JavaScript, existen varios métodos y propiedades que nos permiten acceder y modificar estas relaciones jerárquicas entre nodos.

### Navegación entre nodos

En el siguiente código, mostramos cómo navegar en la jerarquía del DOM accediendo a elementos padres, hijos y hermanos:

```javascript
// Seleccionamos el elemento padre por su ID
const parent = document.getElementById("parent");
console.log(parent); // Muestra el nodo padre en la consola

// Accedemos a todos los hijos directos del nodo padre
const children = parent.children;
console.log(children); // HTMLCollection en vivo de los hijos

// Seleccionamos el primer hijo del nodo padre
const firstChild = parent.firstElementChild;
console.log(firstChild); // Primer hijo del nodo padre

// Seleccionamos el último hijo del nodo padre
const lastChild = parent.lastElementChild;
console.log(lastChild); // Último hijo del nodo padre

// Accedemos al nodo hermano anterior del nodo padre
const previousSibling = parent.previousElementSibling;
console.log(previousSibling); // Hermano anterior

// Accedemos al nodo hermano siguiente del nodo padre
const nextSibling = parent.nextElementSibling;
console.log(nextSibling); // Hermano siguiente
```

## Diferencias entre HTMLCollection y NodeList

- **HTMLCollection**: Es una colección **viva** de nodos, lo que significa que si los elementos DOM cambian, también lo hará la colección automáticamente.
- **NodeList**: Puede ser una colección **viva** o **estática**, dependiendo del contexto en el que se utilice. Los cambios en el DOM no siempre afectan a esta lista.

Por ejemplo:

- `children`: Devuelve un **HTMLCollection** en vivo.
- `childNodes`: Devuelve un **NodeList** que incluye todos los nodos hijos, no solo los elementos.

### Ejemplo con nodos padres y cercanos

```javascript
// Seleccionamos un elemento <li>
const children2 = document.querySelector("li");
console.log(children2); // Nodo <li>

// Accedemos al nodo padre directo del <li>
const parent2 = children2.parentNode;
console.log(parent2); // Nodo padre del <li>

// Accedemos al nodo elemento padre (más específico que node)
const grandParent = children2.parentElement;
console.log(grandParent); // Elemento padre del <li>

// Buscamos el ancestro más cercano que coincida con un selector
const grandGrandParent = children2.closest("menu");
console.log(grandGrandParent); // Ancestro más cercano que es un <menu>
```

## Propiedades clave para navegar en el DOM:

- `parentNode`: Devuelve el nodo padre (puede ser cualquier nodo).
- `parentElement`: Devuelve el elemento padre (excluye nodos que no sean elementos).
- `firstChild` y `lastChild`: Devuelven el primer y último nodo hijo, incluyendo nodos de texto o comentarios.
- `firstElementChild` y `lastElementChild`: Devuelven solo el primer y último **elemento** hijo.
- `previousSibling` y `nextSibling`: Devuelven los hermanos adyacentes (pueden ser cualquier tipo de nodo).
- `previousElementSibling` y `nextElementSibling`: Devuelven los hermanos adyacentes que sean elementos (excluye nodos de texto).

### Uso de `closest()` para buscar ancestros

El método `closest()` es uno de los más utilizados para encontrar el **ancestro más cercano** que coincide con un selector específico. Este método es útil cuando necesitas trabajar con elementos más arriba en la jerarquía DOM sin conocer la estructura exacta de antemano.

```javascript
const grandGrandParent = children2.closest("menu");
console.log(grandGrandParent); // Encuentra el <menu> más cercano como ancestro
```

## Atributos vs Propiedades en HTML y JavaScript 🏷️ 💻

Cuando trabajamos con elementos HTML, es fundamental entender la diferencia entre **atributos** y **propiedades**, ya que aunque pueden parecer similares, tienen roles diferentes en la interacción entre el HTML y el DOM en JavaScript.

### Atributos en HTML 🏷️

Los **atributos** son valores que se definen directamente en las etiquetas de apertura de los elementos HTML y controlan el comportamiento o el estado inicial de esos elementos. Algunos de los atributos más comunes que utilizamos en HTML son:

- `id`: Un identificador único para un elemento.
- `class`: Permite aplicar estilos CSS y agrupar elementos con comportamientos similares.
- `src`: Especifica la fuente de un recurso, como en una imagen o script.
- `href`: Define la URL de un enlace.

Por ejemplo, en el siguiente código HTML, los atributos definen cómo debe comportarse y verse el elemento desde el principio:

```html
<img id="myImage" src="imagen.jpg" alt="Imagen de ejemplo" class="img-fluid" />
```

### Propiedades en JavaScript 💻

Cuando manipulamos el DOM desde JavaScript, los atributos que definimos en HTML se reflejan como **propiedades** del objeto que representa el elemento en el DOM. Estas propiedades nos permiten acceder y modificar el estado actual del elemento.

Sin embargo, es importante tener en cuenta que **modificar una propiedad desde JavaScript no cambia el atributo inicial en el HTML**. El HTML refleja el **estado inicial**, mientras que las propiedades en JavaScript reflejan el **estado actual** del elemento.

### Ejemplo: Diferencia entre Atributos y Propiedades

Supongamos que tenemos un elemento con un atributo `src` definido en HTML para una imagen:

```html
<img id="myImage" src="imagen1.jpg" alt="Primera imagen" />
```

En este caso, el atributo `src` tiene el valor `"imagen1.jpg"`. Ahora, imaginemos que queremos cambiar la imagen que se muestra mediante JavaScript:

```javascript
const imgElement = document.getElementById("myImage");

// Cambiamos la propiedad 'src' a una nueva imagen
imgElement.src = "imagen2.jpg";

console.log(imgElement.src); // Muestra el nuevo valor: 'imagen2.jpg'
console.log(imgElement.getAttribute("src")); // Muestra el valor original del atributo: 'imagen1.jpg'
```

Aquí podemos ver que la **propiedad** `src` del objeto `imgElement` ha cambiado a `"imagen2.jpg"`, pero si inspeccionamos el **atributo** original usando `getAttribute()`, seguirá mostrando `"imagen1.jpg"`, que es el valor con el que el elemento fue creado en el HTML.

## Modificar texto en HTML con JavaScript ✏️

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

## Modificación de estilos en HTML

Modificar los estilos de los elementos HTML a través de JavaScript es muy sencillo y divertido. Puedes cambiar colores, tamaños, márgenes y más para hacer que tu página web luzca espectacular en tiempo real. 🚀

### Cómo modificar estilos

Para cambiar los estilos, simplemente selecciona el elemento que quieres modificar y usa la propiedad `style` para ajustar sus estilos CSS. Aquí tienes algunos ejemplos:

- **Cambiar el color de texto**:

```javascript
const heading = document.getElementById("titulo");
heading.style.color = "red"; // Cambia el color del texto a rojo
```

- **Modificar el tamaño de la fuente**:

```javascript
heading.style.fontSize = "24px"; // Cambia el tamaño de la fuente
```

- **Agregar un fondo**:

```javascript
const body = document.body;
body.style.backgroundColor = "#f0f0f0"; // Cambia el color de fondo de la página
```

### Uso de className y classList 🆕

Otra forma de modificar estilos es a través de la propiedad `className`. Esta propiedad permite añadir o quitar clases CSS de un elemento, lo que puede cambiar su apariencia basándose en las reglas definidas en tu archivo CSS. Sin embargo, es más recomendable utilizar la propiedad `classList`, que ofrece una manera más conveniente de acceder y manipular las clases CSS de un elemento HTML.

#### Métodos de `classList`:

- `.add(class)`: Agrega una o más clases al elemento.

```javascript
const button = document.getElementById("miBoton");
button.classList.add("btn", "btn-primary"); // Agrega las clases btn y btn-primary
```

- `.remove(class)`: Elimina una o más clases del elemento.

```javascript
button.classList.remove("btn-primary"); // Elimina la clase btn-primary
```

- `.toggle(class)`: Alterna la presencia de una clase. Si la clase está presente, se elimina; si no lo está, se agrega.

```javascript
button.addEventListener("click", () => {
  button.classList.toggle("active"); // Activa o desactiva la clase "active"
});
```

- `.contains(class)`: Verifica si una clase está presente en el elemento. Devuelve `true` o `false`.

```javascript
if (button.classList.contains("active")) {
  console.log("El botón está activo");
} else {
  console.log("El botón no está activo");
}
```

- `.replace(oldClass, newClass)`: Reemplaza una clase por otra.

```javascript
button.classList.replace("btn-primary", "btn-success"); // Cambia btn-primary por btn-success
```

- `.length`: Devuelve el número de clases que tiene el elemento.

```javascript
console.log(`El botón tiene ${button.classList.length} clases.`); // Muestra cuántas clases tiene el botón
```

Usar `classList` es mucho más limpio y seguro que manipular la propiedad `className` directamente, ya que evita problemas con la manipulación de cadenas y garantiza que las clases se gestionen correctamente. Esto hace que tu código sea más legible y menos propenso a errores. 🙌

### Estilos embebidos 💻

Los estilos embebidos son aquellos que se agregan directamente a las etiquetas HTML usando el atributo `style`. Por ejemplo:

```html
<p style="color: red;">Este texto es rojo</p>
```

Estos estilos tienen una alta especificidad, por lo que se aplican sobre los estilos definidos en un archivo CSS externo o en una etiqueta `<style>` en el `<head>`, a menos que esos otros estilos sean aún más específicos. Esto significa que si decides usar estilos embebidos, tendrás un control fuerte sobre cómo se verá ese elemento, aunque debes tener cuidado de no abusar de ellos para mantener un código limpio y fácil de mantener. ✨

### Carga de la página web 🌐

Es importante entender cómo se carga una página web para saber cuándo se aplican los estilos y los scripts:

1. **HTML**: El navegador comienza cargando y procesando el HTML de arriba hacia abajo.
2. **CSS**: El navegador descarga y aplica el CSS lo más pronto posible. Si hay un archivo CSS externo vinculado, el navegador lo descarga y aplica antes de mostrar la página completamente (esto se conoce como un "bloqueo de renderizado").
3. **JavaScript**: Si los scripts están en el `<head>` y no tienen el atributo `defer` o `async`, se detiene la carga de la página hasta que se descarguen y ejecuten. Por eso es común colocar los scripts al final del `<body>`, para que el HTML y el CSS se carguen antes de que se ejecute el JavaScript.

## Entendiendo innerHTML y insertAdjacentElement 📝

### `innerHTML`

La propiedad `innerHTML` es una herramienta poderosa y ampliamente utilizada en JavaScript que te permite obtener o establecer el contenido HTML de un elemento. Con `innerHTML`, puedes manipular dinámicamente el contenido de un elemento en tu página web sin necesidad de interactuar directamente con el DOM.

### ¿Cómo funciona? 🤔

- **Obteniendo contenido**: Cuando accedes a `innerHTML`, te devuelve la estructura HTML contenida dentro del elemento especificado como una cadena de texto. Por ejemplo, si tienes un `<div>` con algo de texto y elementos anidados, `innerHTML` te dará la estructura HTML completa como cadena.

```javascript
const myDiv = document.getElementById("myDiv");
const content = myDiv.innerHTML; // Devuelve el HTML dentro de myDiv
```

- **Establenciendo contenido**: También puedes asignar una nueva cadena de HTML a `innerHTML`, lo que reemplazará el contenido actual del elemento. Esto te permite agregar nuevos elementos, actualizar texto o cambiar estilos dinámicamente.

```javascript
myDiv.innerHTML = "<p>¡Nuevo contenido añadido!</p>"; // Reemplaza el contenido existente
```

**Cuidado**: ⚠️ Si bien `innerHTML` es conveniente, puede exponer tu aplicación a vulnerabilidades de seguridad, como ataques de Cross-Site Scripting (XSS), si no tienes cuidado con el contenido que se inyecta. Siempre valida o sanitiza la entrada del usuario si se va a agregar al DOM.

### `insertAdjacentElement`

El método `insertAdjacentElement` es una forma más precisa de insertar elementos en el DOM en relación con un elemento existente. Te permite especificar exactamente dónde deseas colocar el nuevo elemento en relación con el elemento de referencia.

#### ¿Cómo funciona? 🔍

El método toma dos argumentos: la posición relativa al elemento de referencia y el elemento que deseas insertar. La posición puede ser una de las siguientes cadenas:

- `"beforebegin"`: Inserta el elemento antes del elemento de referencia.
- `"afterbegin"`: Inserta el elemento como el primer hijo del elemento de referencia.
- `"beforeend"`: Inserta el elemento como el último hijo del elemento de referencia.
- `"afterend"`: Inserta el elemento después del elemento de referencia.

#### Ejemplo de uso:

```javascript
const myDiv = document.getElementById("myDiv");
const newElement = document.createElement("p");
newElement.textContent = "¡Soy un nuevo párrafo!";

// Insertar el nuevo elemento como el último hijo de myDiv
myDiv.insertAdjacentElement("beforeend", newElement);
```

Con `insertAdjacentElement`, puedes tener un control más preciso sobre la estructura de tu HTML, lo que facilita la manipulación del DOM de una manera más segura y organizada. ✨
