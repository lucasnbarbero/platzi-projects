# Modificación de estilos en HTML

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
