# Propiedades clave para navegar en el DOM:

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