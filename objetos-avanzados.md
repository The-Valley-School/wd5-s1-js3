Como ya hemos visto en anteriores sesiones, los objetos son utilizados para almacenar colecciones de varios datos que se agrupan dentro de una semántica principal. 

Vamos en este video a seguir profundizando con ellos. La definición, el acceso y la modificación de objetos la tenemos controlada (por si acaso la repasamos) así que veremos una serie de nuevos conceptos sobre los objetos.


### Propiedades calculadas

Podemos crear una clave de un objeto a partir de una variable o un literal.


```jsx
let item = 'zapatillas';

let shoppingCart = {
  [item]: 10
};

console.log(shoppingCart.zapatillas);
```


Estos corchetes dan un plus de funcionalidad ya que podemos trabajar realizando operaciones con ellos


```jsx
let item = 'zapatillas';

let shoppingCart = {
  [item + 'Adidas']: 10
};

console.log(shoppingCart.zapatillasAdidas);
```


### Reducción de propiedades

A la hora de trabajar con objetos, normalmente usamos variables como valores de los nombres de esas propiedades por lo que podemos simplificar todo el proceso.


```jsx
function loginTeacher(name, password) {
  return {
    name: name,
    password: password
  };
}

let teacher = loginTeacher("Edu", 'TV2022');
console.log(teacher.name);

//Podríamos usar esto:

function loginTeacher(name, password) {
  return {
    name,
    password
  };
}

let teacher = loginTeacher("Edu", 'TV2022');
console.log(teacher.name);

//Incluso lo podemos combinar

function loginTeacher(name) {
  return {
    name: name,
    password: 'AAAA'
  };
}

let teacher = loginTeacher("Edu");
console.log(teacher.name);
```


### Comprobación de propiedades

A la hora de trabajar con objetos también es interesante saber si existe o no una propiedad con el fin de poder acceder a ella

A diferencia de otros lenguajes, JS nos devuelve ‘undefined’ si accedemos a una propiedad que no existe por lo que es muy fácil hacer la comprobación


```jsx

let shoppingCart = {
	 zapatillas: 10,
};

console.log(shoppingCart.zapatillas === undefined);
```
 

A demás de poder hacerlo utilizando la comprobación con el undefined podemos trabajar con un operador especial, es el operador **in**

 
```jsx
let shoppingCart = {
	 zapatillas: 10,
};

console.log('zapatillas' in shoppingCart);
console.log('pantalones' in shoppingCart);
```


Por lo general, no habría problema en usarlos indistintamente, pero puede darse el caso, en el que undefined no nos esté contestando como queremos.


```jsx
let shoppingCart = {
	 zapatillas: undefined,
};

console.log(shoppingCart.zapatillas === undefined);
```
 

Con esta propiedad hemos visto que existe el bucle **for…in** que nos permite recorrer todas las claves en un objeto.