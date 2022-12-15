Hay una serie de conceptos significativos que está bien que veamos y que salieron en las últimas actualizaciones de javascript.


### **Object Destructuring**

Nos permite acceder a valores de un objeto de una manera más rápida.


```jsx
let serie = {
	nombre: 'Big Bang'
	genero: 'Comedia'
  capitulo: {
		nombre: 'Piloto',
		numero: 0
		temporada: 1
	},

}

let { nombre , genero } = serie;

console.log(nombre);
console.log(genero);

```


### Spread Operator

Este operador permite que una expresión sea extendida en situaciones en las que se esperan varios argumentos/elementos


```jsx
let flanders = ['Ned', 'Todd', 'Rod'];
let simpson = ['Homer', 'Bart', 'Lisa'];

let allFamilies = [...flanders, ...simpson];

let simpsonCopy = [...simpson];

let lastSimpson = [...simpson].reverse();

// No se ha modificado
console.log(simpson);
console.log(simpsonCopy);
console.log(lastSimpson);
```


También se utiliza para funciones, strings y objetos


```jsx
// Párametros función
function suma(a, b, c) {
	return a + b + c;
}

let numeros = [1, 2, 3];
suma(...numeros);

// Strings
let simpson = 'HOMER';
let characters = [ ...simpson ];
console.log(characters);

// Objetos 1
const simpson2 = { firstName: 'Homer', age: 50 };
const simpson1 = { lastName: 'Simpson', gender: 'M' };

const newSimpson = { ...simpson1, ...simpson2, color: 'yellow' };
console.log(newSimpson);

// Objetos 2 con destructuración
let simpson = {
	firstName: 'Homer',
	lastName: 'Simpson',
	age: 50,
	gender: 'M'
}

let { age, ...restOfTheDetails } = details;
console.log(age, restOfTheDetails);
```
