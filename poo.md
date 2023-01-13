A lo largo de estos videos aprendiendo Javascript estamos enfocando el aprendizaje a un paradigma de programación que denominamos ‘Programación funcional’ basando y enfocando nuestro código en las acciones que queremos realizar. 

Sin embargo hay otros paradigmas de programación como la POO, muy utilizado en Java. Es un paradigma que se enfoca en el uso de objetos y la encapsulación de datos y objetos. Javascript no es un lenguaje orientado a objetos pero podemos simular esta forma de programación.

Vamos a ver como, llegado el momento, podríamos trabajar con este paradigma en Javascript.

A partir de ECMAScript 6, JavaScript introdujo la sintaxis de clases, la cual proporciona una manera más clara y estructurada de crear objetos y establecer herencia. Una clase es una plantilla para crear objetos. La sintaxis básica es la siguiente:

```jsx
class Vehiculo {
    constructor(marca, modelo, ano) {
        this.marca = marca;
        this.modelo = modelo;
        this.ano = año;
    }
    arrancar() {
        console.log("Vehículo arrancado");
    }
}
```

 **Acordaros de la palabra **this**. Es una palabra reservada y que sirve como herramienta que nos permite referenciar un objeto desde una función, es decir, acceder a los valores y propiedades de dicho objeto.*

En este ejemplo, creamos una clase "Vehículo" con un constructor y un método "arrancar". El constructor es un método especial que se ejecuta al crear un nuevo objeto a partir de la clase.

Un método es una función que se encuentra dentro de un objeto o clase y que se utiliza para representar el comportamiento de ese objeto o clase. Los métodos tienen acceso a las propiedades del objeto o clase en el que se encuentran y pueden modificarlas o utilizarlas para realizar una acción específica. 

```jsx
let vehiculo1 = new Vehiculo("Audi", "A1", 2010);
console.log(vehiculo1.marca); 
vehiculo1.arrancar(); 
```

La herencia es un mecanismo que permite crear una clase a partir de otra clase existente. El objetivo es reutilizar código y evitar la duplicación de esfuerzo. En javascript se puede crear herencia utilizando la palabra clave "extends"

```jsx
class Camion extends Vehiculo {
    constructor(marca, modelo, ano, carga) {
        super(marca, modelo, ano);
        this.carga = carga;
    }
    cargar(peso) {
        console.log('Peso total de cargado: ' + peso);
    }
}

let camion1 = new Camioneta("Renault", "Kangoo", 1990, 1000);
console.log(camion1.marca); // imprime "Chevrolet"
camion1.arrancar(); 
camion1.cargar(200);

```

En este ejemplo, creamos una clase "Camioneta" que hereda de la clase "Vehículo". La clase "Camioneta" tiene un constructor adicional que recibe una capacidad de carga. También tiene un método adicional llamado "cargar" que permite cargar un peso específico. La palabra clave "super" se utiliza dentro del constructor de la clase hija para llamar al constructor de la clase padre y así poder heredar sus propiedades y métodos.

En resumen, la POO en JavaScript permite crear objetos y establecer relaciones de herencia entre ellos mediante la utilización de clases. Las clases proporcionan una sintaxis más clara y estructurada para crear objetos y establecer herencia. Los objetos creados a partir de una clase tienen propiedades y métodos que representan su estado y comportamiento, respectivamente. La herencia permite reutilizar código y evitar la duplicación de esfuerzo al crear una clase a partir de otra clase existente.
