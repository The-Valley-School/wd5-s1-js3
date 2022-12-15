### array.map()

¿Cómo sacamos un listado de las edades de los personajes?


```jsx
let simpson = [
	{age: 50, name:'Homer'},
	{age: 50, name:'Marge'},
	{age: 10, name:'Bart'},
	{age: 8, name:'Lisa'},
];
```
 

La primera opción que se nos ocurre es usando un bucle


```jsx
let simpsonList = [
	{age: 50, name:'Homer'},
	{age: 50, name:'Marge'},
	{age: 10, name:'Bart'},
	{age: 8, name:'Lisa'},
];

let simpsonAges = [];
 
simpsonList.forEach((simpson) => simpsonAges.push(simpson.age));
console.log(simpsonAges);
```


Otra opción es usando el **map**


```jsx
let simpsonList = [
	{age: 50, name:'Homer'},
	{age: 50, name:'Marge'},
	{age: 10, name:'Bart'},
	{age: 8, name:'Lisa'},
];

let simpsonAges = simpsonList.map(simpson => simpson.age);
```


### array.filter()

¿Qué pasa si ahora solo queremos aquellos personajes del array que tengan 50 años?
 

```jsx
let simpsonList = [
	{age: 50, name:'Homer'},
	{age: 50, name:'Marge'},
	{age: 10, name:'Bart'},
	{age: 8, name:'Lisa'},
];

let simpsonAges = simpsonList.filter(simpson => simpson.age === 50);
console.log(simpsonAges);
```
 

### array.find()

Este método devuelve el primer elemento del array que cumple la función.
 

```jsx
let simpsonList = [
	{age: 50, name:'Homer'},
	{age: 50, name:'Marge'},
	{age: 10, name:'Bart'},
	{age: 8, name:'Lisa'},
];

let simpsonAges = simpsonList.find(simpson => simpson.age === 50);
console.log(simpsonAges);
```
 

### array.reduce()

***.reduce()*** también ejecuta una devolución de llamada para cada elemento de un *array*. Lo diferente aquí es que reduce el resultado de esta devolución de llamada (el acumulador) de un elemento del *array* a otro.
 

```jsx
let simpsonList = [
	{age: 50, name:'Homer'},
	{age: 50, name:'Marge'},
	{age: 10, name:'Bart'},
	{age: 8, name:'Lisa'},
];

//vamos a sumar todos los años de la familia
let simpsonAges = simpsonList.reduce( (contador, simpson) => contador+simpson.age,0);
console.log(simpsonAges);

//vamos a buscar el más joven
let youngSimpson = simpsonList.reduce( function(youngest, simpson){
    return (youngest.age === undefined || youngest.age >= simpson.age) ? simpson : youngest;
},{});
console.log(youngSimpson);

```
 

Vamos a juntar todo ahora:

Objetivo obtener la puntuación total de los pilotos de fórmula uno que conducen un ferrari


```jsx
let drivers = [ 
	{ id: 1, name: "Verstappen", score: 391, car:"red bull", plusScore: 40}, 
	{ id: 1, name: "Leclerk", score: 267, car:"ferrari", plusScore: 10}, 
	{ id: 1, name: "Perez", score: 265, car:"red bull",  plusScore: 50}, 
	{ id: 1, name: "Russell", score: 218, car:"mercedes",  plusScore: 30}, 
	{ id: 1, name: "Sainz", score: 202, car:"ferrari",  plusScore: 25}, 
	{ id: 1, name: "Hamilton", score: 198, car:"mercedes",  plusScore: 40}, 
];

// Primero filtramos por coche
let ferrariDrivers = drivers.filter(driver => driver.car === 'ferrari' );

// Sacamos la puntuación de los pilotos
let ferrariDriversScore = ferrariDrivers.map(driver => driver.score + driver.plusScore);

// Sumamos
let totalScoresFerrari = ferrariDriversScore.reduce( (acc,score) => acc + score);

console.log(totalScoresFerrari);

//Podemos rizar el rizo y hacerlo en una línea

let totalScoresFerrari = drivers
	.filter(driver => driver.car === 'ferrari')
	.map(driver => driver.score + driver.plusScore)
	.reduce( (acc,score) => acc + score);
```