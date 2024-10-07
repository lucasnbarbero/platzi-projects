# Diferencias entre HTMLCollection y NodeList

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