## Diferencias de sintaxis encontradas entre Java y Node.js

Durante la migración del proyecto de listas enlazadas desde Java hacia Node.js, se identificaron varias diferencias de sintaxis, aunque la lógica de la estructura de datos se mantuvo igual.

### 1. Acceso a atributos y métodos
En Java se usaban métodos como `getValue()` y `getNext()` para acceder a la información de cada nodo.  
En Node.js se accede directamente a las propiedades del objeto, por ejemplo `value`, `next` y `previous`.

**Java**
```java
current.getValue();
current.getNext();

Node.js

current.value;
current.next;

2. Uso de this

En Java se puede trabajar directamente con atributos como head, tail y size dentro de la clase.
En Node.js se usa this.head, this.tail y this._size para referirse a los atributos del objeto actual.

3. Tipado de datos

En Java la lista se implementó con genéricos, por ejemplo SinglyLinkedList<T>, lo que permite definir el tipo de dato de forma explícita.
En Node.js no se declaran tipos genéricos, porque JavaScript maneja tipado dinámico.

4. Creación de objetos

En Java la creación de nodos se realiza con sintaxis tipada.

Java
SimpleNode<T> newNode = new SimpleNode<>(value);

Node.js
const newNode = new SimpleNode(value);

5. Comparación con null

En Java se usó != null o == null.
En Node.js se utilizó !== null y === null, lo cual es más estricto en la comparación.

6. Tamaño de la lista

En Java se trabajó con la variable size.
En Node.js se utilizó _size para llevar el control de la cantidad de nodos.

7. Manejo de clases y módulos

En Java cada clase pertenece a un paquete y se usa la estructura de paquetes del lenguaje.
En Node.js se utiliza require() para importar archivos y module.exports para exportar clases.

Node.js
const SimpleNode = require("./SimpleNode");
module.exports = SinglyLinkedList;

8. Estructura de métodos

La lógica de los métodos fue la misma en ambos lenguajes, pero cambió la forma de escribirlos.
Por ejemplo, métodos como countOccurrences, clean, reverseInPlace y removeDuplicates mantuvieron el mismo comportamiento, cambiando únicamente la sintaxis del lenguaje.

Conclusión

La migración permitió comprobar que la lógica de estructuras de datos no cambia entre lenguajes, sino la forma de escribirla. Java y Node.js presentan diferencias de sintaxis, tipado y manejo de clases, pero la implementación de listas enlazadas conserva los mismos principios de recorrido, inserción, eliminación e inversión de nodos.