# Mitos y Verdades sobre Programación Orientada a Objetos (POO)

## 1. “Todos los lenguajes orientados a objetos soportan herencia múltiple por defecto.”  
- **Mito.** No todos los lenguajes de POO soportan herencia múltiple de forma nativa. Por ejemplo, **Java y JavaScript** no permiten herencia múltiple directa, mientras que **C++ sí la admite**. En JavaScript, se puede lograr un comportamiento similar mediante **mixins** o la composición de objetos.

## 2. “La Programación Orientada a Objetos permite organizar el código en entidades con responsabilidad clara.”  
- **Verdad.** La POO se basa en conceptos como encapsulación, herencia y polimorfismo, los cuales ayudan a organizar el código en **clases y objetos** con responsabilidades bien definidas. Esto facilita el mantenimiento y la escalabilidad del software.

## 3. “En JavaScript, usar funciones constructoras es obsoleto porque existen las clases desde ES6.”  
- **Mito.** Aunque las clases de ES6 (`class`) ofrecen una sintaxis más clara y estructurada, las funciones constructoras siguen siendo válidas y funcionales. Internamente, las clases en JavaScript **siguen usando prototipos**, por lo que las funciones constructoras no están obsoletas, sino que simplemente hay una alternativa más moderna.

## 4. “La abstracción implica eliminar cualquier detalle que no sea importante para la funcionalidad principal.”  
- **Verdad.** La abstracción en POO consiste en **ocultar detalles innecesarios** y exponer solo lo esencial. Por ejemplo, una clase `Coche` puede exponer métodos como `acelerar()` y `frenar()`, sin necesidad de mostrar los detalles internos del motor.

## 5. “Para crear objetos usando funciones constructoras, es obligatorio usar el prototipo explícitamente.”  
- **Mito.** No es obligatorio definir propiedades en el **prototype**; las funciones constructoras pueden definir propiedades dentro de `this` sin necesidad de modificar explícitamente el prototipo. Sin embargo, usar el prototipo ayuda a **compartir métodos** entre instancias y ahorrar memoria.  

```javascript
function Persona(nombre) {
    this.nombre = nombre; // No usa el prototipo
}
Persona.prototype.saludar = function() {
    console.log(`Hola, soy ${this.nombre}`);
};
let juan = new Persona("Juan");
```

## 6. “La POO promueve la escalabilidad al agrupar datos y comportamiento en entidades lógicas.”  
- **Verdad.** Agrupar datos y comportamiento en **clases y objetos** ayuda a dividir el código en módulos reutilizables, lo que facilita la **escalabilidad y mantenimiento** de aplicaciones grandes.

## 7. “La palabra clave this en las funciones constructoras apunta a un objeto global, sin importar si se usa new.”  
- **Mito.** Si una función constructora se llama **sin `new`**, `this` apuntará al objeto global (`window` en navegadores o `global` en Node.js). Pero si se usa `new`, `this` apunta a la nueva instancia del objeto.  

```javascript
function Persona(nombre) {
    this.nombre = nombre;
}
let juan = new Persona("Juan"); // Aquí this es la nueva instancia (juan)
Persona("Pedro"); // Aquí this apunta al objeto global (error si se usa 'use strict')
```

---


