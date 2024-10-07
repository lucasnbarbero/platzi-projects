# Jerarquías de nodos en el DOM 🌳

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
