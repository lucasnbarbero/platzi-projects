# Atributos vs Propiedades en HTML y JavaScript 🏷️ 💻

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
