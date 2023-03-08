# **JAVASCRIPT**

La documentacion oficial de W3 es: [w3schools.com](https://www.w3schools.com/js/js_arrays.asp "javascript")

# **VARIABLES**

1. # **let**

   Se puede redeclarar un LET en bloques distintos, pero no en el mismo bloque

   ```javascript
   let x = 2; // Allowed
   {
      let x = 3; // Allowed
   }
   {
      let x = 4; // Allowed
   }
   ```

   <br>

   ## **IMPORTANTE**

   ```javascript
   let x; // declarar
   x = 5; // asignar valor e inicializar

   let x = 5; // declarar, asignar valor e inicializar
   ```

   <br>
   <br>

2. # **const**

   Puede ser usada para crear objetos

   ```javascript
   const x = 10;
   // Here x is 10
   {
      const x = 2;
      // Here x is 2
   }
   // Here x is 10
   ```

   <br>

   > Una variable declarada fuera de una función, se convierte en GLOBAL

   ```javascript
   let carName = "Volvo";
   // code here can use carName

   function myFunction() {
      // code here can also use carName
   }
   ```

   ```javascript
   let carName = "Volvo";
   myFunction();

   function myFunction() {
   document.getElementById("demo").innerHTML = "I can display " + carName; // esta declarando la variable carName
   ```

   <br>

   > En JS los object y las function are also variables

   <br>

   Si se le asigna un valor a una variable que NO a sido DECLARADA, automaticamente se convertira en variable global.

   -  En este ejemplo se convierte **AUTOMATICAMENTE** en una **variable global** **carName** al invocar la funcion que la contendrá lineas despues **"myFunction()"**, even si su valor es asignado lineas abajo en **myFunction()**

   ```javascript
   myFunction(); // HOISTING

   // code here can use carName as a global variable
   document.getElementById("demo").innerHTML = "I can display " + carName; // carName is global scope

   function myFunction() {
      carName = "Volvo"; //recien se le asigna un valor a carName, pero como se invocó la funcion arriba, la hace variable global
   }
   ```

   Debido al **_HOISTING JS_** una funcion se puede invocar antes de ser declarada y no arrojará un error. En este ejm invoco a **myFunction** la cual contiene una variable **carName** la cual lineas abajo se le asigna un valor **volvo** , pero como **myFunction** ya fue invocada arriba de todo, hace que **carName** se convierta en una **VARIABLE GLOBAL** . Pero no es recomendable invocar la funcion sin haberla declarado, ya que podria generar confusion

   <br>

   -  **En strict mode las variables _NO_ declaradas no son automaticamente globales**

   -  En JS el global scope es solo en JS

   -  En HTML el global scope es el window object

   <br>
   <br>

3. # **OPERADORES**

   Primero se **DECLARA** la variable y se le **ASIGNA** un **VALOR**, en la segunda sentencia, se le asigna la operacion que quieren hacer

   ```javascript
   let x = 5; // x=5
   x++; // =x+1     x=6
   let z = x; // z=x=6
   ```

   <br>

   ```javascript
   x += 5; //es como decir x = x+5, aumenta en el valor que le des
   ```

   ```javascript
   x -= 2; //(x = x-2, disminuye el valor que le das) (lo mismo con el resto de operadores)
   ```

   <br>

   ```javascript
   let text1 = "hola ";
   text1 += "como estas"("hola como estas");
   ```

   <br>

   ```javascript
   == //igual a
   === //igual valor y tipo
   != //no es igual
   !== //no es igual en valor ni tipo
   !(x==y) // x no es igual a y
   >=     =<   //mayores y menores
   ~x // niega una variable
   ? //operador ternario
   let x = 100 / 50 * 3;       //de IZQUIERDA a DERECHA
   ```

   <br>
   <br>

# **TIPOS DE DATOS DE JAVASCRIPT**

Una variable puede contener cualquier tipo de datos

1. # **STRING ("" ó '')**

   Empieza con la posicion CERO.

   <br>

   Almacena CERO o más valores de texto entre "" ó ''.

   <br>

   Para escribir comillas en un string se usa \

   ```javascript
   let text = 'We are the so-called "Vikings" from the north.'; //lo mismo con ' y \
   ```

   ```javascript
   let longitud = text.length; //la propiedad length dice cuanto es la longitud de un string
   ```

   <br>
   <br>

   1. ## **METODOS STRING**

      ```javascript
      let ejemplo = "Soy una cadena de texto, utilizada para el ejemplo";
      ```

      <br>

      **slice(start,end)**: extrae parte del string en un nuevo string, no incluye el ultimo caracter "end"

      ```javascript
      let part = ejemplo.slice(7, 13);
      ```

      <br>

      **substring(start,end)**: igual que slice, pero los valores negativos seran tomados como CERO.

      <br>

      **substr(start,lenth)**: igual que slice, pero el 2do valor toma el largo de lo que vas a extraer.

      <br>

      **replace("cambiar","nuevo")**: devuelve una nueva cadena, no cambia la cadena llamada, solo cambia una palabra

      ```javascript
      let text = "Please visit Microsoft!";
      let newText = text.replace("Microsoft", "W3Schools");
      ```

      **replaceAll()**

      <br>

      **toUpperCase()** todo el string se convierte en mayusculas, en una nueva .

      <br>

      **toLowerCase()** todo el string se convierte en minusculas, en una nueva.

      ```javascript
      let text1 = "Hello World!";
      let text2 = text1.toUpperCase();
      ```

      <br>

      **concat()**: une más cadenas, en una nueva

      ```javascript
      let text1 = "Hello";
      let text2 = "World";
      let text3 = text1.concat(" ", text2);
      ```

      <br>

      **trim()**: elimina los espacios en blanco

      ```javascript
      let text1 = "      Hello World!      ";
      let text2 = text1.trim(); //result = "Hello World!"
      ```

      <br>

      **padStart(veces+1,texto) y padEnd()**: permite rellenar STRING desde con texto, las veces que sean establecidas ya sea al inicio o al final

      ```javascript
      let text = "5";
      let padded = text.padStart(4, "0"); //result: 0005
      ```

      <br>

      **chartAt(posicion)**: extrae el valor del STRING segun la posicion dada

      ```javascript
      let text = "HELLO WORLD";
      let char = text.charAt(0); //result: H
      ```

      _en ECMAScript5 se hacía con []_

      ```javascript
      let text = "HELLO WORLD";
      let char = text[0]; //result: H
      ```

      _la diferencia es que con [] devuelve UNDEFINED, mientras que chatAt() devuelve una cadena vacia ""_

      <br>

      **split()**: convierte un STRING en un ARRAY

      ```javascript
      let text = "How are you doing today?";
      const myArray = text.split(" "); //result: ["How","are","you","doing","today?"]
      let what = myArray[2]; //result: "you"
      ```

      <br>
      <br>

      1. ## **METODOS DE BUSQUEDA STRINGS**

         Precisa las mayusculas y minusculas con exactitud.
         **indexof(texto)**: devuelve la posicion del primer texto que coincida con el parametro

         ```javascript
         let str = "Please locate where 'locate' occurs!";
         let result = str.indexOf("locate"); //result: 7
         ```

         <br>

         **lastIndexOf()**, es lo mismo solo que desde atrás. _Ambos llevan un segundo parametro el cual sería la posicion A PARTIR donde empezaria la busqueda_

         <br>

         **includes(texto)**: devuelve true o false si existe o no el texto del parametro

         ```javascript
         let text = "Hello world, welcome to the universe.";
         let result = text.includes("world"); //result: true
         ```

         Tambien puede tener otro parametro, el cual indica si la palabra comienza en determinada posicion.

         ```javascript
         let result = text.includes("world", 12); //result: false
         ```

         <br>

         **startWith(texto), endWith(texto)**: devuelve true o false si un STRING empieza o acaba con el texto dado (tambien se puede dar una posicion como segundo parametro)

         ```javascript
         let text = "John Doe";
         let result = text.endsWith("Doe"); //result: true
         ```

         <br>
         <br>

      ## **NOMBRAR VARIABLES EN STRING** **(${name})**

      Para hacer eso es necesario usar back-tics (``) en lugar de (""). Dentro de los `, podemos usar variables, "" y ''.

      ```javascript
      let firstName = "John";
      let lastName = "Doe";
      let result = `Welcome ${firstName}, ${lastName}!`; //result: Welcome John, Doe!

      let price = 10;
      let VAT = 0.25;
      let total = `Total: ${(price * (1 + VAT)).toFixed(2)}`;
      ```

      <br>
      <br>

      ## HTML TEMPLATES

      ```javascript
      let header = "Templates Literals"; //string
      let tags = ["template literals", "javascript", "es6"]; //array

      let html = `<h2>${header}</h2><ul>`; //por uso de back-tics se puede invocar la variable HEADER y usar elementos HTML en este STRING

      for (const x of tags) {
         //luego dice que por cada array de TAGS
         html += `<li>${x}</li>`; //añada a la variable HTML una lista con el contendio de la const x que hace referencia a los arrays de TAGS
      }

      html += `</ul>`; //por ultimo le dice a la variable HTML que le añada el ELEMENTO de cierre UL
      ```

      <br>
      <br>

2. # **NUMBER**:

   > max cifras de un valor entero: 15 , de decimales: 17).

   <br>

   > NaN significa "no es un número", resulta de forzar operaciones con números. Por ejm: 100/"Apple" / typeof NaN es number.

   <br>

   > infinity o -infinity, tambien resulta de un número entre CERO. typeof infinity es number.

   <br>

   > no escribir numero que empiecen con CERO como 08, ya que sera tomado como numeros octales.

   <br>

   **toString(baseDeseada)**: convierte un número en base 10 a la base que se use como parametro

   ```javascript
   let number = 32;
   let result = number.toString(8); //result: 40, 32 en base 8
   ```

   Tambien se pueden crear objetos númericos con la palabra new, pero no es recomendado.

   ```javascript
   let x = 123;
   let y = new Number(123);
   ```

   <br>
   <br>

   1. ## **METODOS NUMBER**

      **toString()** : toString sin parametro devuelve el número en STRING.

      ```javascript
      let x = 123; //x: number
      let y = x.toString(); //convert x to string
      console.log(y); //result: 123
      console.log(typeof y); //result: string
      ```

      **toFixed(posicion)**: redondea el numero a partir de la posicion dada

      ```javascript
      let x = 9.656;
      x.toFixed(0); //result: 10
      x.toFixed(2); //result: 9.66 (ideal para dinero)
      ```

      <br>
      <br>

   2. ## **METODOS GLOBALES PARA CONVERTIR NUMEROS DE JAVASCRIPT**

      **Number(string,boolean,etc)**: convierte variables en numeros

      ```javascript
      Number(true); //1
      Number(false); //0
      Number("10"); //10
      Number("  10"); //10
      Number("10  "); //10
      Number(" 10  "); //10
      Number("10.33"); //10.33
      Number("10,33"); //NaN
      Number("10 33"); //NaN
      Number("John"); //NaN
      ```

      Tambien convierte fechas en numeros _en milisegundos_, a partir de esa fecha, desde antes sale CERO.

      ```javascript
      let x = new Date("1970-01-02");
      Number(x); //result: 86400000
      ```

      **ParseInt()**: analiza el STRING y devuelve un numero entero, solo devuelve el 1er numero

      ```javascript
      parseInt("-10"); //-10
      parseInt("-10.33"); //-10
      parseInt("10"); //10
      parseInt("10.33"); //10
      parseInt("10 20 30"); //10
      parseInt("10 years"); // 10
      parseInt("years 10"); //NaN
      ```

      <br>
      <br>

3. # **BigInt**

   > Se utiliza para almacenar valores enteros grandes, para utilizar BigInt se debe poner una n al final del número o escribir el metodo BigInt.

   > BigInt no tiene decimales.

   ```javascript
   let x = 1234567890123456789012345n;
   let y = BigInt(1234567890123456789012345)

   (se pueden usar operaciones aritmeticas)
   let x = 9007199254740995n;
   let y = 9007199254740995n;
   let z = x * y;
   ```

4. ## Booleano _True and False_
5. ## Undefined
6. ## Nule
7. ## Simbolo
8. ## Objeto

<br>

# TIPOS DE DATOS DEL OBJETO

1. ## Un objeto
   {propiedad:valor,}
2. ## Una matriz
   ["",3,"abc"]
3. ## Una fecha

<br>
<br>

# **TIPOS DE DATOS DE JAVASCRIPT que pueden CONTENER VALORES**

      String.

      Number.

      Boolean.

      Object {propiedad:valor,}.

      function: function name(){}.

   <br>

# **TIPOS DE DATOS que NO pueden CONTENER VALORES**

    null
    undefined

# TIPOS DE OBJETOS

      Object {propiedad:valor,}.

      Date.

      Array.

      String.

      Number.

      Boolean.

<br>
<br>

# **FUNCTION**

> Una variable declarada fuera de una función, se convierte en **GLOBAL**.

> En JS los object y las function are also variables

En JS algunas funciones no pertenecen a objetos, pero en JS siempre hay un objeto global predeterminado. En HTML seria la pagina HTML, por lo que esas funciones pertenecerian a la pagina HTML. En un navegador, pertenece al objeto window

Si se le asigna un valor a una variable que NO a sido DECLARADA, automaticamente se convertira en variable global.

<br>

**_Sintaxis_**

```javascript
function myFunction(a, b) {
   // declara la function
   return a * b;
}
myFunction(2, 3); // invoca, llama, ejecuta, inicializa la function
```

<br>

-  Si se le asigna un valor a una variable que NO a sido DECLARADA, automaticamente se convertira en variable global.

```javascript
let a = 4;
function myFunction() {
   return a * a;
} // la function esta accediendo a la variable global a
```

-  Las variables declaradas sin const o let, siempre serán globales incluso si estan dentro de una function

```javascript
function myFunction() {
   a = 4;
} // a es una variable global
```

-  Todas las funciones tienen acceso sobre ellas, por ejemplo en una funcion dentro de una function

```javascript
function add() {
   let counter = 0;
   function plus() {
      counter += 1;
   } // plus puede usar la variable counter que esta encima de ella y pertenece a la function add()
   plus();
   return counter;
}
```

-  En este ejemplo se convierte **AUTOMATICAMENTE** en una **variable global** **carName** al invocar la funcion que la contendrá lineas despues **"myFunction()"**, even si su valor es asignado lineas abajo en **myFunction()**

```javascript
myFunction(); // HOISTING

// code here can use carName as a global variable
document.getElementById("demo").innerHTML = "I can display " + carName; // carName is global scope

function myFunction() {
   carName = "Volvo"; //recien se le asigna un valor a carName, pero como se invocó la funcion arriba, la hace variable global
}
```

Debido al **_HOISTING JS_** una funcion se puede invocar antes de ser declarada y no arrojará un error. En este ejm invoco a **myFunction** la cual contiene una variable **carName** la cual lineas abajo se le asigna un valor **volvo** , pero como **myFunction** ya fue invocada arriba de todo, hace que **carName** se convierta en una **VARIABLE GLOBAL** . Pero no es recomendable invocar la funcion sin haberla declarado, ya que podria generar confusion

<br>

> Los argumentos en funciones **(parametros)** funcionan como variables **LOCALES**, que se eliminan una vez terminada la funcion.

<br>

**function name (parametro1, parametro2)**{}
_se usa **RETURN** cuando se quiere devolver un **VALOR** a la funcion que la invoca_

-  Tipos de datos que almacenan valores: string, number, boolean, object y function

```javascript
let x = myFunction(4, 3); // Function is called, return un valor que terminará en la variable X
function myFunction(a, b) {
   return a * b; // Function returns the product of a and b
}

function toCelsius(f) {
   return (5 / 9) * (f - 32);
}
toCelsius();
// si se llama a la funcion sin el (), la funcion mostrará el objeto
```

> **Las variables dentro de un funcion es local, puede ser reinvocada en otra funcion o fuera de ella, pero no tendrá nada que ver con la variable dentro de la funcion**

<br>
<br>

# **FUNCION EN VARIABLE**

Una funcion en JS se puede definir como una expression, y esta se puede almacenar en una variable, se recomienda usar **_const_**

```javascript
const x = function (a, b) {
   return a * b;
};
```

<br>

Como la expresion se almacenó en una variable, esta variable se puede usar como una function, estas son tambien llamadas **_funciones anonimas_**

```javascript
const x = function (a, b) {
   return a * b;
};
document.getElementById("demo").innerHTML = x(4, 3); // invoca la funcion anonima x con los argumentos 4 y 3
```

-  Las functions definidas meditante una variable **_(anonymous function)_** , no cumplen con **_HOISTING_**

<br>

-  Las funciones tambien se pueden usar como valores, almacenados en variables

```javascript
function myFunction(a, b) {
   return a * b;
}
let x = myFunction(4, 3) * 2; // x = 24
document.getElementById("demo").innerHTML = x;
```

# **ARROW FUNCTION**

Establecen una sintaxis más corta

NO permite el **_HOISTING_**

```javascript
let myFunction = (a, b) => a * b;
console.log(4, 5); // 20
```

```javascript
let hello = "";

hello = function () {
   return "Hello World!";
};
```

```javascript
let hello = "";

hello = () => {
   return "Hello World!";
};
```

_Ambas son iguales_

<br>

-  Pero si la funcion tiene **UNA SOLA DECLARACION** y la declaracion devuelve **UN VALOR**, puede quitar los corchetes y el keyword **return**

```javascript
hello = () => "Hello World!";
```

<br>

-  Si tiene parametros va dentro del parentesis

```javascript
hello = (val) => "Hello " + val;
```

<br>

-  Si solo tiene un parametro va sin parentesis

Con las arrow functions la keyword **this** SIEMPRE representa el objeto que definió la arrow function

```javascript
let hello = "";

hello = function () {
   document.getElementById("demo").innerHTML += this;
}; // regular function

//The window object calls the function:
window.addEventListener("load", hello);

//A button object calls the function:
document.getElementById("btn").addEventListener("click", hello);
// result: [object Window][object HTMLButtonElement]
```

```javascript
let hello = "";

hello = () => {
   document.getElementById("demo").innerHTML += this;
}; //arrow function

//The window object calls the function:
window.addEventListener("load", hello);

//A button object calls the function:
document.getElementById("btn").addEventListener("click", hello);
// result: [object Window] [object Window]
```

<br>
<br>

# **PARAMETROS PREDETERMINADOS**

Cuando se declara una funcion se ponen una cantidad x de parametros, si cuando se invoca la funcion falta uno de esos parametros, JS lo determina como **undefined** , para eso hay que poner parametros predefinidos dentro de la function

```javascript
function myFunction(x, y) {
   if (y === undefined) {
      y = 2; // parametro predeterminado
   }
   return x * y;
}
```

<br>

```javascript
function myFunction(x, y = 10) {
   // y = predeterminado
   return x + y;
}
myFunction(5);
```

<br>

## **PARAMETRO REST**

(...) permite que una function contenga innumerables argumentos como un array

```javascript
function sum(...args) {
   let sum = 0;
   for (let arg of args) sum += arg;
   return sum;
} // para cada elemento de args sucederá que la variable sum se sumará con uno de ellos, retornando el valor final de sum

let x = sum(4, 9, 16, 25, 29, 100, 66, 77);

document.getElementById("demo").innerHTML = x;
// 326
```

-  Para encontrar o realizar algo con una function que tiene sus argumentos como arrays es que existe **objeto arguments** , el cual contiene todos los argumentos utilizados cuando se invocó la function

```javascript
x = findMax(1, 123, 500, 115, 44, 88);

function findMax() {
   let max = -Infinity;
   for (let i = 0; i < arguments.length; i++) {
      if (arguments[i] > max) {
         max = arguments[i];
      }
   }
   return max;
} // encuentra el maximo de argumentos que se invocaron que sean mayor a -Infinity
```

```javascript
x = sumAll(1, 123, 500, 115, 44, 88);

function sumAll() {
   let sum = 0;
   for (let i = 0; i < arguments.length; i++) {
      sum += arguments[i];
   }
   return sum;
} // la variable sum aumentará su valor con cada argumento invocado y sera retornada
```

# **OBJETOS**

> Todos los objetos tienen el metodo toString()

-  **Todos los valores de JavaScript, excepto los primitivos, son objetos.**

-  Las fechas son siempre objetos.

-  Las matemáticas son siempre objetos.

-  Las expresiones regulares son siempre objetos.

-  Los arreglos son siempre objetos.

-  Las funciones son siempre objetos.

-  Los objetos son siempre objetos.

> **_Un valor primitivo es un valor que no tiene propiedades ni metodos: string, number, boolean, null, undefined, symbol y bigint_**

<br>

Las variables pueden contener valores `let x = "Hola"`,los objetos son variables, pero los objetos pueden contener muchos valores. Se declaran por lo general con **const**

```javascript
const car = { type: "Fiat", model: "500", color: "white" };
```

<br>

> Para acceder a los valores de los objetos se hace de 2 formas

```javascript
/* objectName.propiedad */ cars.model;
/* objectName[propiedad] */ cars[model];
```

<br>

> Añadir PROPIEDADES a un objeto

```javascript
car.nationality = "English";
```

<br>

> Borrar PROPIEDADES a un objeto

```javascript
const person = {
   firstName: "John",
   lastName: "Doe",
   age: 50,
   eyeColor: "blue",
};

delete person.age; // tambien borra el valor
```

**delete** solo se puede usar en propiedades de objetos, no en variables o funciones

Las propiedades de los objetos pueden ser valores primitivos, otros objetos y funciones

Cuando se declara una variable con la palabra **"new"**, la variable se crea como objeto.

```javascript
let x = new String("John"); // Declares x as a String object (x es un objeto)
let y = new Number(55); // Declares y as a Number object (y es un objeto)
z = new Boolean(); // Declares z as a Boolean object
```

Evitar los objetos tipo string, number y boolean porque RALENTIZAN la velocidad de la ejecucion y complican el codigo.

<br>

La comparación de dos objetos de JavaScript siempre devuelve falso . ==,===

Los **metodos** son funciones dentro de un objeto, **en el valor de una propiedad**.

<br>
<br>

## **COMO CRER UN OBJETO**

Existen diversas entre las cuales son:

-  Por un objeto literal

```javascript
const person = {
   firstName: "John",
   lastName: "Doe",
   age: 50,
   eyeColor: "blue",
};
```

```javascript
const person = {};
person.firstName = "John";
person.lastName = "Doe";
person.age = 50;
person.eyeColor = "blue";
```

<br>

-  Por medio de new Object() - [NO RECOMENDADO]

```javascript
const person = new Object();
person.firstName = "John";
person.lastName = "Doe";
person.age = 50;
person.eyeColor = "blue";
```

<br>

-  Por medio de constructores - class

<br>

-  Y Usando Object.create() - [NO RECOMENDADO]

Los objetos son mutables, si person es un objeto, `const x = person;` No creará una copia de person, será el mismo objeto person

<br>
<br>

## **OBJETOS ANIDADOS**

Los valores de un objeto pueden ser otro objeto

```javascript
myObj = {
   name: "John",
   age: 30,
   cars: {
      car1: "Ford",
      car2: "BMW",
      car3: "Fiat",
   },
}; // myObj.car.car2 = BMW
```

Los valores de los objetos pueden ser matrices y los valores de los arrays pueden ser objects

```javascript
const myObj = {
   name: "John",
   age: 30,
   cars: [
      { name: "Ford", models: ["Fiesta", "Focus", "Mustang"] },
      { name: "BMW", models: ["320", "X3", "X5"] },
      { name: "Fiat", models: ["500", "Panda"] },
   ],
};
```

Para acceder a los arrays dentro de arrays, se usa for in para cada array

```javascript
let x = ""; // variable que almacenará todo en un parrafo
const myObj = {
   name: "John",
   age: 30,
   cars: [
      { name: "Ford", models: ["Fiesta", "Focus", "Mustang"] },
      { name: "BMW", models: ["320", "X3", "X5"] },
      { name: "Fiat", models: ["500", "Panda"] },
   ],
};

for (let i in myObj.cars) {
   // i recorre las propiedades del array cars
   x += "<h2>" + myObj.cars[i].name + "</h2>"; // x almacena los valores de name
   for (let j in myObj.cars[i].models) {
      // j recorre las propiedades del array models
      x += myObj.cars[i].models[j] + "<br>"; // x almacena los valores de models
   }
}
```

<br>

<br>

## **MOSTRAR UN OBJETO EN JS**

Cuando un objeto es llamdo por `console.log(object)`, la consola muestra sus propiedades y valores. Pero cuando se muestra en HTML, arroja **[object Object]** , para eso existen diversas maneras para mostrar un objeto

-  Sus properties se pueden mostrar como strings

```javascript
const person = {
   name: "John",
   age: 30,
   city: "New York",
};

document.getElementById("demo").innerHTML = person.name + "," + person.age + "," + person.city;
```

<br>

-  Por medio de un loop

```javascript
const person = {
   name: "John",
   age: 30,
   city: "New York",
};

let txt = "";
for (let x in person) {
   txt += person[x] + " ";
}

document.getElementById("demo").innerHTML = txt;
```

<br>

-  Cualquier objeto se puede convertir en un array usando **_Object.values()_** (Los ARRAYS SI se pueden MOSTRAR)

```javascript
const person = {
   name: "John",
   age: 30,
   city: "New York",
};

const myArray = Object.values(person);
// Ahora myArray ya es un array para mostrar
// result: John,30,New York
```

<br>

-  Cualquier OBJETO en JS se puede convertir en string con la function JSON.stringify(), y para pasar de string a object (viceversa) se usa JSON.parse()

```javascript
const person = {
   name: "John",
   age: 30,
   city: "New York",
};

let myString = JSON.stringify(person);
// result: {"name":"John","age":30,"city":"New York"} es un string, pero siguiendo la notacion JSON
```

<br>

JSON.stringify() tambien convierte date a string

```javascript
const person = {
   name: "John",
   today: new Date(), // object Date
};

let myString = JSON.stringify(person);
document.getElementById("demo").innerHTML = myString;
// {"name":"John","today":"2023-03-02T22:21:56.742Z"}
```

<br>

Pero JSON.stringify() no funciona con functions

```javascript
const person = {
   name: "John",
   age: function () {
      return 30;
   },
};

let myString = JSON.stringify(person);
document.getElementById("demo").innerHTML = myString;
// solo retorna {"name":"John"}
```

<br>

Para eso podemos convertir la function en string usando toString()

```javascript
const person = {
   name: "John",
   age: function () {
      return 30;
   },
};
person.age = person.age.toString();

let myString = JSON.stringify(person);
document.getElementById("demo").innerHTML = myString;
// {"name":"John","age":"function () {return 30;}"}
```

<br>

-  Un array tambien se puede encadenar

```javascript
const arr = ["John", "Peter", "Sally", "Jane"];

let myString = JSON.stringify(arr);
document.getElementById("demo").innerHTML = myString;
// arr - John,Peter,Sally,Jane
// myString - ["John", "Peter", "Sally", "Jane"] en formato JSON
```

<br>

<br>

# **THIS KEYWORD**

Se refiere al objeto "person" que lo posee

`this.firstName` quiere decir que esta accediendo al valor de la propiedad firstName del objeto person.O la propiedad firstName del objeto "person". Asi como con cars.model, entonces `this.firstName = person.firstName`

```javascript
const person = {
   firstName: "John",
   lastName: "Doe",
   id: 5566,
   fullName: function () {
      return this.firstName + " " + this.lastName;
   },
};
```

<br>

> **this** "solo" se refiere al global object // objeto window

```javascript
let x = this;
console.log(x); //return : [object Window]
```

<br>

> En una función, this se refiere al objeto global.

```javascript
function myFunction() {
  return this;
  console.log(myFunction)  // [object Window]
  //pero si tiene "use strict" sale undefined
```

<br>

> En un evento, this se refiere al _elemento_ que recibió el evento.

```html
<button onclick="this.style.display='none'">Click to Remove Me!</button>
<!-- this hace referencia a button -->
```

<br>
<br>

# **CONSTRUCTOR DE OBJETOS**

Muchas veces es necesario tener un **_model_** para crear varios objetos del mismo tipo y para eso necesitaremos a las constructor functions

-  Los constructores son funciones que pueden crear objetos

<br>

-  Los objetos del mismo tipo se crean llamando a la constructor function con la keyword **new**

-  Se considera poner la 1ra letra en Upper Case a una function constructora

<br>

-  La keyword **this** no tiene valor en una constructor function, solo tomará el valor del objeto cuando se cree el nuevo objeto

```javascript
// Constructor function for Person objects
function Person(first, last, age, eye) {
   this.firstName = first;
   this.lastName = last;
   this.age = age;
   this.eyeColor = eye;
} // Person es la constructor function

// Create a Person object
const myFather = new Person("John", "Doe", 50, "blue");
const myMother = new Person("Sally", "Rally", 48, "green");

// Display age
document.getElementById("demo").innerHTML = "My father is " + myFather.age + ".";
```

<br>

-  Del mismo modo le puedo añadir propiedades al objeto creato

```javascript
myFather.nationality = "English"; // solo se lo añade a myFather
```

<br>

-  A su mismo tambien le puedo añadir metodos al objeto creado

```javascript
myFather.name = function () {
   return this.firstName + " " + this.lastName;
}; // le añado el metodo "name"
// solo se lo añade a myFather
```

<br>

> Pero **NO SE PUEDE** agregar del **MISMO MODO** metodos y propiedades al constructor, para hacerlo se tiene que añadir en el mismo constructor function

```javascript
function Person(first, last, age, eyecolor) {
   // añadio el valor de la propiedad como parametro, pero no el del metodo
   this.firstName = first;
   this.lastName = last;
   this.age = age;
   this.eyeColor = eyecolor; // añadio propiedad
   this.name = function () {
      return this.firstName + " " + this.lastName; // añadio metodo name
   };
}
```

<br>
<br>

# **PROTOTIPOS**

Todos los objects JS heredan sus properties y methods de un prototype

-  Los object Date heredan de Date.prototype

-  Los object Array heredan de Array.prototype

-  Los object Person heredan de Person.prototype

<br>

El `Object.prototype` está en la parte superior de la cadena de herencia del prototipo

Los objetos Date, Array y Person lo heredan de `Object.prototype`

<br>
<br>

> A veces queremos añadir propiedades o metodos a los constructor function o a **TODOS** los objetos existentes de un tipo determinado, para eso usamos la propiedad de JS **_prototype_**

```javascript
// con propiedades
function Person(first, last, age, eye) {
   this.firstName = first;
   this.lastName = last;
   this.age = age;
   this.eyeColor = eye;
}

Person.prototype.nationality = "English";

const myFather = new Person("John", "Doe", 50, "blue");
document.getElementById("demo").innerHTML = "The nationality of my father is " + myFather.nationality;
```

<br>

```javascript
// con metodos
function Person(first, last, age, eye) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eye;
}

Person.prototype.name = function() {
  return this.firstName + " " + this.lastName
};

const myFather = new Person("John", "Doe", 50, "blue");
document.getElementById("demo").innerHTML =
"My father is " + myFather.name();
</script>
```

<br>

# **OBJETOS CON STRICT MODE**

-  Estos metodos son para gestion de objetos

```javascript
// Create object with an existing object as prototype
Object.create();

// Adding or changing an object property
Object.defineProperty(object, property, descriptor);

// Adding or changing object properties
Object.defineProperties(object, descriptors);

// Accessing Properties
Object.getOwnPropertyDescriptor(object, property);

// Returns all properties as an array
Object.getOwnPropertyNames(object);

// Accessing the prototype
Object.getPrototypeOf(object);

// Returns enumerable properties as an array
Object.keys(object);
```

<br>

-  Estos para Protección de objetos

```javascript
// Prevents adding properties to an object
Object.preventExtensions(object);

// Returns true if properties can be added to an object
Object.isExtensible(object);

// Prevents changes of object properties (not values)
Object.seal(object);

// Returns true if object is sealed
Object.isSealed(object);

// Prevents any changes to an object
Object.freeze(object);

// Returns true if object is frozen
Object.isFrozen(object);
```

<br>

-  Para cambiar los metadatos

```javascript
writable: true; // Property value can be changed
enumerable: true; // Property can be enumerated
configurable: true; // Property can be reconfigured

// con FALSE no se puede cambiar
```

<br>

-  Ejemplo de Listado de todas las propiedades y de las enumerables

```javascript
// Create an object:
const person = {
   firstName: "John",
   lastName: "Doe",
   language: "EN",
};

// Change Property
Object.defineProperty(person, "language", { enumerable: false }); // no permite que la propiedad language sea contada

// Display Properties
document.getElementById("demo").innerHTML = Object.getOwnPropertyNames(person); // firstName,lastName,language
document.getElementById("demo").innerHTML = Object.keys(person); // firstName,lastName
```

<br>

-  Ejemplo para añadir propiedades

```javascript
// Create an object:
const person = {
   firstName: "John",
   lastName: "Doe",
   language: "EN",
};

// Add a property
Object.defineProperty(person, "year", { value: "2008" }); // al objeto person le añade la propiedad year con valor 2008
document.getElementById("demo").innerHTML = person.year;
// 2008
```

<br>

> **_Object.defineProperty()_** tambien se usa para agregar getters y setters

```javascript
// Define an object
const obj = { counter: 0 }; // define un obj con propierdad counter con valor CERO

// Define Setters and Getters
Object.defineProperty(obj, "reset", {
   get: function () {
      this.counter = 0;
   }, // obtiene la propiedad reset con el valor de counter, osea CERO
});
Object.defineProperty(obj, "increment", {
   get: function () {
      this.counter++;
   }, // crea la propiedad increment y cuyo valor counter aumentado en 1
});
Object.defineProperty(obj, "decrement", {
   get: function () {
      this.counter--;
   }, // crea la propiedad decrement y cuyo valor counter disminuido en 1
});
Object.defineProperty(obj, "add", {
   set: function (value) {
      this.counter += value;
   }, // establece propiedad add y cuyo valor counter será sumado con el valor de la propiedad add
});
Object.defineProperty(obj, "subtract", {
   set: function (value) {
      this.counter -= value;
   }, // crea la propiedad subtract y cuyo valor counter será restado con el valor de la propiedad subtract
});

// Play with counter:
obj.reset; // 0
obj.add = 5; // valor de la property add / +5
obj.subtract = 1; // valor de la property subtract / -1
obj.increment; // +1
obj.decrement; // -1
document.getElementById("demo").innerHTML = obj.counter;
// result: 4
```

# **EVENTOS**

Los eventos HTML son "cosas" que suceden en ELEMENTOS HTML, pueden ser algo que hace el usuario o algo que hace el navegador.

Se agregan atributos a elementos HTML por medio de los eventos.

Los atributos de eventos HTML pueden llamar a funciones de JavaScript.

```html
<button onclick="displayDate()">The time is?</button>
<script>
   function displayDate() {
      document.getElementById("demo").innerHTML = Date();
   }
</script>
<p id="demo"></p>
```

<br>
<br>

# **ARRAYS**

Una matriz es una **variable** especial, que puede contener **más de un valor** . _Se usa la palabra const_

Son objetos iterables

```javascript
const cars = ["Saab", "Volvo", "BMW"];
```

Sintaxis

```javascript
const array_name = [item1, item2, ...];
```

<br>

> También puede crear una matriz y luego proporcionar los elementos

```javascript
const cars = [];
cars[0] = "Saab";
cars[1] = "Volvo";
cars[2] = "BMW";
console.log(cars); //['Saab', 'Volvo', 'BMW']
```

Las matrices se declaran con _const_ y se le asigna un valor al inicializarla

```javascript
const cars = ["Volvo", "BMW"]; // Allowed
{
   const cars = ["Volvo", "BMW"]; // Allowed
}
{
   const cars = ["Volvo", "BMW"]; // Allowed
}
```

La palabra **new** tambien crea un array y le asigna valores

```javascript
const cars = new Array("Saab", "Volvo", "BMW");
console.log(cars); //['Saab', 'Volvo', 'BMW']
```

No hay necesidad de usar _new_, por simplicidad se utiliza el 1er metodo.

<br>

> Acceder a una matriz, los _indices_ de la matriz empiezan en _CERO_

```javascript
const cars = ["Saab", "Volvo", "BMW"];
let car = cars[0]; //result: Saab
```

<br>

> Cambiar el _elemento_ de una matriz

```javascript
const cars = ["Saab", "Volvo", "BMW"];
cars[0] = "Cambio";
console.log(cars[0]); //result: Cambio
```

<br>

Para acceder a la matriz entera, solo se hace referencia al nombre de la matriz

```javascript
const cars = ["Saab", "Volvo", "BMW"];
console.log(cars); //result:['Saab', 'Volvo', 'BMW']
```

<br>

Las matrices son objetos, al usar _typeof_ devuelve _object_.

En el caso de los arrays, usan los numeros para acceder a sus _elementos_.

En el caso de los objetos, usan los nombres de sus _propiedades_ para acceder a sus _valores o miembros_.

> Los matrices son tipos especiales de objetos, por eso pueden tener variables de diferentes tipos en _el mismo array_ . Puedes tener _objetos_ en un array, _funciones_ y _arrays_ dentro de un mismo array.

```javascript
myArray[0] = Date.now; //el 0 es una fecha
myArray[1] = myFunction; //it's a function
myArray[2] = myCars; //it's a object
```

<br>

La diferencia entre matrices y objetos

> En JavaScript, las matrices usan índices numerados .

> En JavaScript, los objetos usan índices con nombre .

_Las matrices son un tipo especial de objetos, con índices numerados._

**_Debe utilizar objetos cuando desee que los nombres de los elementos sean cadenas (texto) ._**

**_Debe utilizar matrices cuando desee que los nombres de los elementos sean números ._**

Como ya se dijo, se pueden crear matrices de 2 maneras y una de ellas es usando la _palabra clave_ **new**, estos 2 ejemplos crean matrices vacias

```javascript
const points = new Array(); //empty array
const points = []; //empty array
```

Estas 2 tambien son iguales

```javascript
const points = new Array(40, 100, 1, 5, 25, 10);
const points = [40, 100, 1, 5, 25, 10];
```

Pero esto no se puede hacer con 1 elemento

```javascript
const points = [40]; //result 40
const points = new Array(40); //result: undefined, ya que (since) crea 40 elementos indefinidos
```

<br>
<br>

1. ## **PROPIEDADES ARRAYS**

   **length**: da la longitud de la matriz

   ```javascript
   const fruits = ["Banana", "Orange", "Apple", "Mango"];
   let length = fruits.length; //result: 4
   ```

   > Para accer al ultimo elemento

   ```javascript
   const fruits = ["Banana", "Orange", "Apple", "Mango"];
   console.log(fruits[fruits.length - 1];) //result: Mango
   ```

   Una forma de _recorrer_ una matriz, es usando _for_

   ```javascript
   const fruits = ["Banana", "Orange", "Apple", "Mango"];
   let fLen = fruits.length; //4

   let text = "<ul>"; //string elemento html ul
   for (let i = 0; i < fLen; i++) {
      text += "<li>" + fruits[i] + "</li>";
   } //se itera por cada elemento de la matriz
   text += "</ul>"; //terminado el bucle se añade la etiqueta de cierre a la variable text
   ```

   <br>
   <br>

2. ## **METODOS ARRAYS**

   **forEach(_funcion_)**: funciona igual que la funcion que acabamos de ver, usa una funcion callback actuando con cada elemento del array (iterar), usaremos forEach() cuando solo querramos saber informacion sobre el array en la consola y **_NO ALMACENAR SUS DATOS_** en variables, ya que si se almacenan arroja **undefined**

   ```javascript
   const fruits = ["Banana", "Orange", "Apple", "Mango"];

   let text = "<ul>";
   fruits.forEach(myFunction); //ejecuta myFunction
   text += "</ul>";

   function myFunction(value, index, array) {
      text += "<li>" + value + "</li>";
   } //se declara la funcion al final
   ```

   La funcion toma 3 argumentos

   -  El valor del artículo
   -  El índice de artículos
   -  La matriz en sí

   <br>

   **map(funcion):** crea una nueva matriz, y actua como forEach() , **_que no crea un array nuevo_** , con una funcion callback (ambas iteran). Usaremos map cuando querramos tener un array de respuesta para almacenarlo en una variable y poder usarlo posteriormente. Ambos son leidos en consola, pero forEach() no se puede almacenar en variables ya que da **undefined**

   ```javascript
   const numbers1 = [45, 4, 9, 16, 25];
   const numbers2 = numbers1.map(myFunction);

   function myFunction(value, index, array) {
      return value * 2;
   }
   console.log(numbers2); //result: 90,8,18,32,50
   ```

   <br>

   **find(function):** ejecuta una **FUNCION** para cada elemento del array, no cambia el array original.

   Si no se encuentran elementos arroja **undefined** y no ejecuta la function para elementos vacios. Devuelve el 1er elemento que pasa la prueba.

   ```javascript
   array.find(function(currentValue, index, arr),thisValue)
   ```

   -  Require: function y currentValue

   -  Optional: index, arr y thisValue (default **undefined** es un valor pasado a la function como su valor **this**)

   ```javascript
   const ages = [4, 12, 16, 20];

   function checkAge(age) {
      // function (currentValue)
      return age > document.getElementById("ageToCheck").value;
   } // el valor de age será el 1er elemento que sea mayor que el puesto en el input de texto

   function myFunction() {
      document.getElementById("demo").innerHTML = ages.find(checkAge); // la function
   }
   ```

   **push():** añade elementos a la matriz

   ```javascript
   const fruits = ["Banana", "Orange", "Apple"];
   fruits.push("Lemon"); // Adds a new element (Lemon) to fruits
   ```

   <br>

   **toString():** convierte una matriz en string

   ```javascript
   const fruits = ["Banana", "Orange", "Apple", "Mango"];
   console.log(fruits); //Banana,Orange,Apple,Mango
   ```

   <br>

   **join("separador"):** es igual que toString(), pero puedes poner el elemento que los va a separar. En toString() se separa solo por comas

   ```javascript
   const fruits = ["Banana", "Orange", "Apple", "Mango"];
   console.log(fruits.join(" * ")); //result: Banana * Orange * Apple * Mango
   ```

   <br>

   **pop()** elimina el ultimo elemento del array, y lo puede devolver si es invocado

   ```javascript
   const fruits = ["Banana", "Orange", "Apple", "Mango"];
   fruits.pop(); //elimina el ultimo elemento y tomalo
   console.log(fruits.pop()); //result: Mango
   console.log(fruits); //result: ["Banana", "Orange", "Apple"]
   ```

   <br>

   **shift():** es igual que pop(), elimina el primero elemento

   ```javascript
   const fruits = ["Banana", "Orange", "Apple", "Mango"];
   fruits.shift();
   console.log(fruits); //result: ["Orange", "Apple", "Mango"]
   ```

   <br>

   **unshift("elemento")** es igual que push()

   <br>

   **push("elemento"):** añade un elemento al array y devuelve la longitud del array

   ```javascript
   const fruits = ["Banana", "Orange", "Apple", "Mango"];
   fruits.push("Kiwi");
   console.log(fruits); //result: ['Banana', 'Orange', 'Apple', 'Mango', 'Kiwi']
   ```

   > Reemplazar un elemento

   ```javascript
   const fruits = ["Banana", "Orange", "Apple", "Mango"];
   fruits[0] = "Kiwi";
   console.log(fruits); //result:['Kiwi', 'Orange', 'Apple', 'Mango']
   ```

   <br>

   **concat(arrayAUnir1,arrayAUnir2,etc):** une arrays creando un **_array nuevo_**

   ```javascript
   const myGirls = ["Cecilie", "Lone"];
   const myBoys = ["Emil", "Tobias", "Linus"];

   const myChildren = myGirls.concat(myBoys); //este es el nuevo array
   console.log(myChildren); //result: ['Cecilie', 'Lone', 'Emil', 'Tobias', 'Linus']
   ```

   <br>

   **splite():**

   ```javascript
   const fruits = ["Banana", "Orange", "Apple", "Mango"];
   fruits.splice(2, 0, "Lemon", "Kiwi");
   ```

   (2) define en que posicion se debe agregar

   (0) cuantos elementos se deben eliminar

   ("Lemon", "Kiwi") elementos a añadir

   ```javascript
   const fruits = ["Banana", "Orange", "Apple", "Mango"];
   fruits.splice(0, 1);
   ```

   (0)define en que posicion se va a eliminar

   (1)define cuantos elementos se van a eliminar

   El resto de parametros se omite porque no se añadira nada

   <br>
   <br>

   **slice(posicion):** corta la matriz en la posicion indicada y crea una nueva

   ```javascript
   const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
   const citrus = fruits.slice(1);
   console.log(citrus); //result:["Orange", "Lemon", "Apple", "Mango"]
   ```

   **slice(posicion,end):** corta la matriz desde posicion inicial hasta posicion final -1

   ```javascript
   const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
   const citrus = fruits.slice(2, 4);
   console.log(citrus); //result:Lemon,Apple
   ```

   <br>

   **sort():** ordena un array alfabeticamente

   ```javascript
   const fruits = ["Banana", "Orange", "Apple", "Mango"];
   fruits.sort();
   console.log(fruits.sort()); //result:['Apple', 'Banana', 'Mango', 'Orange']
   ```

   Para ordenar con numeros se utiliza una funcion

   ```javascript
   const points = [40, 100, 1, 5, 25, 10];
   points.sort(function (a, b) {
      return a - b;
   }); //result: 1,5,10,25,40,100
   ```

   <br>

   **reverse():** devuelve el array en modo invertido

   <br>

   **filter(funcion):** crea un nuevo array, con elementos de matriz que cumplen una condicion

   ```javascript
   const numbers = [45, 4, 9, 16, 25];
   const over18 = numbers.filter(myFunction);

   function myFunction(value, index, array) {
      return value > 18;
   }
   console.log(over18); //result: 45,25
   ```

   > Todas esas funciones callback toman 3 argumentos, pero no utilizan index y array. Por lo que se puede omitir

   **reduce(funcion:)** realiza la funcion con cada elemento hasta reducirlo a _uno_

   ```javascript
   const numbers = [45, 4, 9, 16, 25];
   let sum = numbers.reduce(myFunction);

   function myFunction(total, value, index, array) {
      return total + value;
   }
   console.log(sum); //result: 99
   ```

   Esta toma 4 parametros a diferencia de las demas que toman 3.
   **every():** es lo mismo que map() y filter(), pero responde un valor booleano

   ```javascript
   const numbers = [45, 4, 9, 16, 25];
   let allOver18 = numbers.every(myFunction);

   function myFunction(value, index, array) {
      return value > 18;
   }
   //result: false, porque no todos los elementos son mayores que 18
   ```

   **indexOf("elemento"):** devuelve la posicion del elemento a encontrar

   ```javascript
   const fruits = ["Apple", "Orange", "Apple", "Mango"];
   let position = fruits.indexOf("Apple"); //result: 0
   ```

   **includes():** verifica si existe un elemento o no en la matriz devolviendo un booleano

   ```javascript
   const fruits = ["Banana", "Orange", "Apple", "Mango"];

   fruits.includes("Mango"); // is true
   ```

   <br>
   <br>

# **DATE**

Los objetos Date() o de fecha, nos permiten trabajar con fechas

```javascript
const d = new Date();
```

Los objetos de fecha se crean con el constructor _new Date()_ , y hay 9 formas de crear un objeto fecha

```javascript
new Date()  //result: fecha y hora actuales
new Date(date string)   //crea el objeto fecha a partir de un string como "October 13, 2014 11:13:00" o "2022-03-25"

//Son 7 números o argumentos que especifican año, mes, día, hora, minuto, segundo y milisegundo, en ese orden
new Date(year,month)
new Date(year,month,day)
new Date(year,month,day,hours)
new Date(year,month,day,hours,minutes)
new Date(year,month,day,hours,minutes,seconds)
new Date(year,month,day,hours,minutes,seconds,ms)

new Date(milliseconds)
```

> En cuestion de meses, enero = 0 y diciembre = 11

> Javascript almacena la fecha en milisegundos

Las fechas ISO son el formato de Javascript

```javascript
const d = new Date("2015-03-25"); //YEAR-MONTH-DAY
```

<br>
<br>

1. Metodo de Date()

   **toString()** convierte la fecha en string en HTML

   ```javascript
   const d = new Date();
   d.toString();
   ```

   **toDateString()** convierte la fech de manera más legible

   ```javascript
   const d = new Date();
   d.toDateString(); //result: Tue Feb 28 2023
   ```

   **DateParse()** convierte la fecha en milisegundos desde 1 enero 1970

   ```javascript
   const msec = Date.parse("March 21, 2012");
   //1332306000000
   ```

   <br>

2. Metodos para obtener fechas **get**

   ```javascript
   const d = new Date("2021-03-25");
   d.getFullYear(); //2021
   d.getMonth(); //3
   d.getDate(); //devulve el dia con un numero del 1 al 31
   d.getDay(); //retorna el dia de la semana como un numero del 0 al 6, siendo 0 domingo
   d.getHours(); //17 devuelve las horas con numeros del 0 al 23
   d.getMinutes(); //22 numeros del 0 al 59
   d.getSeconds(); //15 numero del 0 al 59
   d.getMilliseconds(); //numeros del 0 al 999
   d.getTime(); //retorna el numero de ms desde 1970/1/1
   ```

   **Date.now()** tambien devuelve los ms desde 1970/1/1

   ```javascript
   let ms = Date.now();
   ```

   <br>

3. Metodos para establecer fechas **set**

   Los mismos que con _get_, solo que ahora será con _set_

   ```javascript
   const d = new Date();
   d.setFullYear(2020); //result: Fri Feb 28 2020 17:54:51 GMT-0500 (hora estándar de Perú)
   ```

   <br>
   <br>

# **Objeto MATH**

A diferencia de otros objetos, el objeto Math no tiene constructor

Es estatico

Todos sus metodos y propiedades se pueden usar sin crear primero el objeto

## **Propiedades** Sintaxis

Son **constantes**

`Math.property`

```javascript
Math.E; // returns Euler's number
Math.PI; // returns PI
Math.SQRT2; // returns the square root of 2, raiz cuadrada de 2
Math.SQRT1_2; // returns the square root of 1/2
Math.LN2; // returns the natural logarithm of 2
Math.LN10; // returns the natural logarithm of 10
Math.LOG2E; // returns base 2 logarithm of E
Math.LOG10E; // returns base 10 logarithm of E
```

<br>
<br>

## **Metodos** Sintaxis

`Math.method(number)`

**Math.round(x)** returns el entero más cercano

```javascript
Math.round(4.6); //result:5
Math.round(4.5); //result:5
Math.round(4.4); //result:4
```

**Math.floor(x):** return el entero menor o igual

```javascript
Math.floor(4.9); //result: 4
Math.floor(-4.2); //result: -5
Math.floor(-4.7); //result: -5
```

**trunc()** elimina los decimales

```javascript
Math.trunc(4.9); //result: 4
```

**Math.pow(x, y)** retorna x a la y

```javascript
Math.pow(8, 2); //result: 64
```

**Math.sqrt(x)** retorna raiz cuadrada root quarter de x

```javascript
Math.sqrt(64); //result: 8
```

**Math.abs(x)** retorna valor absoluto

```javascript
Math.abs(-4.6); //result: 4
```

**Math.random()** da un random number entre el 0 (incluye) al 1 (no incluye)

```javascript
Math.random(); //result: 0.2605385161155298
```

**Math.log(x)** devuelve el logaritmo natural o neperiano ln de x

```javascript
Math.log(2); //result: 0.6931471805599453
```

**Math.log2(x)** devuelve el log en base 2 de x

```javascript
Math.log2(8); //result:3
```

Para obtener numero enteros aleatorios (en JS no existen los enteros), se usa _Math.floor()_ junto con _Math.random_

```javascript
Math.floor(Math.random() * 10); //enteros aleatorios del 0 al 9
Math.floor(Math.random() * 10) + 1; //enteros aleatorios del 1 al 10
```

> Funcion para retornar un num aleatorio entre min(incluido) y max(excluido)

```javascript
function getRndInteger(min, max) {
   return Math.floor(Math.random() * (max - min)) + min;
}
```

> Funcion para retornar un num aleatorio con min y max incluidos

```javascript
function getRndInteger(min, max) {
   return Math.floor(Math.random() * (max - min + 1)) + min;
}
```

<br>
<br>

# **BOOLEAN**

Retorna true and false

El valor de un booleano siempre es resultado de comparaciones en JS

Todas estas comparaciones son verdaderas

```javascript
100; //true

3.14 - //true
   15; //true

("Hello"); //true

("false"); //true

7 + 1 + 3.14; //true, cualquier numero o operacion es true, excepto ZERO
```

> Los valores booleanos tambien pueden definirse como objetos con _new_ . Pero se recomienda **NO CREARLOS**

```javascript
let y = new Boolean(false);
```

```javascript
let x = false;
let y = new Boolean(false);

// typeof x returns boolean
// typeof y returns object
```

<br>
<br>

1. ## Operadores Logicos

   Si `x=5`

   ```javascript
   x == 8; //false
   x == 5; //true
   x == "5"; //true
   x === 5; //true
   x === "5"; //false
   x != 8; //true
   x !== 5; //false
   x !== "5"; //true
   x !== 8; //true
   x > 8; //false
   x < 8; //true
   x >= 8; //false
   x <= 8; //true
   ```

   Los operadores de comparación se pueden usar en declaraciones condicionales para comparar valores y tomar medidas según el resultado

   ```javascript
   if (age < 18) text = "Too young to buy alcohol";
   ```

   <br>
   <br>

2. ## Operadores Condicionales

   `x = 6  y = 3`

   ```javascript
   x < 10 && y > 1; // true, and

   x == 5 || y == 5; // false, or

   !(x == y); // true, not
   ```

   <br>

3. ## Operador Ternario

   ```javascript
   let voteable = age < 18 ? "Too young" : "Old enough"; // Si la variable age es un valor inferior a 18, el valor de la variable voteable será "Too Young", de lo contrario, el valor de voteable será "Old Enough".
   ```

   > Al comparar un string con un number, JS convertirá el string en un number, si no fuera un number, saldría NaN, lo que siempre es false

   <br>
   <br>

# **Declaraciones Condicionales (Conditional Statement)**

1. ## **if**

   Es un statement de un bloque de codigo que se ejecutará si la condition es true

   ```javascript
   if (condition) {
      //  block of code to be executed if the condition is true
   }
   ```

   ```javascript
   const time = new Date().getHours();
   let greeting;
   if (hour < 18) {
      greeting = "Good day";
   } //si son menos de las 18 horas, saluda con "Good Day"
   ```

   <br>
   <br>

2. ## **else**

   Viene despues de _if_ y se ejecutara si _if_ es false

   ```javascript
   if (condition) {
      //  block of code to be executed if the condition is true
   } else {
      //  block of code to be executed if the condition is false
   }
   ```

   ```javascript
   const hour = new Date().getHours();
   let greeting;
   if (hour < 18) {
      greeting = "Good day"; // si es menos de las 18  di "good day"
   } else {
      greeting = "Good evening"; // si son más de las 18 di "good evening"
   }
   ```

   <br>
   <br>

3. ## **else if**

   Se usa para especificar si la _1ra_ condition is false

   ```javascript
   if (condition1) {
      //  block of code to be executed if condition1 is true
   } else if (condition2) {
      //  block of code to be executed if the condition1 is false and condition2 is true
   } else {
      //  block of code to be executed if the condition1 is false and condition2 is false
   }
   ```

   ```javascript
   const time = new Date().getHours();
   let greeting;
   if (time < 10) {
      greeting = "Good morning";
   } else if (time < 20) {
      greeting = "Good day";
   } else {
      greeting = "Good evening";
   }
   //Si la hora es inferior a las 10:00, cree un saludo de "Buenos días", si no, pero la hora es inferior a las 20:00, cree un saludo de "Buenos días", de lo contrario, un "Buenas noches":
   ```

   <br>
   <br>

# **_switch_**

La statement switch se usa para seleccionar uno de los muchos bloques de codigo que se ejecutarán

```javascript
let variable;
switch (expression) {
   case x:
      // code block
      break;
   case y:
      // code block
      break;
   default:
   // code block
}
```

switch se utiliza una vez

El valor de la expresion se compara con los valores de cada caso

Si un bloque tiene una coincidencia, se procederá a ejecutar

Si no hay ninguna coincidencia, se ejecuta el default block

```javascript
let day;
switch (new Date().getDay()) {
   case 0:
      day = "Sunday";
      break;
   case 1:
      day = "Monday";
      break;
   case 2:
      day = "Tuesday";
      break;
   case 3:
      day = "Wednesday";
      break;
   case 4:
      day = "Thursday";
      break;
   case 5:
      day = "Friday";
      break;
   case 6:
      day = "Saturday";
} //result: Tuesday, ya que hoy es Martes
```

> Cuando JS llega a la keyword **_break_** sale del bloque switch, esto detiene la ejecución del bloque switch. No es necesario poner **_break_** al ultimo ya que alli termina el bloque

> La keyword **_default_** indica el codigo que se va a ejecutar si no se encuentra ninguna coincidencia en los demás bloques de codigo

```javascript
let text;
switch (new Date().getDay()) {
   case 6:
      text = "Today is Saturday";
      break;
   case 0:
      text = "Today is Sunday";
      break;
   default:
      text = "Looking forward to the Weekend";
   //Hoy es martes, por lo que no se cumple el 1er ni el 2do caso. Then we will use the default block
}
```

> Tambien se pueden compartir 2 casos en un code block

```javascript
let text;
switch (new Date().getDay()) {
   case 4:
   case 5:
      text = "Soon it is Weekend";
      break;
   case 0:
   case 6:
      text = "It is Weekend";
      break;
   default:
      text = "Looking forward to the Weekend";
}
```

> Si es que hay una coincidencia, se ejecutará el 1er caso

> **Los switch usan === para comparar, osea deben ser del mismo valor, pero tambien del mismo tipo de dato**

```javascript
let x = "0";
switch (x) {
   case 0:
      text = "Off";
      break;
   case 1:
      text = "On";
      break;
   default:
      text = "No value found";
}
//result: "No value found" , por que case 0 es un numero, no un string "0"
```

<br>
<br>

## **LOOP**

Los loop pueden ejecutar code blocks multiple times

Los arrays son objetos iterables

_En lugar de escribir_

```javascript
text += cars[0] + "<br>";
text += cars[1] + "<br>";
text += cars[2] + "<br>";
text += cars[3] + "<br>";
text += cars[4] + "<br>";
text += cars[5] + "<br>";
```

You can write:

```javascript
let text = "";
for (let i = 0; i < cars.length; i++) {
   text += cars[i] + "<br>";
}
```

> Son iguales

<br>
<br>

1. ## **KIND OF LOOPS**

   1. **for**
      Crea un loop con 3 optional expressions

      ```javascript
      let text = ""; //tambien puede contener un string
      for (expression 1; expression 2; expression 3) {
      // code block to be executed
      }
      ```

      > La expression 1, se ejecuta 1 vez antes de la execute of the code block

      > La expression 2, define la condition para execute the code block

      > La expression 3, se ejecuta **EVERY TIMES** despues de ejecutarse el bloque de codigo

      ```javascript
      let text = "";
      for (let i = 0; i < 5; i++) {
         text += "The number is " + i + "<br>";
      }
      //The number is 0
      //The number is 1
      //The number is 2
      //The number is 3
      //The number is 4
      ```

      La expresión 1 establece una variable antes de que comience el ciclo (sea i = 0).

      La expresión 2 define la condición para que se ejecute el bucle (debe ser inferior a 5).

      La expresión 3 aumenta un valor (i++) cada vez que se ejecuta el bloque de código en el ciclo.

      <br>

      ## Expression 1

      Normalmente se usa (i=0), pero no siempre es el caso, ya que es opcional. _Puedes iniciar **VARIOS** valores en la expression 1 separados por **COMAS**_

      ```javascript
      const cars = ["BMW", "Volvo", "Saab", "Ford"];
      let i, len, text; //se crea la variable i , len y text
      for (i = 0, len = cars.length, text = ""; i < len; i++) {
         text += cars[i] + "<br>";
      }
      ```

      Y tambien se puede omitir la expression 1 si se establece antes que comience el loop

      ```javascript
      const cars = ["BMW", "Volvo", "Saab", "Ford"];
      let i = 2; //definio i, len y text
      let len = cars.length;
      let text = "";

      for (; i < len; i++) {
         text += cars[i] + "<br>";
      } //no se utilizó la expression 1 porque ya se habian definido sus valores
      ```

      <br>

      ## Expresion 2

      Tambien es opcional, si retorna verdadero, el loop comenzará de nuevo.

      Si es falso el loop terminará

      <br>

      ## Expresion 3

      A menudo se le incrementa 1 _i++_, pero n siempre es el caso. Tambien es opcional.

      Tambien puede ser _i--_ o _i = i + 15_ o cualquier otra cosa. Tambien se puede omitir si incrementas el valor _DENTRO_ del loop

      ```javascript
      const cars = ["BMW", "Volvo", "Saab", "Ford"];

      let i = 0;
      let len = cars.length;
      let text = "";

      for (; i < len; ) {
         text += cars[i] + "<br>";
         i++;
      }
      //BMW
      //Volvo
      //Saab
      //Ford
      ```

      > La variable solo será visible dentro del loop

      ```javascript
      let i = 5; //i fuera del ciclo

      for (let i = 0; i < 10; i++) {
         //i dentro del ciclo
         // some code
      }

      // Here i is 5
      ```

      <br>
      <br>

   2. ## **for in**

      > Este statement recorre las **_PROPIEDADES_** de un object

      > Se ejecutará una vez para cada propiedad

      ```javascript
      for (key/variable in object) {
         // code block to be executed
      }
      ```

      ```javascript
      const person = { fname: "John", lname: "Doe", age: 25 };

      let txt = "";
      for (let x in person) {
         /* x recorre las propiedades de person */
         txt += person[x] + " "; // txt almacena los valores de las propiedades de person, la key x solo se puede usar con []
      }
      //result: John Doe 25, recorrio las propiedades del objeto persona a traves de la key x, la cual puede ser cualquier letra
      ```

      **_IMPORTANT_** Debes usar person[x] en el bucle, person.x no funcionará (porque x es una variable).
      <br>
      <br>

      -  El bucle _for in_ itera(realiza varias veces) sobre las propiedades del object _person_

      -  Cada iteracion retorna una **_clave "key" (x)_** - **_let x_**

      -  **_key x_** es utilizada para acceder al **valor** de la key como si estuviera accediendo al **_valor de la propiedad del objeto_**

      -  El **_valor de la propiedad del objeto_** es **_person[x]_**

      -  Entonces person[x] accede al **valor de las propiedades del objeto person**

      -  **RESUMEN**: el loop for in itera por cada propiedad y el valor que se le de a su key (x, y, i, j, etc) tomará el valor de la propiedad del objeto. Además deberá usarse dentro del loop con []

      > ## Para recorrer los elementos de un array

      Pero es preferible hacer con su metodo forEach()

      ```javascript
      for (variable in array) {
         code;
      }
      ```

      ```javascript
      const numbers = [45, 4, 9, 16, 25];

      let txt = "";
      for (let x in numbers) {
         txt += numbers[x];
      }
      //45
      //4
      //9
      //16
      //25
      ```

      <br>
      <br>

   3. ## **_for of_**

      Statement que recorre los **_VALORES_** de un objeto iterable

      Recorre estructuras de datos iterables como arrays, string, maps, nodelist y más

      ```javascript
      for (variable of iterable) {
         // code block to be executed
      }
      ```

      -  Variable: el valor de la propiedad es asignado a la variable, puede ser let o const
      -  Iterable: el objeto que tiene propiedades iterables

      <br>

      > En un ARRAY

      ```javascript
      const cars = ["BMW", "Volvo", "Mini"];

      let text = "";
      for (let x of cars) {
         text += x;
      }
      //BMW
      //Volvo
      //Mini
      ```

      ```javascript
      // en un string
      let language = "JavaScript";

      let text = "";
      for (let x of language) {
         text += x + "<br>";
      }
      //J
      //a
      //v
      //a
      //S
      //c
      //r
      //i
      //p
      //t
      ```

      <br>
      <br>

   4. ## **while**
      Ejecuta un code block siempre que cumpla una condicion especifica _TRUE_
      ```javascript
      while (condition) {
         // code block to be executed
      }
      ```
      ```javascript
      let text = "";
      let i = 0;
      while (i < 10) {
         text += "<br>The number is " + i;
         i++; // No olvidar aumentar la variable, since no terminará el loop
      }
      //The number is 0
      //The number is 1
      //The number is 2
      //The number is 3
      //The number is 4
      //The number is 5
      //The number is 6
      //The number is 7
      //The number is 8
      //The number is 9
      // Se ejecuta una y otra vez siempre que i sea menor que 10
      ```
      <br>
      <br>
   5. ## **do while**

      Este loop execute el code block antes de verificar si la condition is true, luego repetirá el loop siempre que sea verdadera. El bucle siempre se ejecutará asi la condicion sea falsa, ya que el code block se ejecuta antes de que se pruebe la condition

      ```javascript
      do {
         // code block to be executed
      } while (condition);
      ```

      ```javascript
      let text = "";
      let i = 0;

      do {
         text += "<br>The number is " + i;
         i++; // No olvidar aumentar la variable
      } while (i < 10);
      // The number is 0
      // The number is 1
      // The number is 2
      // The number is 3
      // The number is 4
      // The number is 5
      // The number is 6
      // The number is 7
      // The number is 8
      // The number is 9
      ```

      El loop _for_ y _while_ son similares si se omite el statement 1 y 3 de for

   ```javascript
   const cars = ["BMW", "Volvo", "Saab", "Ford"];
   let i = 0;
   let text = "";

   for (; cars[i]; ) {
      text += cars[i];
      i++;
   }
   ```

   ```javascript
   const cars = ["BMW", "Volvo", "Saab", "Ford"];
   let i = 0;
   let text = "";

   while (cars[i]) {
      text += cars[i];
      i++;
   }
   ```

   <br>
   <br>

   ## **break**

   finaliza el loop cuando se cumple la condicion

   > break sin referencia de un objeto solo termina o salta cuando se cumple la condicion

   ```javascript
   let text = "";
   for (let i = 0; i < 10; i++) {
      if (i === 3) {
         break;
      }
      text += "The number is " + i + "<br>";
   }
   // Finalliza el loop cuando i===3
   // The number is 0
   // The number is 1
   // The number is 2
   ```

   > break con referencia de un object, rompe la iteracon y salta del code block

   ```javascript
   const cars = ["BMW", "Volvo", "Saab", "Ford"];
   list: {
      text += cars[0] + "<br>";
      text += cars[1] + "<br>";
      break list;
      text += cars[2] + "<br>";
      text += cars[3] + "<br>";
   }
   // BMW
   // Volvo
   ```

   <br>
   <br>

   ## **continue**

   Interrumpe la iteracion en el loop cuando se cumple la condicion

   > continue omite una iteracion cuando es cumplida

   ```javascript
   let text = "";
   for (let i = 0; i < 10; i++) {
      if (i === 3) {
         continue;
      }
      text += "The number is " + i + "<br>";
   }
   // The number is 0
   // The number is 1
   // The number is 2
   // The number is 4
   // The number is 5
   // The number is 6
   // The number is 7
   // The number is 8
   // The number is 9
   ```

<br>
<br>

# **SET**

Es una coleccion de **_valores_** unicos

Cada valor solo puede ocurrir **_una vez_** en un set, **_no se repiten_**

Un set puede contener cualquier valor de cualquier tipo de datos

<br>

Usaremos set en lugar de array, cuando necesitamos valores unicos. Si un array tiene valores repetidos, podemos craer una condicion, luego usar sus metodos; pero con set solo creamos el objeto set y eliminará los valores repetidos

<br>

> Para crear un set

1. ## new Set()

   > Crear un set y le paso un array

   ```javascript
   // Create a Set
   const letters = new Set(["a", "b", "c"]);
   console.log(letters.size); // 3
   ```

   <br>

   > Si quiero agregar los valores despues, no coloco nada en el ()

   ```javascript
   // Create a Set
   const letters = new Set();

   // Add Values to the Set
   letters.add("a");
   letters.add("b");
   letters.add("c");
   console.log(letters.size); //result:3
   ```

   <br>

   > Crear un set y añadir variables

   ```javascript
   // Create a Set
   const letters = new Set();

   // Create Variables
   const a = "a";
   const b = "b";
   const c = "c";

   // Add the Variables to the Set
   letters.add(a);
   letters.add(b);
   letters.add(c);
   console.log(letters.size); // result: 3
   ```

   <br>
   <br>

2. ## add()

   ```javascript
   // Create a Set
   const letters = new Set();

   // Add values to the Set
   letters.add("d");
   letters.add("e");
   ```

<br>
<br>

3. ## forEach()

   hace un callback e itera cada elemento de Set, los elementos del callback son los mismos (value, index, array)

   ```javascript
   // Create a Set
   const letters = new Set(["a", "b", "c"]);

   // List all Elements
   let text = "";
   letters.forEach(function (value) {
      text += value + "<br>";
   });
   console.log(text); //a b c
   ```

<br>
<br>

4. ## values()

   Devuelve el objeto iterador, así se ven en consola, pero en HTML sale **_[object Set Iterator]_** y **_keys()_** tambien devuelve lo mismo que values ()

   ```javascript
   // Create a Set
   const letters = new Set(["a", "b", "c"]);

   // Display set.size
   document.getElementById("demo").innerHTML = letters.values();
   ```

   <br>

5. ## entries()

   Para acceder a los valores del objeto set usaremos el metodo entries()

   entries() con set devuelve pares [valor, valor], pero con map [clave, valor]

   Esto hace que set sea compatible con el objeto Map

   ```javascript
   // Create a Set
   const letters = new Set(["a", "b", "c"]);

   // List all entries
   const iterator = letters.entries();
   let text = "";
   for (const entry of iterator) {
      text += entry + "<br>";
   }

   document.getElementById("demo").innerHTML = text;
   //a,a
   //b,b
   //c,c
   ```

<br>
<br>

# **MAP**

Un map contiene key-values donde sus keys pueden ser cualquier tipo de dato

<br>

Conviene usar un MAP en lugar de un array cuando vamos a buscar un valor por medio de su key. Si fuera un array de 3 objetos seria muy facil (array[1].property), pero si fueran 500 objetos?

<br>

Conviene usar un MAP en lugar de un objeto cuando vamos a agregar propiedades constantemente **_(dinamic object)_**, podemos añadirle propiedades a un literal object de manera normal, pero no es muy recomendable ya que deberian de tener una estructura fija. Por eso seria recomendable usar un MAP para guardar objetos de forma dinamica **_(añadir propiedades despues de declarar el object)_**

> Crear un mapa con new Map

```javascript
// Create a Map
const fruits = new Map([
   ["apples", 500], //key-value
   ["bananas", 300],
   ["oranges", 200],
]);
console.log(fruits.get("apples")); // 500
```

<br>

> Agregar elementos al Map con **set()**

```javascript
// Create a Map
const fruits = new Map();

// Set Map Values
fruits.set("apples", 500);
fruits.set("bananas", 300);
fruits.set("oranges", 200);
console.log(fruits.get("apples")); // 500
```

<br>

> **_set()_** tambien puede cambiar los value del Map

```javascript
// Create a Map
const fruits = new Map([
   ["apples", 500],
   ["bananas", 300],
   ["oranges", 200],
]);

fruits.set("apples", 200);
```

<br>

> **_get()_** obtiene el valor de un key en el Map

`fruits.get("apples");    // Returns 500`

<br>

> **_set()_** tambien puede agregar objetos a un **map**

```javascript
// Create Objects
const apples = { name: "Apples" };
const bananas = { name: "Bananas" };
const oranges = { name: "Oranges" };

// Create a Map
const fruits = new Map();

// Add the Objects to the Map
fruits.set(apples, 500);
fruits.set(bananas, 300);
fruits.set(oranges, 200);

document.getElementById("demo").innerHTML = fruits.get(apples); // aca no se usa "apples" porque esta haciendo referencia al object no al key
// 500
```

<br>

> **_size_** esta propiedad return el number of map elements
> `fruits.size;`

<br>

> **_delete()_** elimina un elemento o propiedad o key del mapa

```javascript
// Create a Map
const fruits = new Map([
   ["apples", 500],
   ["bananas", 300],
   ["oranges", 200],
]);

// Delete an Element
fruits.delete("apples");
console.log(fruits.size); // 2
```

<br>

> **_has()_** return true and false si existe una key in the map
> `fruits.has("apples");` true

<br>

> **_forEach()_** llama a una funcion para cada key-value

```javascript
// Create a Map
const fruits = new Map([
   ["apples", 500],
   ["bananas", 300],
   ["oranges", 200],
]);

let text = "";
fruits.forEach(function (value, key) {
   text += key + " = " + value + "<br>";
});
```

<br>

**_values()_** devuelve los value de un map

```javascript
// Create a Map
const fruits = new Map([
   ["apples", 500],
   ["bananas", 300],
   ["oranges", 200],
]);

let text = "";
for (const x of fruits.values()) {
   text += x + "<br>";
}

document.getElementById("demo").innerHTML = text;
//500
//300
//200
```

<br>

**_keys()_** devuelve los keys en un map

```javascript
// Create a Map
const fruits = new Map([
   ["apples", 500],
   ["bananas", 300],
   ["oranges", 200],
]);

let text = "";
for (const x of fruits.keys()) {
   text += x + "<br>";
}

document.getElementById("demo").innerHTML = text;
//apples
//bananas
//oranges
```

<br>

> **_entries()_** retorna el objeto iterador con su key-value

```javascript
// Create a Map
const fruits = new Map([
   ["apples", 500],
   ["bananas", 300],
   ["oranges", 200],
]);

let text = "";
for (const x of fruits.entries()) {
   text += x + "<br>";
}
// apples,500
// bananas,300
// oranges,200
```

<br>
<br>

# **typeof**

Devuelve string, number, boolean, undefined para valores con datos primitivos

Devuelve object (object, arrays, null) y function para funciones

En JS una variable sin valor obtiene el valor de undefined y su tipo tambien sería undefined

`let car`

Pero un valor vacio no es lo mismo que undefined

`let car = "";    // The value is "", the typeof is "string"`

Y el tipo de dato en JS de null es object

Null y undefined son iguales en valor, pero no en tipo

```javascript
null == undefined; // true
null === undefined; // false
```

<br>
<br>

# **CONVERSORES DE TIPOS DE DATOS**

**_Number()_** convierte una variable o un valor en un numero

```javascript
Number("3.14");
Number(Math.PI);
Number(" "); // 0
Number(""); // 0
Number("99 88"); // NaN
Number("John"); // NaN
Number(false); // returns 0
Number(true); // returns 1
```

fechas a Numeros

```javascript
d = new Date();
Number(d); // returns 1404568027739
```

fechas a strings

```javascript
Date().toString(); // returns "Thu Jul 17 2014 15:38:19 GMT+0200 (W. Europe Daylight Time)"
```

## **&&**

Es lo mismo que logica proposicional

_0 false 1 true_

1 && 1 true

1 && 0 false

0 && 1 false

0 && 0 false

## **||**

_0 false 1 true_

1 || 1 true

1 || 0 true

0 || 1 true

0 || 0 false

## ^

Disyuntiva condicional (triangulo), valores iguales son false

_0 false 1 true_

1 || 1 false

1 || 0 true

0 || 1 true

0 || 0 false

<br>
<br>

## Reg Exp (Expresiones Regulares)

Cuando uno busca un texto en un string o lo quiere reemplazar, tiene que escribir el texto exacto (Mayusculas y Minusculas), pero para eso puedes usar reg exp

`/hola/i = "Hola", "HOLA", "holA", etc`

> Lo pueden usar para los metodos de string search() y replace()

-  _La terminacion i es para hacer una busqueda sin importar las mayus y minus_

*  _La terminacion g es para hacer un global search_

<br>
<br>

# **ERRORS**

## **try**

Statement allow definir un code block para probar errores mientras se execute

<br>

## **catch**

Statement allow define a code block para ser executed si ocurre un error en el try block

> Sintaxis

```javascript
try {
  Block of code to try  // prueba errores
}
catch(err) {
  Block of code to handle errors    // codigo de bloque para manejar o controlar errores
}
```

Cuando ocurre un error, JS para y arroja un error message. Con nombre y valor

<br>
<br>

## **throw**

statement crea un error personalizado. Osea puede lanzar un error que puede ser string, number, boolean or an object

```javascript
throw "Too big"; // throw a text
throw 500; // throw a number
```

> Si usa throw con try and catch puedes controlar el flow del programa y generar custom error messages

```javascript
function myFunction() {
   const message = document.getElementById("p01");
   message.innerHTML = "";
   let x = document.getElementById("demo").value; // x es el valor que será puesto en el input con id = "demo"
   try {
      if (x.trim() == "") throw "empty"; // trim eliman espacios en blanco; si x no tiene content arroja throw "vacio"
      if (isNaN(x)) throw "not a number"; //si x es NaN, then lanza throw
      x = Number(x); // aca empieza otro code block para x = number
      if (x < 5) throw "too low"; // si es menor que 5 ...
      if (x > 10) throw "too high"; // si es mayor que 5 ...
   } catch (err) {
      message.innerHTML = "Input is " + err; // si ninguna de las anteriores condiciones funciona, lanza un error message
   }
}
```

<br>
<br>

## **finally**

Este statement allow execute code, despues de try and catch, independientemente de su resultado

```javascript
try {
  Block of code to try
}
catch(err) {
  Block of code to handle errors
}
finally {
  Block of code to be executed regardless of the try / catch result
}
```

```javascript
function myFunction() {
   const message = document.getElementById("p01"); // selecciona el *p* con id = "p01"
   message.innerHTML = ""; // escribe HTML en p01
   let x = document.getElementById("demo").value; //x es el valor que será puesto en el input con id = "demo"
   try {
      if (x.trim() == "") throw "is empty"; // trim eliman espacios en blanco; si x no tiene content arroja throw "vacio"
      if (isNaN(x)) throw "is not a number"; //si x es NaN, then lanza throw
      x = Number(x); // aca empieza otro code block para x = number
      if (x > 10) throw "is too high";
      if (x < 5) throw "is too low";
   } catch (err) {
      message.innerHTML = "Error: " + err + ".";
   } finally {
      document.getElementById("demo").value = ""; // se execute asi se cumplan los anteriores o no
   }
}
```

<br>

> El error object proporciona 2 propeidaes, name and message. Por lo general van en catch(err)

Entre ellos tenemos a:

-  ReferenceError Cuando lanzas una variable que no ha sido declarada
-  SyntaxError A syntax error has occurred
-  TypeError A type error has occurred, cuando el valor es de otro tipo de lo que se espera. Cuando le pides un metodo string a un number por ejemplo
-  RangeError A number "out of range" has occurred

<br>
<br>

# **STRICT MODE**

Se debe agregar al comienzo del script o al comienzo de una function, no permite variables no declaradas

`"use strict";`

```javascript
"use strict";
x = 3.14; // This will cause an error because x is not declared
```

-  Los objetos y function tambien son variables, por eso se tienen que declarar
-  No permite eliminar variables con delete x
-  This hace referencia al objeto que llamó a una function, pero si no se especifica el object devolverá **undefined**

<br>
<br>

# **CLASS**

La keyword class se utiliza para crear clases, y siempre se le agrega un metodo **constructor()** . Sirven para crear objetos por medio de una platilla o template

Sintaxis

```javascript
class ClassName {
  constructor() { ... }
}
```

```javascript
class Car {
   constructor(name, year) {
      this.name = name;
      this.year = year;
   }
}
```

-  Crea una clase llamada "Car" y esa clase tiene 2 propiedades: "name", "year"

<br>

Las clases no son objetos

Son templates para objetos

Puedes usar la clase para crear objetos

```javascript
class Car {
   constructor(name, year) {
      this.name = name;
      this.year = year;
   }
}

const myCar1 = new Car("Ford", 2014); // Car {name: 'Ford', year: 2014}
const myCar2 = new Car("BMW", 2015); // Car {name: 'Audi', year: 2019}
// tambien puede ser con let
// acabo de crear 2 objetos Car usando la class Car
```

## **constructor()**

Se ejecuta automaticamente cuando se CREA un objeto nuevo, se utiliza para INICIALIZAR las PROPIEDADES del OBJETO

Si no defines el metodo constructor, JS agrega un constructor vacio

<br>
<br>

## **METODOS DE CLASS**

Se crea la class, añade el metodo construsctor y luego se añaden los metodos que quieras

-  Sintaxis

```javascript
class ClassName {
  constructor() { ... }
  method_1() { ... }
  method_2() { ... }
  method_3() { ... }
}
```

-  Crear un metodo de class llamdo age() que devuelva la edad del automovil

```javascript
class Car {
   constructor(name, year) {
      this.name = name;
      this.year = year;
   }
   age() {
      let date = new Date();
      return date.getFullYear() - this.year;
   }
}

let myCar = new Car("Ford", 2014);
document.getElementById("demo").innerHTML = "My car is " + myCar.age() + " years old.";
// My car is 9 years old.
```

-  Tambien puede enviar parametros a los metodos de class

```javascript
class Car {
   constructor(name, year) {
      this.name = name;
      this.year = year;
   }
   age(x) {
      // x puede usar el argumento que se le asigne
      return x - this.year; // 2023 - 2020 = 3
   }
}

let date = new Date(); //Se crea el OBJETO DATE - Wed Mar 01 2023 22:10:22 GMT-0500 (hora estándar de Perú)
let year = date.getFullYear(); //2023 - distinto al del constructor

let myCar = new Car("Ford", 2020);
document.getElementById("demo").innerHTML = "My car is " + myCar.age(year) + " years old."; //al metodo age se le asigna el argumento let year
// My car is 3 years old.
```

<br>
<br>

# **HERENCIA DE CLASES**

Una clase puede heredar las propiedades de otra, gracias a la **extends** keyword

```javascript
class Car {
   constructor(brand) {
      this.carname = brand; // la propiedad carname sera igual al parametro brand
   }
   present() {
      return "I have a " + this.carname;
   }
} // se crea la clase Car

class Model extends Car {
   constructor(brand, mod) {
      super(brand); // al invocar el metodo super(), llamamos al metodo constructor padre (Car) y obtenemos acceso a sus proppiedades y metodos
      this.model = mod; // la propiedad model sera igual al parametro mod
   } // ya no es necesario poner this.brand
   show() {
      return this.present() + ", it is a " + this.model;
   } // retorna el metodo present() de la clase Car con el parametro mod o la propiedad o argumento de Model
} // se crea la clase Model que hereda las propiedades y metodos de su padre Car

let myCar = new Model("Ford", "Mustang"); // se crea el objeto con la clase heredada Model (TENIENDO las propiedades carname y model)
document.getElementById("demo").innerHTML = myCar.show();
// I have a Ford, it is a Mustang
```

<br>
<br>

-  Tambien se pueden usar setters y getters para sus propiedades si se desea hacer algo con el valor antes de retornarlos. Se recomienda poner el nombre de la propiedad del objeto con \_ para no confundirlo con los metodos si es que estos tienen el mismo nombre.

```javascript
class Car {
   constructor(brand) {
      this._carname = brand; // la property _carname = parametro brand = "Ford"
   }
   get carname() {
      return this._carname; // el metodo get carname () obtiene el valor de la property _carname
   }
   set carname(x) {
      this._carname = x; // establece que el valor de la property _carname será igual a x / x = "Ford"
   }
}

let myCar = new Car("Ford"); // crea el objeto myCar con clase Car y argumento

document.getElementById("demo").innerHTML = myCar.carname;
// Ford
```

<br>
<br>

# **MODULES**

Los modulos permiten dividir el codigo en archivos _separados_

Solo funcionan con el protocolo HTTP(s), más no con el protocolo file:// ...

-  Se importan con el statement _import_

```javascript
import { name, age } from "./person.js";
```

En el elemento `<script>` se puede poner el atributo `type = "module"`

```html
<script type="module">
   import message from "./message.js";
</script>
```

-  Para exportar se puede hacer individualmente o todo junto

```javascript
export const name = "Jesse";
export const age = 40;
```

```javascript
const name = "Jesse";
const age = 40;

export { name, age };
```

-  Para default imports and exports, no se usa llave y se añade default al exportar

```javascript
const message = () => {
   const name = "Jesse";
   const age = 40;
   return name + " is " + age + "years old.";
};
export default message;
import message from "./message.js";
```

# **JSON**

Javascript Object Notation, es un formato ligero de intercambio de datos. Solo almacena texto, lo cual le permite ser usado en cualquier lenguaje de programacion. Autodescriptivo y facil de entender

## **Sintaxis**

No permite comas al final

```javascript
{
"employees":[
  {"firstName":"John", "lastName":"Doe"},
  {"firstName":"Anna", "lastName":"Smith"},
  {"firstName":"Peter", "lastName":"Jones"}  // sin coma
]  // sin coma
}
```

-  Un objeto con una matriz que contiene 3 objetos dentro

Su sintaxis es muy parecida a la de crear objects en JS, por lo que se puede convertir un JSON a objetos JS nativos de manera facil

## **Reglas de Sintaxis**

-  Los datos estan en pares de nombre y valor
-  Los datos estan separados por comas, y estan entre ""

`"firstName":"John"`

-  Las llaves sostienen objetos, al igual que en JS los object pueden contener name / value

`{"firstName":"John", "lastName":"Doe"}`

-  Los corchetes arrays JSON, al igual que en JS los arrays pueden contener objects

```javascript
"employees":[
  {"firstName":"John", "lastName":"Doe"},
  {"firstName":"Anna", "lastName":"Smith"},
  {"firstName":"Peter", "lastName":"Jones"}
]
// el object "employees" es un array que contiene 3 objects
```

## **Convertir un texto JSON a un objeto JS**

Los JSON leen datos de un web server y los muestran en una web page.

-  Para simplificar podemos usar un string que contenga la sintaxis JSON, ponemos comillas a cada parte del JSON

```javascript
let text = '{ "employees" : [' + '{ "firstName":"John" , "lastName":"Doe" },' + '{ "firstName":"Anna" , "lastName":"Smith" },' + '{ "firstName":"Peter" , "lastName":"Jones" } ]}';
// text es un string, es lo mismo que escribir "a"+"b"+"c" = abc
```

-  Luego convertimos el string a un objeto usando la function JSON.parse()

```javascript
const obj = JSON.parse(text); // const obj es un objeto
```

-  Ahora ya puedes usar el object en tu web page

```javascript
document.getElementById("demo").innerHTML = obj.employees[1].firstName + " " + obj.employees[1].lastName;
// accede al objecto obj con propiedad employees luego a la posicion 1 de su array y toma el valor de la propiedad firstName y luego la de lastName
```

# **Debugging**

Buscar y corregir errores en el codigo de programacion se llama depuracion o debugging. Por lo general se usa el console.log() para mostrar los valores de JS en la ventana del debugger

Se puede usar el keyword `debugger` para pausar la ejecucion de codigo

```javascript
let x = 15 * 5;
debugger; // JS se ejecutará hasta esta linea
document.getElementById("demo").innerHTML = x;
```

> **RECOMENDACIONES**

-  Evitar variables globales, evitar new, evitar ==, evitareval()

-  Usar variables locales

-  Se recomienda inicializar las variables al declararse, ya que nos dice que tipo de dato va a tener

```javascript
let firstName = "";
let lastName = "";
let price = 0;
let discount = 0;
let fullPrice = 0;
const myArray = []; // array
const myObject = {}; // object
```

Siempre declara objects y arrays con **const**

-  No usar new object()

Usar "" en lugar de new String()

Usar 0 en lugar de new Number()

Usar false en lugar den ew Boolean()

Usar {} en lugar de new Object()

Usar [] en lugar de new Array()

Usar /()/ en lugar de new RegExp()

Usar function (){} en lugar de new Function()

-  Las declaraciones que se usen fueran de un loop haran que el loop se execute más quick

```javascript
for (let i = 0; i < arr.length; i++) {} // slow

let l = arr.length; // se define la variable l
for (let i = 0; i < l; i++) {} // fast
```

-  Acceder al DOM es muy lento, si deseas acceder al DOM varias veces, guardalo en una variable y usalo por medio de la variable

```javascript
const obj = document.getElementById("demo"); // accede al DOM
obj.innerHTML = "Hello"; // lo reutiliza
```

-  Manten pequeña la cantidad de elementos HTML DOM

-  Evita crear variables innecesarias

```javascript
let fullName = firstName + " " + lastName;
document.getElementById("demo").innerHTML = fullName;
// es mejor reemplazarlo con el sgt codigo y evitar crear una tercera variable (fullName)
document.getElementById("demo").innerHTML = firstName + " " + lastName;
```

-  La keyword with no esta permitida en strict mode y no se recomienda usarla

<br>
<br>

# **ASYNC**

1. # **CALLBACKS**

   -  Evaluemos estos 2, 3 ejemplos sobre **CONTROL DE SECUENCIA**

   ```javascript
   function myDisplayer(some) {
      document.getElementById("demo").innerHTML = some;
   } // callback

   function myFirst() {
      myDisplayer("Hello");
   } // muestro el argumento Hello

   function mySecond() {
      myDisplayer("Goodbye");
   } // muestra el argunmento Goodbye

   myFirst(); // invoca a la 1ra funcion y lo imprime en el HTML
   mySecond(); // invoca a la 2da funcion y lo imprime en el HTML borrando la primera
   // result: "Goodbye"
   ```

   <br>

   ```javascript
   function myDisplayer(some) {
      document.getElementById("demo").innerHTML = some;
   }

   function myCalculator(num1, num2) {
      let sum = num1 + num2;
      return sum;
   } // retorna un number

   let result = myCalculator(5, 5); // almacena el number en una variable
   myDisplayer(result); // lo muestra en el HTML
   ```

   <br>

   ```javascript
   function myDisplayer(some) {
      document.getElementById("demo").innerHTML = some;
   } // callback

   function myCalculator(num1, num2) {
      let sum = num1 + num2;
      myDisplayer(sum); // usa el callback, por eso no se usa return
   }

   myCalculator(5, 5); // 10
   ```

   <br>

   -  Una **_callback_** function es una function que se pasa como argument a otra function, esto permite que una funcion llame a otra function. El callback puede ejecutarse despues de que otra function se haya ejecutado.

   ```javascript
   function myDisplayer(something) {
      document.getElementById("demo").innerHTML = something;
   } // SERÁ el callback (funcion argumento de otra function)

   function myCalculator(num1, num2, myCallback) {
      let sum = num1 + num2;
      myCallback(sum); // callback function como argumento de myCalculator y tiene como argumento a sum
   }

   myCalculator(5, 5, myDisplayer); // el callback myDisplayer se llama sin () como figura en la function myCalculator
   // 10
   ```

   <br>

   **_EXPLICACION_** En el codigo hay 2 functions **(myDisplayer y myCalculator)** para realizar una suma y mostrarla en HTML.

   -  myCalculator acepta 3 parametros, **num1** y **num2** que se suman y **myCallback** que se ejecutará cuando se termine la suma.

   -  La suma se almacena en la variable **sum** , y posterior a esto se llama a la callback function **myCallback** a la cual se le pasa **sum** como argumento

   -  En la ultima parte del codigo se invoca a **myCalculator** y se le pasa como argumentos 5, 5 y **myDisplayer**.

   -  **myCalculator** realiza la suma de los 2 números y luego llama a myDisplayer() con el resultado de la suma como argumento.

   -  En pocas palabras se esta usando a **myDisplayer** como la callback function **myCallback** la cual es llamada una vez cumplida la suma y almacenada en la variable **sum**

   -  El callback siempre se llama sin parentesis

   <br>

   ```javascript
   // Create an Array
   const myNumbers = [4, 1, -20, -7, 5, 9, -6];

   // Call removeNeg with a Callback
   const posNumbers = removeNeg(myNumbers, (x) => x >= 0);

   // Display Result
   document.getElementById("demo").innerHTML = posNumbers;

   // Remove negative numbers
   function removeNeg(numbers, callback) {
      const myArray = [];
      for (const x of numbers) {
         if (callback(x)) {
            myArray.push(x);
         }
      }
      return myArray;
   }
   ```

   <br>
   <br>

   -  Otro ejemplo:

   ```javascript
   // Create an Array
   const myNumbers = [4, 1, -20, -7, 5, 9, -6];

   // Call removeNeg with a Callback
   const posNumbers = removeNeg(myNumbers, (x) => x >= 0); // HOISTING - CALLBACK = para todo x que sea mayor que CERO (ANONYMOUS ARROW FUNCTION)

   // Display Result
   document.getElementById("demo").innerHTML = posNumbers;

   // Remove negative numbers, callback es el CALLBACK FUNCTION de removeNeg
   function removeNeg(numbers, callback) {
      const myArray = []; // crea un array vacio
      for (const x of numbers) {
         if (callback(x)) {
            myArray.push(x);
         }
      }
      return myArray;
   } // si el callback(x) cumple con la condicion, entonces con el metodo push() colocale al array el valor que logro cumplir con la condicion
   // luego retorna el array con los numeros que cumplieron
   ```

   <br>

   -**_Cuando usar los callback:_**

   Los callback por lo general se usan en las funciones asincronas, donde una function tiene que esperar a otra function, **_como esperar a que se cargue un file_**

2. # **ASYNCHRONOUS JS**

   Son funciones que se ejecutan en paralelo con otras functions. Como setTimeout().

   Los callback se usan muy amenudo con asynchronous functions

   <br>

   ## **setTimeout()**

   Al usar setTimeout() puedes especificar un callback function para que se ejecute en un tiempo de espera.

   ```javascript
   setTimeout(myFunction, 3000); // myFunction es usada como callback y se invocara 3 segundos despues - HOISTING

   function myFunction() {
      document.getElementById("demo").innerHTML = "I love You !!";
   }
   ```

   **_NOTA:_** cuando pases una function como argumento, no uses parentesis.

   <br>
   <br>

   ## **setInterval()**

   Al usarla puede ejecutar un callback que se realizará cada intervalo de tiempo

   ```javascript
   setInterval(myFunction, 1000); // myFunction es callback y se invocará cada 1 segundo - HOISTING

   function myFunction() {
      let d = new Date();
      document.getElementById("demo").innerHTML = d.getHours() + ":" + d.getMinutes() + ":" + d.getSeconds();
   } // crea "d" un objeto Date, luego pinta en el HTML sus valores por medio de metodos.
   ```

   <br>

   Los metodos de JS asynchronous moderno no usan callback, en su lugar usan Promesas, ya que por medio de callback es dificil de escribir y ejecutar.

   <br>
   <br>

# **PROMESAS PROMISES**

-  **Producir codigo** es un code que puede tomar algo de tiempo.

-  **El codigo de consumo** es un code que debe esperar el resultado.

-  Una promesa es un **objeto** de JS que **VINCULA** la produccion de codigo con el codigo de consumo

Un objeto promesa contiene tanto el codigo de produccion como las llamadas del codigo de consumo.

<br>

**_SYNTAX_**

```javascript
let myPromise = new Promise(function (myResolve, myReject) {
   // "Producing Code" (May take some time)

   myResolve(); // when successful
   myReject(); // when error
});

// "Consuming Code" (Must wait for a fulfilled Promise)
myPromise.then(
   function (value) {
      /* code if successful */
   },
   function (error) {
      /* code if some error */
   }
);
```

<br>

Cuando el **codigo de produccion** obtiene el resultado, debe llamar a uno de los 2 **callback**

-  Cuando el resultado es **SUCCESS**, llama a un **_myResolve(result value)_**

-  Cuando el resultado es **ERROR**, llama a un **_myReject(error object)_**

<br>

# **PROPIEDADES DE PROMISES**

Un objeto promesa en JS puede ser:

-  pendiente - pending

-  cumplido - fulfilled

-  rechazado - rejected

<br>

Un objeto promesa admite 2 properties: **estado y resultado** - **state and result**

-  Mientras un objeto promesa esta pendiente(en funcionamiento aun), el resultado no esta definido **_undefined_**

-  Cuando se cumple, el resultado es un **_valor_**

-  Cuando es rechazado, el resultado es un **_error_**

<br>

**_myPromise.state:_** "pending", "fulfilled" and "rejected"

**_myPromise.result:_** "undefined", "value" and "error"

<br>

-  No se puede acceder al state ni al result de las propiedades de Promise.

-  Debes usar un metodo Promise para manage las Promises

<br>
<br>

# **Promise.then()**

Toma 2 arguments, un **callback** para **success** y otro para **error**

Ambos son opcionales, por lo que puedes usar un callback solo para success o para error

**_SYNTAX_**

```javascript
myPromise.then(
   function (value) {
      /* code if successful */
   },
   function (error) {
      /* code if some error */
   }
);
```

<br>
<br>

```javascript
function myDisplayer(some) {
  document.getElementById("demo").innerHTML = some;
}  // pinta lo que tiene como argumento

let myPromise = new Promise(function(myResolve, myReject) {
  let x = 0;   // define una variable x

// some code (try to change x to 5)

  if (x == 0) {
    myResolve("OK");
  } else {
    myReject("Error");
  }
});
// si x == 0 entonces es SUCCESS, por ende "OK" se convierte en "value"
// si x != 0 entonces es ERROR, por ende "Error" se convierte en "error"

myPromise.then(
  function(value) {myDisplayer(value);},  // si es SUCCESS pinta "OK"
  function(error) {myDisplayer(error);}   // si es ERROR pinta "Error"
// result: "OK"
```

<br>
<br>

-  **COMPARANDO CALLBACK FUNCTION CON PROMISE**

```javascript
// CALLBACK FUNCTION
setTimeout(function () {
   myFunction("I love You !!!");
}, 3000);

function myFunction(value) {
   document.getElementById("demo").innerHTML = value;
}
```

<br>

```javascript
// PROMISE
const myPromise = new Promise(function (myResolve, myReject) {
   setTimeout(function () {
      myResolve("I love You !!");
   }, 3000);
}); // no fue necesario poner myReject porque no generaría ERROR

myPromise.then(function (value) {
   document.getElementById("demo").innerHTML = value;
});
```

<br>

-  Esperando un file

```javascript
// CALLBACK
function myDisplayer(some) {
   document.getElementById("demo").innerHTML = some;
}

function getFile(myCallback) {
   let req = new XMLHttpRequest();
   req.onload = function () {
      if (req.status == 200) {
         myCallback(this.responseText);
      } else {
         myCallback("Error: " + req.status);
      }
   };
   req.open("GET", "mycar.html");
   req.send();
}

getFile(myDisplayer);
```

<br>

```javascript
// PROMISE
function myDisplayer(some) {
   document.getElementById("demo").innerHTML = some;
}

let myPromise = new Promise(function (myResolve, myReject) {
   let req = new XMLHttpRequest();
   req.open("GET", "mycar.html");
   req.onload = function () {
      if (req.status == 200) {
         myResolve(req.response);
      } else {
         myReject("File not Found");
      }
   };
   req.send();
});

myPromise.then(
   function (value) {
      myDisplayer(value);
   },
   function (error) {
      myDisplayer(error);
   }
);
```

<br>
<br>

# **ASYNC Y AWAIT**

**Async y await** hacen más facil de escribir las **Promise**

-  **async** hace que una función **devuelva** una promesa

-  **await** hace que una función **espere** una Promesa

<br>

La keyword **async antes de una funcion**, hace que la funcion **devuelva** una **Promise**

```javascript
async function myFunction() {
   return "Hello";
}
```

Es igual que :

```javascript
function myFunction() {
   return Promise.resolve("Hello");
}
```

<br>
<br>

-  El ejemplo completo es este:

```javascript
function myDisplayer(some) {
  document.getElementById("demo").innerHTML = some;
}

async function myFunction() {return "Hello";}

myFunction().then(
  function(value) {myDisplayer(value);},
  function(error) {myDisplayer(error);}   // no seria necesario
// el codigo seria más simple, como solo retornará un valor, entonces no habrá "error", por ende se puede eliminar la ultima linea
```

<br>
<br>

# **AWAIT**

**_await_** solo se puede usar dentro de una function **_async_**

Hace que la función **_pause la ejecución_** y **_espere_** una **_promesa resuelta_** antes de **_continuar_**

`let value = await promise;`

```javascript
async function myDisplay() {
   let myPromise = new Promise(function (resolve, reject) {
      resolve("I love You !!");
   });
   document.getElementById("demo").innerHTML = await myPromise;
} // espera a que se ejecute myPromise para pintar en HTML

myDisplay();
```

-  Los parametros **_resolve_** y **_reject_** estan **_predefinidos_** por JS

-  No los crearemos, pero se **_llamará a uno_** de ellos cuando la **_function esté lista_**.

-  Muy a menudo **_no_** usaremos **_reject_**

<br>
<br>

```javascript
// example without reject
async function myDisplay() {
   let myPromise = new Promise(function (resolve) {
      resolve("I love You !!");
   });
   document.getElementById("demo").innerHTML = await myPromise;
} // espera a que se ejecute myPromise para pintar en HTML

myDisplay();
```

<br>
<br>

```javascript
// esperando un setTimeout() - tiempo de espera
async function myDisplay() {
   let myPromise = new Promise(function (resolve) {
      setTimeout(function () {
         resolve("I love You !!");
      }, 3000);
   });
   document.getElementById("demo").innerHTML = await myPromise;
} // espera a myPromise para pintar en HTML

myDisplay();
```

<br>
<br>

```javascript
// esperar un archivo
async function getFile() {
   let myPromise = new Promise(function (resolve) {
      let req = new XMLHttpRequest();
      req.open("GET", "mycar.html");
      req.onload = function () {
         if (req.status == 200) {
            resolve(req.response);
         } else {
            resolve("File not Found");
         }
      };
      req.send();
   });
   document.getElementById("demo").innerHTML = await myPromise;
} // espera a que se ejecute myPromise para pintar el archivo mycar.html

getFile();
```

<br>
<br>

# **HTML DOM**

Con HTML DOM, JavaScript puede **acceder** y **cambiar** todos los elementos de un **documento HTML**

Este es el arbol de **objetos HTML**

![HTML OBJECT](./imgs/html.gif)

<br>

Con el modelo de objetos JS puede hacer lo sgt:

-  Cambiar todos los elementos HTML en la página

-  Cambiar todos los atributos HTML en la página

-  Cambiar todos los estilos CSS en la página

-  Eliminar elementos y atributos HTML existentes

-  Agregar nuevos elementos y atributos HTML

-  Reaccionar a todos los eventos HTML existentes en la página

-  Crear nuevos eventos HTML en la página

En pocas palabras el HTML DOM es un estandar sobre como obtener, cambiar, agregar o eliminar HTML elements.

En el DOM todos los elementos HTML se definen como objects.

-  Una **property** es un **value** que puede obtener o establecer (**_como cambiar el contenido de un HTML element_**)

-  Un **method** es una accion que puede realizar (**_como agregar o elimanar un elemento HTML_**)

```javascript
document.getElementById("demo").innerHTML = "Hello World!";
```

**_getElementById()_** es un metodo.

**_innerHTML_** es una propiedad

<br>

El object document representa la pagina web.

Si deseas accede a cualquier elemento del HTML siempre comienza accediendo al document object.

<br>

**Encontrar** elementos HTML

-  **_document.getElementById(id)_**, encuentra **UN** elemento

-  **_document.getElementsByTagName(name)_**, encuentra todos los **elementos** que tengan esa etiqueta - tag

-  **_document.getElementsByClassName(name)_**, encuentra **elementos** por su clase

-  **_querySelectorAll()_**, encuentra elementos por medio de sus selectores CSS

<br>

**Propiedades** para **cambiar** elementos

-  **_element.innerHTML_**, cambia el contenido HTML de un element

-  **_element.attribute_**, change su atributo

-  **_element.style.property_**, cambia el style de un HTML element

-  **_element.setAttribute(attribute, value)_**, cambia el valor del atributo de un HTML element **método**

<br>

**Adicion** y **eliminacion** de objetos

-  **_document.createElement(element)_**, crea un HTML element

-  **_document.removeChild(element)_**, remueve un HTML element

-  **_document.appendChild(element)_**, añade un HTML element

-  **_document.replaceChild(new, old)_**, reemplaza un HTML element

<br>
<br>

Su forma sería algo así:

```javascript
document.getElementById(id).onclick = function () {
   code;
};
```

<br>

Tambien se puede buscar un elemento por su etiqueta HTML:

-  **document.forms[""]**, retorna todos los form

<br>
<br>

La manera más comun de encontrar un elemento es por medio de su ID

```javascript
const element = document.getElementById("intro");
```

<br>
<br>

# **ENCONTRAR HTML ELEMENTS**

-  Si se encuentra el elemento, el metodo devolverá el elemento como un **OBJETO** (**en el elemento**)

-  Si no se encuentra el elemento, el elemento contendrá un null

<br>

Este ejemplo encuentra todos los tag <p> que estan dentro de un div con id = "main"

```html
<div id="main">
<p>Finding HTML Elements by Tag Name</p>
<p>This example demonstrates the <b>getElementsByTagName</b> method.</p>
</div>

<p id="demo"></p>

<script>
const x = document.getElementById("main");   // coloca el elemento en un objeto x
const y = x.getElementsByTagName("p"); // busca todos los p del objeto x

document.getElementById("demo").innerHTML =
'The first paragraph (index 0) inside "main" is: ' + y[0].innerHTML; // los ubica como un array
```

<br>

Este example ubicará los elementos por su clase

```html
<p>Finding HTML Elements by Class Name.</p>
<p class="intro">Hello World!</p>
<p class="intro">This example demonstrates the <b>getElementsByClassName</b> method.</p>

<p id="demo"></p>

<script>
const x = document.getElementsByClassName("intro");
document.getElementById("demo").innerHTML =
'The first paragraph (index 0) with class="intro" is: ' + x[0].innerHTML;  // ubica a los elementos como si fuera un array
```

<br>
<br>

Este example muestra como utilizar los hijos de un element

```html
<form id="frm1" action="/action_page.php">
  First name: <input type="text" name="fname" value="Donald"><br>
  Last name: <input type="text" name="lname" value="Duck"><br><br>
  <input type="submit" value="Submit">
</form>  <!-- form tiene 3 hijos -->

<p>These are the values of each element in the form:</p>

<p id="demo"></p>

<script>
const x = document.forms["frm1"];   // selecciona form
let text = "";
for (let i = 0; i < x.length ;i++) {
  text += x.elements[i].value + "<br>";
}  // para acceder a cada hijo, se pone elements[i]
document.getElementById("demo").innerHTML = text;
```

<br>
<br>

# **CAMBIAR CONTENIDO HTML**

La forma más comun de cambiar contenido HTML es mediante la propiedad **innerHTML**

```html
<p id="p1">Hello World!</p>

<script>
   document.getElementById("p1").innerHTML = "New text!";
</script>
```

<br>

Lo mismo pasa si lo guardo en una variable

```html
<h1 id="id01">Old Heading</h1>

<script>
   const element = document.getElementById("id01");
   element.innerHTML = "New Heading";
</script>
```

-  Cambiar valor de un atributo

Se usará esta syntax:

`document.getElementById(id).attribute = new value`

```html
<img id="image" src="smiley.gif" width="160" height="120" />

<script>
   document.getElementById("image").src = "landscape.jpg";
   // su nombre era smiley.gif y fue cambiado a landscape.jpg
</script>
```

# **VALIDACION DE FORMULARIOS**

Esto se puede realizar directamente desde JS.

Si un campo esta vacío, una funcion alertará con un message y return false para prevent que se envie el form

```html
<script>
function validateForm() {
  let x = document.forms["myForm"]["fname"].value; // selecciona al formulario que tenga name "myForm" y al input que tenga el ID "fname"
  if (x == "") {
    alert("Name must be filled out");
    return false; // este false EVITA que se envíe el formulario si no se cumple la condition
  }
}
</script>
</head>
<body>

<h2>JavaScript Validation</h2>

<form name="myForm" action="/action_page.php" onsubmit="return validateForm()" method="post">   <!-- cuando se envíe retornará la function validateForm() -->
  Name: <input type="text" name="fname">
  <input type="submit" value="Submit">
</form>
```

<br>

Este example muestra un message cuando se presiona un button y no se ha llenado el input con la condition required

```html
<input id="numb">

<button type="button" onclick="myFunction()">Submit</button>

<p id="demo"></p>

<script>
function myFunction() {
  // Get the value of the input field with id="numb"
  let x = document.getElementById("numb").value;
  // If x is Not a Number or less than one or greater than 10
  let text;
  if (isNaN(x) || x < 1 || x > 10) {
    text = "Input not valid";
  } else {
    text = "Input OK";
  }
  document.getElementById("demo").innerHTML = text;
}
```

<br>

Tambien se puede validar un form usando **_required_** attribute

```html
<form action="/action_page.php" method="post">
   <input type="text" name="fname" required />
   <input type="submit" value="Submit" />
</form>
```

<br>

-  Atributos de inputs HTML

   -  **_disabled_** especifica el input element que deberia ser disableado

   -  **_max y min_** maximo o minimo de characters

   -  **_pattern_** specifies el patron de valor de un input

   -  **_required_** specifies que el campo del input requiere un elemento

<br>

-  Pseudo Clases o Pseudo Selectores

   -  **_:invalid_** Selecciona el input con valores invalidos

   -  **_:required_** Select el input con el atributo required

   -  **_:valid_** Select el input con valores validos

<br>
<br>

# **DOM CSS**

Para cambiar el style de un HTML element se usa la sgt syntax

`document.getElementById(id).style.property = new style`

<br>

```html
<!-- Cambia el style del parrafo con las siguientes properties -->
<p id="p2">Hello World!</p>

<script>
document.getElementById("p2").style.color = "blue";
document.getElementById("p2").style.fontFamily = "Arial";
document.getElementById("p2").style.fontSize = "larger";
```

<br>

-  Como ocultar y mostrar un elemento

```html
<p id="p1">This is a text. This is a text. This is a text. This is a text.</p>

<input type="button" value="Hide text" onclick="document.getElementById('p1').style.visibility='hidden'" />
<input type="button" value="Show text" onclick="document.getElementById('p1').style.visibility='visible'" />
```

-  Link con todas las properties del **_[style object](https://www.w3schools.com/jsref/dom_obj_style.asp)_**

<br>
<br>

-  Ejemplo de animaciones en JS

```javascript
function myMove() {
  let id = null;  // valor null
  const elem = document.getElementById("animate");
  let pos = 0;
  clearInterval(id); // limpia todos los intervalos con argumento id
  id = setInterval(frame, 5);
  function frame() {
    if (pos == 350) {
      clearInterval(id);   // si pos = 350, limpiará todos los intervalos con argumento id
    } else {
      pos++;
      elem.style.top = pos + "px";  // aumentará pos 1px
      elem.style.left = pos + "px"; // aumentará pos 1px
    }
  }
```

<br>
<br>

# **EVENTOS - EVENTS**

Un evento es cuando sucede algo relacionado al HTML DOM.

-  Cuando un usuario hace clic con el mouse

-  Cuando una página web ha cargado

-  Cuando se ha cargado una imagen

-  Cuando el mouse se mueve sobre un elemento

-  Cuando se cambia un campo de entrada

-  Cuando se envía un formulario HTML

-  Cuando un usuario pulsa una tecla

Syntax:

```html
<!-- onclick = JavaScript; -->

<h2 onclick="this.innerHTML='Ooops!'">Click on this text!</h2>
<!-- this hace referencia al element -->
```

<br>

El mismo example, but from the handler events

```javascript
<h1 onclick="changeText(this)">Click on this text!</h1>

<script>
function changeText(id) {
  id.innerHTML = "Ooops!";
}
</script>
```

<br>

Asignar eventos a HTML elements, se pueden usar atributos

```html
<button onclick="displayDate()">The time is?</button>

<script>
   function displayDate() {
      document.getElementById("demo").innerHTML = Date();
   }
</script>

<p id="demo"></p>
```

<br>

Asignar eventos pero desde el DOM HTML

```html
<button id="myBtn">Try it</button>  <!-- No es necesario onclick -->

<p id="demo"></p>

<script>
document.getElementById("myBtn").onclick = displayDate;

function displayDate() {
  document.getElementById("demo").innerHTML = Date();
}
```

<br>

-  Evento **_onload_**, se usa para verificar si cargó una pagina o verificar cookies

```html
<body onload="checkCookies()">

<h2>JavaScript HTML Events</h2>

<p id="demo"></p>

<script>
function checkCookies() {
  var text = "";
  if (navigator.cookieEnabled == true) {
    text = "Cookies are enabled.";
  } else {
    text = "Cookies are not enabled.";
  }
  document.getElementById("demo").innerHTML = text;
}
```

<br>

-  Evento **_onchage_**, se usa por lo general con **_input_** para la validacion de input fields

```html
<input type="text" id="fname" onchange="upperCase()" />
<p>When you leave the input field, a function is triggered which transforms the input text to upper case.</p>

<script>
   function upperCase() {
      const x = document.getElementById("fname");
      x.value = x.value.toUpperCase(); // el valor del input se cambiará a mayusculas
   }
</script>
```

-  Evento **_onmouseover_** y **_onmouseout_**, pueden ser usados para activar una function cuando el mouse pasa sobre o fuera del HTML element

```html
<div onmouseover="mOver(this)" onmouseout="mOut(this)" style="background-color:#D94A38;width:120px;height:20px;padding:40px;">HOLA</div>

<script>
   function mOver(obj) {
      obj.innerHTML = "Thank You";
   }

   function mOut(obj) {
      obj.innerHTML = "Mouse Over Me";
   }
   // al inicio dice HOLA, luego con onmouseover "Thank You" y cuando sale el raton (onmouseout) se queda con "Mouse Over Me"
</script>
```

<br>

-  Evento **_onmousedown_** y **_onmouseup_**, se activan cuando se mantiene clickeado y cuando se levanta el click

```html
<div onmousedown="mDown(this)" onmouseup="mUp(this)" style="background-color:#D94A38;width:90px;height:20px;padding:40px;">Click Me</div>

<script>
   function mDown(obj) {
      obj.style.backgroundColor = "#1ec5e5";
      obj.innerHTML = "Release Me";
   }

   function mUp(obj) {
      obj.style.backgroundColor = "#D94A38";
      obj.innerHTML = "Thank You";
   }
</script>
```

<br>
<br>

Diferencias de detectores de eventos y eventos:

-  En HTML, onclick es el detector de eventos, myFunction es el controlador de eventos

```html
<button onclick="myFunction()">Click me</button>
```

<br>

-  En JavaScript, el clic es el evento, myFunction es el controlador de eventos

```javascript
button.addEventListener("click", myFunction);
```

<br>

Todos los HTML DOM [**_event object_**](https://www.w3schools.com/jsref/dom_obj_event.asp)

# **METODO addEventListener()**

**_Syntax_** añade un detector de eventos (event listener) que se active cuando un usuario haga click (event) en un button

`element.addEventListener(event, function, useCapture);`

<br>

`document.getElementById("myBtn").addEventListener("click", displayDate);`

```html
<button id="myBtn">Try it</button>

<p id="demo"></p>

<script>
   document.getElementById("myBtn").addEventListener("click", displayDate);

   function displayDate() {
      document.getElementById("demo").innerHTML = Date();
   }
</script>
```

<br>

**_addEventListener()_**

-  Adjunta un controlador de eventos al elemento especificado

-  **_Añade_** un controlador de eventos a un elemento **_sin sobrescribir_** los controladores de **_eventos existentes_**

   -  Puede **_agregar muchos controladores_** de eventos a **_un elemento_**

   -  Puede **_agregar muchos controladores de eventos_** del mismo tipo a **_un elemento_**, es decir, **_dos eventos de "clic"_**

   -  Puede agregar detectores de eventos a cualquier objeto DOM, no solo elementos HTML. es decir, el **_WINDOW OBJECT_** y como el **_xmlHttpRequest object_**

-  Puedes **_eliminar_** un detector de eventos usando **_removeEventListener()_**

<br>

**_`element.addEventListener(event, function, useCapture);`_**

-  El primer parametro es el [tipo de evento](https://www.w3schools.com/jsref/dom_obj_event.asp) ("click" o "mousedown")

-  El segundo parametro es la funcion que queremos llamar cuando ocurra el evento

-  El tercer parametro es un **_booleano_** que especifica si se debe usar el event bubbling or event capturing (**_es opcional_**)

<br>

**_IMPORTANT:_** Tenga en cuenta que no utiliza el prefijo "on" para el evento; utilice " click" en lugar de " onclick".

<br>

Examples:

```html
<button id="myBtn">Try it</button>

<script>
   document.getElementById("myBtn").addEventListener("click", function () {
      alert("Hello World!");
   });
</script>
<!-- Muestra una alerta cuando se clickea el button -->
```

```html
<!-- Lo mismo pero con la function afuera -->
<button id="myBtn">Try it</button>

<script>
document.getElementById("myBtn").addEventListener("click", myFunction);

function myFunction() {
  alert ("Hello World!");
}
```

<br>
<br>

-  2 tipos de eventos iguales a un mismo elemento

```html
<button id="myBtn">Try it</button>

<script>
   let x = document.getElementById("myBtn");
   x.addEventListener("click", myFunction);
   x.addEventListener("click", someOtherFunction);

   function myFunction() {
      alert("Hello World!");
   }

   function someOtherFunction() {
      alert("This function was also executed!");
   }
</script>
```

<br>
<br>

-  Varios tipos de eventos a un mismo elemento

```html
<button id="myBtn">Try it</button>

<p id="demo"></p>

<script>
   let x = document.getElementById("myBtn");
   x.addEventListener("mouseover", myFunction);
   x.addEventListener("click", mySecondFunction);
   x.addEventListener("mouseout", myThirdFunction);

   function myFunction() {
      document.getElementById("demo").innerHTML += "Moused over!<br>";
   }

   function mySecondFunction() {
      document.getElementById("demo").innerHTML += "Clicked!<br>";
   }

   function myThirdFunction() {
      document.getElementById("demo").innerHTML += "Moused out!<br>";
   }
</script>
```

<br>
<br>

-  Tambien funciona para el **_window object_** o para el **_XML object_**

```html
<p id="demo"></p>

<script>
   window.addEventListener("resize", function () {
      document.getElementById("demo").innerHTML = Math.random();
   });
</script>
<!-- Cuando se ajuste el tamaño de la ventana will throw a random number -->
```

<br>
<br>

-  Al pasar parametros, en este example uso una funcion anonima para llamar a una function especificada con parametros **_myFunction_**

```html
<button id="myBtn">Try it</button>

<p id="demo"></p>

<script>
   let p1 = 5;
   let p2 = 7;
   document.getElementById("myBtn").addEventListener("click", function () {
      myFunction(p1, p2);
   });

   function myFunction(a, b) {
      document.getElementById("demo").innerHTML = a * b;
   }
</script>
```

<br>
<br>

-  Event Bubbling o Event Capture; si un elemento `<p>` esta dentro de un `<div>` y a ambos se les asigna un evento de click, entonces...

`addEventListener(event, function, useCapture);`

-  Con el event bubbling el elemento **_MÁS INTERNO_** se manejará primero y luego el externo, el valor por defecto es **_false_** , lo que usara el bubbling

-  Con el event capture el elemento **_MÁS EXTERNO_** se ejecutará primero y luego el interno, cuando el valor es **_true_** se ejecutará el capture

<br>

Example

```javascript
document.getElementById("myP").addEventListener("click", myFunction, true);
document.getElementById("myDiv").addEventListener("click", myFunction, true);
```

<br>

```html
<div id="myDiv1">
   <h2>Bubbling:</h2>
   <p id="myP1">Click me!</p>
</div>
<br />

<div id="myDiv2">
   <h2>Capturing:</h2>
   <p id="myP2">Click me!</p>
</div>

<script>
   document.getElementById("myP1").addEventListener(
      "click",
      function () {
         alert("You clicked the white element!");
      },
      false
   );

   document.getElementById("myDiv1").addEventListener(
      "click",
      function () {
         alert("You clicked the orange element!");
      },
      false
   );

   document.getElementById("myP2").addEventListener(
      "click",
      function () {
         alert("You clicked the white element!");
      },
      true
   );

   document.getElementById("myDiv2").addEventListener(
      "click",
      function () {
         alert("You clicked the orange element!");
      },
      true
   );
</script>
<!-- En el caso del bubbling, se ejecuta primero el p e inmediatamente despues el div, en el caso del capture es al reves. Solo cuando clickeamos los parrafos, cuando clickeamos los div, no hay ninguna diferencia -->
```

<br>

-  El method removeEventListener() elimina los controladores de eventos, que se han adjuntado con addEventListener()

```html
<div id="myDIV">
   <p>This div element has an onmousemove event handler that displays a random number every time you move your mouse inside this orange field.</p>
   <p>Click the button to remove the div's event handler.</p>
   <button onclick="removeHandler()" id="myBtn">Remove</button>
</div>

<p id="demo"></p>

<script>
   document.getElementById("myDIV").addEventListener("mousemove", myFunction);

   function myFunction() {
      document.getElementById("demo").innerHTML = Math.random();
   }

   function removeHandler() {
      document.getElementById("myDIV").removeEventListener("mousemove", myFunction);
   }
</script>
```

<br>
<br>

# **NAVIGATION DOM**

1. # **NODES - NODOS**

   Todo en un HTML document es un nodo

   -  Todo el documento es un nodo del documento

   -  Cada elemento HTML es un nodo de elemento

   -  El texto dentro de los elementos HTML son nodos de texto

   -  Cada atributo HTML es un nodo de atributo **_(obsoleto)_**

   -  Todos los comentarios son nodos de comentarios

   ![HTML Nodos](./imgs/html.gif)

   <br>

   Con el HTML DOM, JavaScript puede acceder a todos los nodos del árbol de nodos.

   Se **_pueden crear nuevos nodos_** y **_todos los nodos_** se pueden **_modificar_** o **_eliminar_**.

   <br>

   Los nodos del árbol de nodos tienen una **_relación jerárquica_** entre sí.

   -  Los términos padre, hijo y hermano se utilizan para describir las relaciones.

   -  En un árbol de nodos, el nodo superior se llama root - raíz (o root node)

   -  Cada nodo tiene exactamente un padre, **_excepto la raíz - root (que no tiene padre)_**

   -  Un nodo puede tener varios hijos.

   -  Los siblings (hermanos o hermanas) son nodos con el mismo padre

   ```html
   <html>
      <head>
         <title>DOM Tutorial</title>
      </head>

      <body>
         <h1>DOM Lesson one</h1>
         <p>Hello world!</p>
      </body>
   </html>
   ```

   <br>

   ![Node](https://www.w3schools.com/js/pic_navigate.gif)

   `<html>` es el root node

   `<html>` no tiene parents

   `<html>` es el parent de `<head>` y `<body>`

   `<head>` es el first child de `<html>`

   `<body>` es el last child de `<html>`

   y:

   `<head>` tiene un child : `<title>`

   `<title>` tiene un child (un text node): "Tutorial DOM"

   `<body>` tiene dos childs: `<h1>` y `<p>`

   `<h1>` tiene un child: "Lección uno de DOM"

   `<p>` tiene un child: "¡Hola mundo!"

   `<h1>` y `<p>` son sibings

   <br>

   **_Para navegar entre nodos se usan las sgts properties:_**

   -  parentNode

   -  childNodes[nodenumber]

   -  firstChild

   -  lastChild

   -  nextSibling

   -  previousSibling

   <br>

   Un error comun es esperar que un element node tenga text

   `<title id="demo">DOM Tutorial</title>`

   -  El node element **_tittle_** no contiene texto, contiene un text node con el valor "DOM Tutorial".

   <br>

   -  Se puede accder de varias formas, usando innerHTML

   `myTitle = document.getElementById("demo").innerHTML;`

   <br>

   -  Es lo mismo que acceder al nodeValue del primer child

   `myTitle = document.getElementById("demo").firstChild.nodeValue;`

   <br>

   -  Acceder al primer child tambien se puede hacer así

   `myTitle = document.getElementById("demo").childNodes[0].nodeValue;`

   <br>

   **_Es importante aprender todos estos metodos para comrender la estructura del árbol y la navegation del DOM_**

   <br>
   <br>

   Hay 2 propiedades para acceder al documento completo:

   -  **_document.body_** , cuerpo del documento

   -  **_document.documentElement_** , documento completo

   ```html
   <h2>JavaScript HTMLDOM</h2>
   <p>Displaying document.body</p>

   <p id="demo"></p>

   <script>
      document.getElementById("demo").innerHTML = document.body.innerHTML;
   </script>
   <!-- Vuelve a pintar el h2 y el p -->
   ```

   <br>
   <br>

   Propiedad **_nodeName_** especifica el nombre de un nodo

   -  Es **_solo de lectura_**

   -  De un elemento es igual al tag

   -  De un atributo es el name del attribute

   -  De un text node es #text

   -  De un document node es #document

   -  **_nodeName_** siempre contiene el nombre de la **_etiqueta en mayúsculas de un elemento HTML_**.

   `document.getElementById("id02").innerHTML = document.getElementById("id01").nodeName;`

   <br>
   <br>

   Propiedad **_nodeValue_** especifica el valor de un nodo

   -  Si es de un elemento = **_null_**

   -  Si es un text node, sera el texto

   -  Si es un attribute node, sera el atributo

   <br>
   <br>

   Propiedad **_nodeType_** solo de lectura, devuelve el tipo de un node

   ```html
   <h1 id="id01">My First Page</h1>
   <p id="id02"></p>

   <script>
      document.getElementById("id02").innerHTML = document.getElementById("id01").nodeType;
   </script>
   <!-- 1 -->
   ```

   -  **_ELEMENT_NODE (1):_** `<h1 class="heading">W3Schools</h1>`

   -  **_ATTRIBUTE_NODE (2):_** ` class = "heading" (deprecated - obsoleto)`

   -  **_TEXT_NODE (3):_** ` W3Schools`

   -  **_COMMENT_NODE (8):_** `<!-- This is a comment -->`

   -  **_DOCUMENT_NODE (9):_** `The HTML document itself (the parent of <html>)`

   -  **_DOCUMENT_TYPE_NODE (10):_** `<!Doctype html>`

   El tipo 2 esta en desuso en HTML DOM (pero funciona), pero no en XML DOM

2. # **CREACIÓN DE NUEVOS HTML ELEMENTS (NODES)**

   Para agregar un nuevo elemento al HTML DOM, primero debe crear el elemento (nodo de elemento) y luego agregarlo a un elemento existente.

   ```html
   <div id="div1">
      <p id="p1">This is a paragraph.</p>
      <p id="p2">This is another paragraph.</p>
   </div>

   <script>
      const para = document.createElement("p");
      const node = document.createTextNode("This is new.");
      para.appendChild(node);
      const element = document.getElementById("div1");
      element.appendChild(para);
   </script>
   ```

      <br>

   **_Explicacion_**

   -  Crea un nuevo `<p>` : `const para = document.createElement("p");`

   -  Para agregar texto al elemento `<p>` , primero debe crear un nodo de texto. Este código crea un nodo de texto: `const node = document.createTextNode("This is a new paragraph.");`

   -  Luego se agrega el text node a `<p>` : `para.appendChild(node);`

   -  Finalmente, debe agregar el nuevo elemento a un elemento existente, este code **_encuentra_** un **_elemento existente_**: `const element = document.getElementById("div1");`

   -  Agrega el nuevo elemento al elemento existente: `element.appendChild(para);`

   -  Cabe aclarar que antes habian 2 `<p>` y `appendChild(para)` lo añadió al final. Si quieres que vaya al inicio usa `insertBefore()`

      <br>
      <br>

   **_insertBefore(newElement,afterElement)_**

   ```html
   <div id="div1">
      <p id="p1">This is a paragraph.</p>
      <p id="p2">This is another paragraph.</p>
   </div>

   <script>
      const para = document.createElement("p");
      const node = document.createTextNode("This is new.");
      para.appendChild(node);

      const element = document.getElementById("div1");
      const child = document.getElementById("p1");
      element.insertBefore(para, child); // que el parrafo "para" este antes del parrafo "child"
   </script>
   ```

      <br>
      <br>

   **_remove()_** elimina un HTML element

   ```html
   <div>
      <p id="p1">This is a paragraph.</p>
      <p id="p2">This is another paragraph.</p>
   </div>

   <button onclick="myFunction()">Remove Element</button>

   <script>
      function myFunction() {
         document.getElementById("p1").remove();
      }
   </script>
   <!-- Elimina al elemento "p1" al clickear el button -->
   ```

   <br>

   Hay algunos navegadores que no admiten el method **_remove()_** , para ellos tienes que encontrar primero al principal node para eliminar el elemento

   ```html
   <div id="div1">
      <p id="p1">This is a paragraph.</p>
      <p id="p2">This is another paragraph.</p>
   </div>

   <script>
      const parent = document.getElementById("div1");
      const child = document.getElementById("p1");
      parent.removeChild(child);
   </script>
   ```

   <br>

   Otra solucion sería encontrar el elemento que se desea eliminar y luego usa **_parentNode property_** para encontrar el parent

   ```javascript
   const child = document.getElementById("p1");
   child.parentNode.removeChild(child);
   ```

   <br>
   <br>

   **_replaceChild(new,remove)_** sirve para reemplazar un HTML element

   ```html
   <div id="div1">
      <p id="p1">This is a paragraph.</p>
      <p id="p2">This is another paragraph.</p>
   </div>

   <script>
      const para = document.createElement("p");
      const node = document.createTextNode("This is new.");
      para.appendChild(node);

      const parent = document.getElementById("div1");
      const child = document.getElementById("p1");
      parent.replaceChild(para, child); // reemplaza child con para
   </script>
   ```

   <br>
   <br>

   ## **_HTMLCollection Object_**

   El **_getElementsByTagName()_** method, devuelve un objeto HTMLCollection, que es una lista como un array de HTML elements.

   ```javascript
   const myCollection = document.getElementsByTagName("p");
   ```

   Este code selecciona a todos los `<p>` elements del document.

   Para acceder a los elementos `<p>` lo puedes hacer con un indice, como los array. **_myCollection[1]_** para acceder al **_Segundo elemento_**

   **_NOTA_** el index comienza con **_ZERO_**

   <br>
   <br>

   -  Tambien se puede saber su longitud con la property **_length_**

   `myCollection.length`

   ```html
   <p>Hello World!</p>

   <p>Hello Norway!</p>

   <p id="demo"></p>

   <script>
   const myCollection = document.getElementsByTagName("p");

   document.getElementById("demo").innerHTML = "This document contains " + myCollection.length + " paragraphs.";
   ```

   <br>

   -  Es muy útil cuando se desea recorrer los elementos de una collection.

   ```html
   <p>Hello World!</p>

   <p>Hello Norway!</p>

   <p>Click the button to change the color of all p elements.</p>

   <button onclick="myFunction()">Try it</button>

   <script>
      function myFunction() {
         const myCollection = document.getElementsByTagName("p");
         for (let i = 0; i < myCollection.length; i++) {
            myCollection[i].style.color = "red";
         }
      }
   </script>
   <!-- Vuelve rojo el texto de todos los parrafos -->
   ```

   <br>

   **_HTMLCollection NO_** es un **_ARRAY_**, recorre la lista como un array pero no lo es. Además no puede usar sus methods.

   <br>
   <br>

   ## **_HTML DOM NodeList_**

   Es una collection de nodos extraidos del document

   Es casi como un **_HTMLCollection_**

   Algunos navegadores antiguos devuelven un NodeList en vez de HTMLCollection con **_getElementsByClassName()_**

   Todos los navegadores devuelven un Nodelist object para la property **_childNodes_**

   La mayoria de browser devuelve un NodeList object para **_querySelectorAll()_**

   ```javascript
   const myNodeList = document.querySelectorAll("p");
   ```

   -  Selecciona todos los `<p>` , para acceder a ellos se hace como si fuera un array `myNodeList[1]`

   -  Tambien se puede usar la property **_length_**

   <br>

   Diferencias con **_HTMLCollection y NodeList_**

   -  Una HTMLCollection es una colección de elementos de documento .

   -  Una lista de nodos es una colección de nodos de documentos (nodos de elementos, nodos de atributos y nodos de texto)

   -  Se puede acceder a **_HTMLCollection_** por su nombre, id o index

   -  Se puede acceder a **_NodeList_** por su número de indice (index)

   -  Los métodos **_getElementsByClassName() y getElementsByTagName()_** devuelven una **_HTMLCollection activa_**.

   -  El **_querySelectorAll()_** método devuelve una **_lista de nodos estática_**.

   -  Ambos no son arrays.

   <br>
   <br>

   # **BROWSER OBJECT MODEL (BOM)**

   Permite que JS "**_hable con_** el navegador.

   1. # **WINDOW OBJECT**

      Es compatible con todos los navegadores

      Todos los objetos, funciones y variables globales de JavaScript se convierten automáticamente en miembros del objeto de ventana.

      Las variables globales son propiedades del objeto ventana.

      Las funciones globales son métodos del objeto ventana.

      Incluso el objeto del documento (del HTML DOM) es una propiedad del objeto de la ventana

      ```javascript
      window.document.getElementById("header");
      // es igual que ...
      document.getElementById("header");
      ```

      <br>
      <br>

      ## **TAMAÑO DE WINDOW**

      -  **_window.innerHeight_** la altura interior de la ventana del navegador (en píxeles)

      -  **_window.innerWidth_** el ancho interior de la ventana del navegador (en píxeles)

      **_NOTA:_** La ventana del navegador (la ventana del navegador) **_NO incluye_** barras de herramientas ni barras de desplazamiento.

      ```html
      <script>
         document.getElementById("demo").innerHTML = "Browser inner window width: " + window.innerWidth + "px<br>" + "Browser inner window height: " + window.innerHeight + "px";
      </script>
      ```

      <br>

      Algunos methods de window:

      -  **_window.open()_** abrir una nueva ventana

      -  **_window.close()_** cerrar la ventana actual

      -  **_window.moveTo()_** mover la ventana actual

      -  **_window.resizeTo()_** cambiar el tamaño de la ventana actual

      <br>
      <br>

      ## **SCREEN DE WINDOW**

      El **_objeto_** **_window.screen_** contiene información sobre la pantalla del usuario

      El **_window.screen_** objet se puede escribir sin el prefijo de window

      Properties:

      -  **_screen.width_** devuelve el ancho de la pantalla del visitante en píxeles

      -  **_screen.height_**

      -  **_screen.availWidth_**

      -  **_screen.availHeight_**

      -  **_screen.colorDepth_**

      -  **_screen.pixelDepth_**

      <br>
      <br>

      Muestra el width de una window en px

      ```html
      <p id="demo"></p>

      <script>
         document.getElementById("demo").innerHTML = "Screen width is " + screen.width;
      </script>
      ```

      <br>

      Muestra el heigth de una window en px

      ```javascript
      document.getElementById("demo").innerHTML = "Screen Height: " + screen.height;
      ```

      <br>
      <br>

      ## **UBICACION DE LA JS WINDOW**

      El **_window.location_** objet se puede utilizar para **_obtener_** la dirección de la página actual **_(URL)_** y para **_redirigir el navegador a una nueva página_**.

      El **_window.location_** objet se puede escribir sin el prefijo de **_window_**

      -  **_window.location.href_** devuelve el href **_(URL)_** de la página actual

      ```javascript
      document.getElementById("demo").innerHTML = "Page location is " + window.location.href;
      /* https://www.w3schools.com/js/js_window_location.asp */
      ```

      <br>

      -  **_window.location.hostname_** devuelve el nombre de dominio del servidor web

      ```javascript
      document.getElementById("demo").innerHTML = "Page hostname is " + window.location.hostname;
      // Page hostname is www.w3schools.com
      ```

      <br>

      -  **_window.location.pathname_** devuelve la ruta y el nombre de archivo de la página actual

      ```javascript
      document.getElementById("demo").innerHTML = "Page path is " + window.location.pathname;
      // Page path is /js/js_window_location.asp
      ```

      <br>

      -  **_window.location.protocol_** devuelve el protocolo web utilizado **_(http: o https:)_**

      ```javascript
      document.getElementById("demo").innerHTML = "Page protocol is " + window.location.protocol;
      // Page protocol is https:
      ```

      <br>

      -  **_window.location.assign()_** carga un nuevo documento

      ```html
      <input type="button" value="Load new document" onclick="newDoc()" />

      <script>
         function newDoc() {
            window.location.assign("https://www.w3schools.com");
         } // carga la pagina de w3schools al dar click al button
      </script>
      ```

      <br>

      -  **_window.location.port_** muestra el port - puerto de host de internet

      ```javascript
      document.getElementById("demo").innerHTML = "The URL port number of the current page is: " + window.location.port;
      ```

      <br>
      <br>

      ## **HISTORIAL DE WINDOW**

      El **_window.history_** objet contiene el **_historial de los navegadores._**

      Para proteger la privacidad de los usuarios, existen limitaciones sobre cómo JavaScript puede acceder a este objeto

      -  **_history.back()_** igual que clickear atras en el navegador

      ```html
      <head>
         <script>
            function goBack() {
               window.history.back();
            }
         </script>
      </head>
      <body>
         <input type="button" value="Back" onclick="goBack()" />
      </body>
      ```

      <br>

      -  **_history.forward()_** igual que clickear adelante en el navegador

      ```html
      <head>
         <script>
            function goForward() {
               window.history.forward();
            }
         </script>
      </head>
      <body>
         <input type="button" value="Forward" onclick="goForward()" />
      </body>
      ```

      ## **WINDOW NAVIGATOR - NAVEGADOR DE VENTANA**

      El **_window.navigator_** objet contiene información sobre el **_navegador del visitante_**.

      El **_window.navigator_** objet se puede escribir sin el prefijo de window

      -  **_navigator.cookieEnabled_** property que devuelve **_true_** si las **_cookies_** están **_habilitadas_**; de lo contrario, devuelve falso

      ```javascript
      document.getElementById("demo").innerHTML = "navigator.cookieEnabled is " + navigator.cookieEnabled;
      // navigator.cookieEnabled is true
      ```

      <br>

      **_platform_** property devuelve la plataforma del navegador (sistema operativo)

      ```javascript
      document.getElementById("demo").innerHTML = navigator.platform;
      ```

      <br>

      **_language_** property devuelve el idioma del navegador

      ```javascript
      document.getElementById("demo").innerHTML = navigator.language;
      // en
      ```

      <br>

      **_online_** property devuelve verdadero si el navegador está en línea

      ```javascript
      document.getElementById("demo").innerHTML = navigator.onLine;
      // true
      ```

      <br>
      <br>

      ## **POPUP BOXES - CUADROS EMERGENTES**

      JavaScript tiene tres tipos de cuadros emergentes: cuadro de alerta, cuadro de confirmación y cuadro de solicitud.

      -  **_Alert Box:_** se usa a menudo si desea asegurarse de que la información llegue al usuario. Cuando aparece un cuadro de alerta, el usuario deberá hacer clic en "Aceptar" para continuar

         El **_window.alert()_** method se puede escribir sin el prefijo de **_window_**.

         ```html
         <button onclick="myFunction()">Try it</button>

         <script>
            function myFunction() {
               alert("I am an alert box!");
            }
         </script>
         ```

         <br>

      -  **_Confirm Box:_** se usa a menudo si desea que el usuario verifique o acepte algo

         Cuando aparece un cuadro de confirmación, el usuario deberá hacer clic en "Aceptar" o "Cancelar" para continuar.

         Si el usuario hace clic en "Aceptar", el cuadro devuelve verdadero . Si el usuario hace clic en "Cancelar", el cuadro devuelve falso .

         El window.confirm()método se puede escribir sin el prefijo de window.

         `window.confirm("sometext");`

         ```html
         <button onclick="myFunction()">Try it</button>

         <p id="demo"></p>

         <script>
            function myFunction() {
               var txt;
               if (confirm("Press a button!")) {
                  // si presiona aceptar es true
                  txt = "You pressed OK!";
               } else {
                  txt = "You pressed Cancel!";
               }
               document.getElementById("demo").innerHTML = txt;
            }
         </script>
         ```

         <br>

      -  **_Prompt Box_** se usa a menudo si desea que el usuario ingrese un valor antes de ingresar a una página.

         Cuando aparece un cuadro emergente, el usuario deberá hacer clic en "Aceptar" o "Cancelar" para continuar después de ingresar un valor de entrada.

         Si el usuario hace clic en "Aceptar", el cuadro devuelve el valor de entrada. Si el usuario hace clic en "**_Cancelar"_**, el cuadro devuelve **_null_**.

         `window.prompt("sometext","defaultText");`

         ```html
         <button onclick="myFunction()">Try it</button>

         <p id="demo"></p>

         <script>
         function myFunction() {
         let text;
         let person = prompt("Please enter your name:", "Harry Potter");
         if (person == null || person == "") {  // si es null o vacio ...
            text = "User cancelled the prompt.";
         } else {
            text = "Hello " + person + "! How are you today?";
         }
         document.getElementById("demo").innerHTML = text;
         }
         ```

      ## **TIMING EVENTS - TEMPORIZADOR DE EVENTOS**

      JavaScript se puede ejecutar en intervalos de tiempo.

      Esto se llama eventos de tiempo.

      El **_window object_** permite la ejecución de código en intervalos de tiempo específicos

      -  **_setTimeout(function, milliseconds)_**
         Ejecuta una función, después de esperar un número específico de milisegundos.

         ```html
         <button onclick="setTimeout(myFunction, 3000);">Try it</button>

         <script>
         function myFunction() {
         alert('Hello');
         }
         // se execute la alert 3 seconds after
         ```

         <br>

         **_clearTimeout()_** method detiene la ejecución de la función especificada en setTimeout().
         `window.clearTimeout(timeoutVariable)`

         **_clearTimeout()_** method utiliza la variable devuelta por setTimeout()

         Si la ejecucion aun no se ha dado, puede usar **_clearTimeout()_** . Se puede escribir sin el prefijo **_window_**

         `window.clearTimeout(timeoutVariable)`

         ```javascript
         <button onclick="myVar = setTimeout(myFunction, 3000)">Try it</button>

         <button onclick="clearTimeout(myVar)">Stop it</button>

         <script>
         function myFunction() {
         alert("Hello");
         }
         ```

         <br>

      -  **_setInterval(function, milliseconds)_**
         Igual que setTimeout(), pero repite la ejecución de la función continuamente.

         ```html
         <p id="demo"></p>

         <script>
            setInterval(myTimer, 1000);

            function myTimer() {
               const d = new Date();
               document.getElementById("demo").innerHTML = d.toLocaleTimeString();
            }
         </script>
         ```

         De la misma manera se usa **_clearInterval()_**

         `window.clearInterval(timerVariable)`

         <br>

      Los **_setTimeout() y setInterval()_** son ambos métodos del objeto HTML DOM Window.

      <br>
      <br>

      ## **COOKIES JS**

      Las cookies le permiten **_almacenar información del usuario_** en las páginas web

      Las cookies son datos, almacenados en pequeños archivos de texto, en su computadora.

      Cuando un servidor web ha enviado una página web a un navegador, la conexión se cierra y el servidor se olvida de todo sobre el usuario.

      Las cookies se inventaron para resolver el problema "cómo recordar información sobre el usuario":

      -  Cuando un usuario visita una página web, su nombre puede almacenarse en una cookie.

      -  La próxima vez que el usuario visite la página, la cookie "recordará" su nombre.

      Las cookies se guardan en pares de **_nombre-valor_** como:

      `username = John Doe`

      Cuando un navegador solicita una página web de un servidor, las cookies que pertenecen a la página se agregan a la solicitud. De esta forma, el servidor obtiene los datos necesarios para "recordar" información sobre los usuarios.

      Una cookie se elimina cuando se cierra el browser

      <br>

      ### **_CREAR UNA COOKIE CON JS_**

      JavaScript puede crear, leer y eliminar cookies con la **_document.cookie_** property

      Con JavaScript, se puede crear una cookie como esta:

      ```javascript
      document.cookie = "username=John Doe";
      ```

      <br>

      ### **_LEER UNA COOKIE CON JS_**

      Con JavaScript, las cookies se pueden leer así:

      ```javascript
      let x = document.cookie;
      ```

      **_document.cookie_** devolverá todas las cookies en una cadena como: **_cookie1=value; galleta2=value; cookie3=value;_**

      <br>

      ### **_CAMBIAR UNA COOKIE CON JS_**

      Puede cambiar una cookie de la misma manera que la crea:

      ```javascript
      document.cookie = "username=John Smith; expires=Thu, 18 Dec 2013 12:00:00 UTC; path=/";
      ```

      La cookie anterior se sobrescribe.

      <br>

      ### **_ELIMINAR UNA COOKIE CON JS_**

      No tiene que especificar un valor de cookie cuando elimina una cookie.

      Simplemente establezca el parámetro de expiración en una fecha pasada

      ```javascript
      document.cookie = "username=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/;";
      ```

      Debe definir la ruta de la cookie para asegurarse de eliminar la cookie correcta.

      Algunos navegadores no le permitirán eliminar una cookie si no especifica la ruta.

      <br>

      ### **_EXAMPLE DE COOKIE_**

      -  Crear una cookie que almacena el nombre de un visitante. La primera vez que un visitante llega a la página web, se le pedirá que introduzca su nombre. A continuación, el nombre se almacena en una cookie. La próxima vez que el visitante llegue a la misma página, recibirá un mensaje de bienvenida.

         <br>

         Se crearan 3 funciones para esto

         -  Una función para establecer un valor de cookie

         ```javascript
         function setCookie(cname, cvalue, exdays) {
            const d = new Date();
            d.setTime(d.getTime() + exdays * 24 * 60 * 60 * 1000);
            let expires = "expires=" + d.toUTCString();
            document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
         }
         // La función establece una cookie sumando el nombre de la cookie, el valor de la cookie y la cadena de expiración
         ```

         <br>

         -  Una función para obtener un valor de cookie.

         ```javascript
         function getCookie(cname) {
            let name = cname + "=";
            let decodedCookie = decodeURIComponent(document.cookie);
            let ca = decodedCookie.split(";");
            for (let i = 0; i < ca.length; i++) {
               let c = ca[i];
               while (c.charAt(0) == " ") {
                  c = c.substring(1);
               }
               if (c.indexOf(name) == 0) {
                  return c.substring(name.length, c.length);
               }
            }
            return "";
         }
         ```

         Tome el nombre de la cookie como parámetro (cname).

         Cree una variable (nombre) con el texto a buscar (cname + "=").

         Decodificar la cadena de cookies, para manejar cookies con caracteres especiales, por ejemplo, '$'

         Divida document.cookie en punto y coma en una matriz llamada ca (ca = decodedCookie.split(';')).

         Recorra la matriz ca (i = 0; i < ca.length; i++) y lea cada valor c = ca[i]).

         Si se encuentra la cookie (c.indexOf(name) == 0), devuelva el valor de la cookie (c.substring(name.length, c.length).

         Si no se encuentra la cookie, devuelva "".

         <br>

         -  Una función para comprobar el valor de una cookie.

            Si la cookie está configurada, mostrará un saludo.

            Si la cookie no está configurada, mostrará un cuadro de aviso, solicitando el nombre del usuario, y almacena la cookie de nombre de usuario durante 365 días

         ```javascript
         function checkCookie() {
            let username = getCookie("username");
            if (username != "") {
               alert("Welcome again " + username);
            } else {
               username = prompt("Please enter your name:", "");
               if (username != "" && username != null) {
                  setCookie("username", username, 365);
               }
            }
         }
         ```

         <br>

         **_TODO JUNTO_**

         ```html
         <script>
         function setCookie(cname,cvalue,exdays) {
         const d = new Date();
         d.setTime(d.getTime() + (exdays*24*60*60*1000));
         let expires = "expires=" + d.toUTCString();
         document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
         }

         function getCookie(cname) {
         let name = cname + "=";
         let decodedCookie = decodeURIComponent(document.cookie);
         let ca = decodedCookie.split(';');
         for(let i = 0; i < ca.length; i++) {
            let c = ca[i];
            while (c.charAt(0) == ' ') {
               c = c.substring(1);
            }
            if (c.indexOf(name) == 0) {
               return c.substring(name.length, c.length);
            }
         }
         return "";
         }

         function checkCookie() {
         let user = getCookie("username");
         if (user != "") {
            alert("Welcome again " + user);
         } else {
            user = prompt("Please enter your name:","");
            if (user != "" && user != null) {
               setCookie("username", user, 30);
            }
         }
         }
         </script>
         </head>

         <body onload="checkCookie()"></body>
         <!-- El ejemplo ejecuta la checkCookie()función cuando se carga la página -->
         ```

<br>
<br>

# **WEB API**

API significa Interfaz de programación de aplicaciones

Una API de navegador puede ampliar la funcionalidad de un navegador web

Una API de servidor puede ampliar la funcionalidad de un servidor web.

Puede simplificar enormemente funciones complejas.

Puede proporcionar una sintaxis fácil para código complejo.

1. # **API del navegador**

   Todos los navegadores tienen un conjunto de API web integradas para admitir operaciones complejas y ayudar a acceder a los datos

   Por ejemplo, la API de geolocalización puede devolver las coordenadas de dónde se encuentra el navegador

   ```html
   <button onclick="getLocation()">Try It</button>

   <p id="demo"></p>

   <script>
      const x = document.getElementById("demo");

      function getLocation() {
         try {
            navigator.geolocation.getCurrentPosition(showPosition);
         } catch {
            x.innerHTML = err;
         }
      }

      function showPosition(position) {
         x.innerHTML = "Latitude: " + position.coords.latitude + "<br>Longitude: " + position.coords.longitude;
      }
   </script>
   ```

   <br>

2. # **API de Terceros**

   Las API de terceros no están integradas en su navegador.

   Para utilizar estas API, deberá descargar el código de la Web

   -  API de YouTube: le permite mostrar videos en un sitio web.

   -  API de Twitter: le permite mostrar Tweets en un sitio web.

   -  API de Facebook: le permite mostrar información de Facebook en un sitio web.

   <br>

3. # **API Validation**

   **_checkValidity()_** retorna **_true_** si un input contiene datos validos

   **_setCustomValidity()_** establece la property **_validationMessage_** de un input

   ```html
   <input id="id1" type="number" min="100" max="300" required />
   <button onclick="myFunction()">OK</button>

   <p>If the number is less than 100 or greater than 300, an error message will be displayed.</p>

   <p id="demo"></p>

   <script>
      function myFunction() {
         const inpObj = document.getElementById("id1");
         if (!inpObj.checkValidity()) {
            document.getElementById("demo").innerHTML = inpObj.validationMessage;
         } else {
            document.getElementById("demo").innerHTML = "Input OK";
         }
      }
   </script>
   ```

   -  Propiedades DOM de validación de restricciones

   **_validity_** contiene properties booleanas relacionadas a la validez de un input

   **_validationMessage_** contiene el message un browser mostrará cuando el validity sea false

   **_willValidate_** indica si un input sería validado

   -  Propiedades de validez de un Input: contiene una serie de propiedades relacionadas con la validez de los datos

   **_customError_** true, si se establece un message de validity personalizado

   **_rangeOverflow_** true, si el valor de un elemento es mayor que el attribute maximo

   **_rangeUnderflow_** true, si el valor de un elemento es menor que el attribute minimo

   <br>

   Si el número en un campo de entrada es mayor que 100 (el max atributo de la entrada), muestra un mensaje

   ```html
   <input id="id1" type="number" max="100" />
   <button onclick="myFunction()">OK</button>

   <p>If the number is greater than 100 (the input's max attribute), an error message will be displayed.</p>

   <p id="demo"></p>

   <script>
      function myFunction() {
         let text;
         if (document.getElementById("id1").validity.rangeOverflow) {
            text = "Value too large";
         } else {
            text = "Input OK";
         }
         document.getElementById("demo").innerHTML = text;
      }
   </script>
   ```

   <br>

   Si el número en un campo de entrada es menor que 100 (el minatributo de la entrada), muestra un mensaje

   ```html
   <input id="id1" type="number" min="100" />
   <button onclick="myFunction()">OK</button>

   <p>If the number is less than 100 (the input's min attribute), an error message will be displayed.</p>

   <p id="demo"></p>

   <script>
      function myFunction() {
         let text;
         if (document.getElementById("id1").validity.rangeUnderflow) {
            text = "Value too small";
         } else {
            text = "Input OK";
         }
         document.getElementById("demo").innerHTML = text;
      }
   </script>
   ```

   <br>
   <br>

4. # **WEB HISTORY API**

   La API de historial web proporciona métodos sencillos para acceder al objeto windows.history.

   El objeto window.history contiene las URL (sitios web) visitadas por el usuario.

   **_go()_** carga una URL específica de la lista de historial

   ```html
   <button onclick="myFunction()">Go Back 2 Pages</button>

   <script>
      function myFunction() {
         window.history.go(-2); /* Regresa 2 paginas atras */
      }
   </script>
   ```

   <br>
   <br>

5. # **WEB STORAGE API - API DE ALMACENAMIENTO WEB**

   Es una sintaxis simple para almacenar y recuperar datos en el navegador

   <br>

   **_LocalStorage object_** proporciona acceso a un almacenamiento local para un sitio web en particular.

   Le permite almacenar, leer, agregar, modificar y eliminar elementos de datos para ese dominio.

   Los datos se almacenan sin fecha de vencimiento y no se eliminarán cuando se cierre el navegador.

   Los datos estarán disponibles por días, semanas y años.

   <br>

   **_localStorage.setItem()_** method almacena un elemento de datos en un almacenamiento

   Toma un name and value como parámetros

   `localStorage.setItem("name", "John Doe");`

   <br>

   **_localStorage.getItem()_** recupera un elemento de datos del almacenamiento

   Toma un nombre como parámetro

   `localStorage.getItem("name");`

   <br>
   <br>

   **_sessionStorage object_** es idéntico al objeto **_localStorage_**.

   La diferencia es que el objeto sessionStorage almacena datos para una sesión.

   Los datos se eliminan cuando se cierra el navegador.

   ```javascript
   sessionStorage.setItem("name", "John Doe");
   document.getElementById("demo").innerHTML = sessionStorage.getItem("name");
   ```

   Tambien cuenta con los metodos **_setItem y getItem_**

   <br>

   Otras propiedades y metodos:

   **_length_** retorna el numero de datos almacenados en el Storage object

   **_clear()_** limpia todas las keys del almacenamiento

   <br>
   <br>

6. # **WEB WORKER**

   Es un JS que se **_ejecuta en segundo plano_**, **_sin afectar_** el **_rendimiento_** de la página.

   Cuando se executing varios commands en un HTML, la pagina deja de responder hasta que finaliza la secuencia de commads

   El web worker se ejecuta independientemente de otros **_scripts_** sin afectar el rendimiento de la pagina. Puedes continuar haciendo **_click, seleccionar cosas, etc_** , mientras el web worker se execute in second plane

   ```html
   <!-- Todo el codigo del web worker -->
   <p>Count numbers: <output id="result"></output></p>
   <button onclick="startWorker()">Start Worker</button>
   <button onclick="stopWorker()">Stop Worker</button>

   <script>
      let w;

      function startWorker() {
         if (typeof w == "undefined") {
            w = new Worker("demo_workers.js");
         }
         w.onmessage = function (event) {
            document.getElementById("result").innerHTML = event.data;
         };
      }

      function stopWorker() {
         w.terminate();
         w = undefined;
      }
   </script>
   ```

   ## **CREAR UN WEB WORKER**

   Crealo en un JS externo.

   Creamos un script que cuenta (example). El script se almacena en el archivo "demo_worker.js" (example)

   ```javascript
   // va en el web worker
   let i = 0;

   function timedCount() {
      i++;
      postMessage(i); // sirve para enviar un message al HTML
      setTimeout("timedCount()", 500);
   }

   timedCount();
   ```

   **_NOTA_** Normalmente, los web worker no se utilizan para scripts tan simples, sino para tareas más intensivas de CPU.

   <br>

   ## **CREAR UN WEB WORKER OBJECT**

   Este codigo verifica si el web worker ya existe, en caso de que no, crea un nuevo web worker

   ```javascript
   if (typeof w == "undefined") {
      w = new Worker("demo_workers.js");
   }
   ```

   <br>

   Ahora podemos enviar y recibir message del web worker.

   Añadiré un detector de eventos "onmessage" al web worker

   ```javascript
   w.onmessage = function (event) {
      document.getElementById("result").innerHTML = event.data;
   }; // puede decir event o e, data es su propiedad
   ```

   Cuando el web worker publica un mensaje, se ejecuta el código dentro del detector de eventos (message). Los datos del web worker se almacenan en event.data.

   <br>

   ## **TERMINAR UN WEB WORKER**

   Cuando se crea un web worker, seguira viendo el message incluso si el script externo finalizó, para eso se tiene que finalizar el web worker.

   Para finalizar un web worker y recursos gratuitos de browser and computer, se usa el method **_terminate()_**

   `w.terminate();`

   <br>

   ## **REUTILIZAR UN WEB WORKER**

   Para reutilizarlo, establece la variable del web worker en undefined, despues de que se haya terminado

   `w = undefined;`

   <br>
   <br>

   Dado que los **_web worker_** están en archivos externos, no tienen acceso a los siguientes objetos de JavaScript:

   -  window object

   -  document object

   -  parent object

   <br>
   <br>

7. # **FETCH API - API DE RECUPERACIÓN**

   La interfaz Fetch API permite que el navegador web realice solicitudes HTTP a los servidores web.

   **_Ya no es necesario XMLHttpRequest_**

   <br>

   El siguiente ejemplo obtiene un archivo y muestra el contenido

   ```javascript
   let file = "fetch_info.txt";

   fetch(file)
      .then((x) => x.text())
      .then((y) => (document.getElementById("demo").innerHTML = y));
   // Fetch puede hacer lo mismo de una manera más simple que el objeto XMLHttpRequest
   ```

   <br>

   Dado que **_Fetch se basa en async y await_**, el ejemplo anterior podría ser más fácil de entender así:

   ```javascript
   getText("fetch_info.txt");

   async function getText(file) {
      let x = await fetch(file);
      let y = await x.text();
      document.getElementById("demo").innerHTML = y;
   }
   ```

   <br>

   O mejor use nombres comprensibles en lugar de x e y

   ```javascript
   getText("fetch_info.txt");

   async function getText(file) {
      let myObject = await fetch(file);
      let myText = await myObject.text();
      document.getElementById("demo").innerHTML = myText;
   }
   ```

   <br>
   <br>

8. # **API DE GEOLOCALIZACION WEB**

   La API de geolocalización HTML se utiliza para obtener la posición geográfica de un usuario

   La geolocalización es más precisa para dispositivos con GPS, como los teléfonos inteligentes.

   La API de geolocalización solo funcionará en contextos seguros como HTTPS.

   Si su sitio está alojado en un origen no seguro (como HTTP), las solicitudes NO funcionaran

   <br>

   ## **USO DE LA API DE GEOLOCATION**

   **_getCurrentPosition()_** method se utiliza para devolver la posición del usuario

   El example devolverá la latitud y longitud de la position del usuario

   ```html
   <button onclick="getLocation()">Try It</button>

   <p id="demo"></p>

   <script>
   const x = document.getElementById("demo");

   function getLocation() {
   if (navigator.geolocation) {  // si el navegador puede usar geolocation entonces
      navigator.geolocation.getCurrentPosition(showPosition);
   } else {
      x.innerHTML = "Geolocation is not supported by this browser.";
   }
   }

   function showPosition(position) {
   x.innerHTML = "Latitude: " + position.coords.latitude +
   "<br>Longitude: " + position.coords.longitude;
   }
   ```

   <br>

   -  Comprueba si se puede usar geolocation en el browser

   -  Si se puede execute **_getCurrentPosition()_**. Si no, mostrar un mensaje al usuario. Se usa principalmente para manejar errores

   -  Si el método **_getCurrentPosition()_** tiene éxito, devuelve un objeto de coordenadas a la función especificada en el parámetro (**_showPosition_**)

   -  La función **_showPosition()_** genera la latitud y la longitud

   <br>

   Para mostrar el resultado en un mapa estatico y no con coordenadas, se requiere un acceso a google maps.

   ```javascript
   function showPosition(position) {
   let latlon = position.coords.latitude + "," + position.coords.longitude;

   let img_url = "https://maps.googleapis.com/maps/api/staticmap?center=
   "+latlon+"&zoom=14&size=400x300&sensor=false&key=YOUR_KEY";

   document.getElementById("mapholder").innerHTML = "<img src='"+img_url+"'>";
   }
   ```

   <br>

   Otros methods

   -  **_watchPosition()_** Devuelve la posición actual del usuario y continúa devolviendo la posición actualizada a medida que el usuario se mueve (como el GPS en un automóvil).

   -  **_clearWatch()_** Detiene el watchPosition() method.

   Para usar estos methods se necesita un equipo GPS como los celulares.

   ```html
   <button onclick="getLocation()">Try It</button>

   <p id="demo"></p>

   <script>
   const x = document.getElementById("demo");

   function getLocation() {
   if (navigator.geolocation) {
      navigator.geolocation.watchPosition(showPosition);
   } else {
      x.innerHTML = "Geolocation is not supported by this browser.";
   }
   }

   function showPosition(position) {
      x.innerHTML="Latitude: " + position.coords.latitude +
      "<br>Longitude: " + position.coords.longitude;
   }
   ```

   <br>
   <br>

# **AJAX**

Permite leer datos de un servidor web, después de que se haya cargado la página

Actualizar una página web sin recargar la página

Enviar datos a un servidor web - en segundo plano

No es un lenguaje de programacion

Es una tecnica para **_acceder a servidores web_** desde una web page

AJAX significa JavaScript asíncrono y XML.

-  Ejemplo

```html
<div id="demo">
   <h2>Let AJAX change this text</h2>
   <button type="button" onclick="loadDoc()">Change Content</button>
</div>
<script>
   function loadDoc() {
      const xhttp = new XMLHttpRequest();
      xhttp.onload = function () {
         document.getElementById("demo").innerHTML = this.responseText;
      };
      xhttp.open("GET", "ajax_info.txt", true);
      xhttp.send();
   }
</script>
```

   <br>

`<div>` se utiliza para mostrar información de un servidor

La función solicita datos de un servidor web y los muestra

   <br>

**_AJAX_** usa una combinacion de:

-  Un objeto XMLHttpRequest integrado en el navegador (para solicitar datos de un servidor web)

-  JavaScript y HTML DOM (para mostrar o usar los datos)

Las aplicaciones AJAX pueden usar XML para transportar datos, pero es igualmente común transportar datos como texto sin formato o texto JSON.

   <br>

**_AJAX permite que las páginas web se actualicen de forma asíncrona mediante el intercambio de datos con un servidor web en segundo plano. Esto significa que es posible actualizar partes de una página web sin recargar toda la página._**

   <br>

-  Como funciona AJAX

![AJAX](./imgs/ajax.gif)

1. Se produce un evento en una página web (se carga la página, se hace clic en un botón)

2. JavaScript crea un objeto XMLHttpRequest

3. El objeto XMLHttpRequest envía una solicitud a un servidor web

4. El servidor procesa la solicitud

5. El servidor envía una respuesta a la página web.

6. La respuesta es leída por JavaScript

7. JavaScript realiza la acción adecuada (como la actualización de la página)

   <br>

## **_Navegadores modernos (Fetch API)_**

Los navegadores modernos pueden usar la API Fetch en lugar del objeto XMLHttpRequest.

La interfaz Fetch API permite que el navegador web realice solicitudes HTTP a los servidores web.

Si usa el objeto XMLHttpRequest, Fetch puede hacer lo mismo de una manera más simple.

<br>
<br>

# **AJAX: el objeto XMLHttpRequest**

-  Crear un objeto XMLHttpRequest

-  Definir una función callback

-  Abra el objeto XMLHttpRequest

-  Enviar una solicitud a un servidor

<br>

## **_XMLHttpRequest Object_**

[XML File](https://www.w3schools.com/js/cd_catalog.xml)

Todos los navegadores modernos admiten el XMLHttpRequestobjeto.

Se puede utilizar para intercambiar datos con un servidor web en segundo plano. Esto significa que es posible actualizar partes de una página web sin recargar toda la página.

La pagina web y el archivo XML que desean cargar **_deben estar en el mismo server_** todos los archivos que hay de ejemplos estan en el dominio de dichas paginas, no en dominio externos

<br>

## **_Crear un objeto XMLHttpRequest_**

Todos los browser tienen un objeto integrado XMLHttpRequest

**_Syntax_**

```javascript
variable = new XMLHttpRequest();
```

<br>

## **_Definir una Callback function_**

Se pasa como parámetro

El callback debe contener la funcion a ejecutar cuando la respuesta **_(response)_** este lista

```javascript
xhttp.onload = function () {
   // What to do when the response is ready
};
```

<br>

## **_Enviar un Request (Solicitud, peticion)_**

Para enviar un request a un server, pueden usar los métodos **_open() y send()_** del **_XMLHttpRequest object_**

```javascript
xhttp.open("GET", "ajax_info.txt", true);
xhttp.send();
```

El archivo del method **_open()_** es una direccion a un archivo del server

<br>

**_El archivo puede ser cualquier tipo de archivo, como .txt y .xml, o archivos de secuencias de comandos del servidor como .asp y .php (que pueden realizar acciones en el servidor antes de devolver la respuesta)._**

Los request del server deben enviarse de forma asynchronous, el parametro del **_open()_** method debe establecerse en **_true_**

`xhttp.open("GET", "ajax_test.asp", true);`

<br>

Al enviar de forma asíncrona, JS **_no tiene que esperar la respuesta del server_**, sino que puede:

Ejecutar otros scripts mientras espera la respuesta del servidor

Tratar el **_response_** después de que el **_response_** esté listo. Su valor por default es **_true_** , no se recomienda ponerlo en **_false_**

<br>

-  Complete Example

```html
<div id="demo">
   <p>Let AJAX change this text.</p>
   <button type="button" onclick="loadDoc()">Change Content</button>
</div>

<script>
   function loadDoc() {
      const xhttp = new XMLHttpRequest();
      xhttp.onload = function () {
         document.getElementById("demo").innerHTML = this.responseText;
      };
      xhttp.open("GET", "ajax_info.txt", true);
      xhttp.send();
   }
</script>
```

<br>

## **_Metodos del object XMLHttpRequest_**

[XML File](https://www.w3schools.com/js/cd_catalog.xml)

**_abort()_** Cancels the current request / Cancela la peticion - solicitud actual

**_open(method, url, async, user, psw)_** Specifies la solicitud

-  method: the request type GET or POST

-  url: the file location

-  async: true (asynchronous) or false (synchronous)

-  user: optional user name

-  psw: optional password

**_send(string)_** Envia la request al server. Usado por peticiones POST

<br>
<br>

## **_Propiedades del objeto XMLHttpRequest_**

**_onload_** define una function para ser llamada cuando la peticion es recibida (loaded - cargado)

**_responseText_** retorna los datos response como un string

**_status_** retorna numeros de status de la request

-  200: "OK" **_(success)_**

-  403: "Forbidden" **_(prohibido)_**

-  404: "Not Found" **_(no encontrado)_**

<br>

**_readyState_** Mantiene the status of the XMLHttpRequest.

-  0: request not initialized

-  1: server connection established

-  2: request received

-  3: processing request

-  4: request finished and response is ready

<br>

**_onload_** Con el XMLHttpRequest objet puede definir una función callback que se ejecutará cuando la request reciba una response.

La función se define en la **_onload_** propiedad del XMLHttpRequestobjeto

```html
<div id="demo">
<h2>The XMLHttpRequest Object</h2>
<button type="button" onclick="loadDoc()">Change Content</button>
</div>

<script>
function loadDoc() {
  const xhttp = new XMLHttpRequest();
  xhttp.onload = function() { // se define la function en onload
    document.getElementById("demo").innerHTML =
    this.responseText;
  }
  xhttp.open("GET", "ajax_info.txt", true);
  xhttp.send();
}
```

<br>

## **Multiples callback functions**

[XML File](https://www.w3schools.com/js/cd_catalog.xml)

Si tiene más de una tarea AJAX en un sitio web, **_debe crear una función para ejecutar el XMLHttpRequest object_** y una función **_callback_** para cada tarea AJAX.

```javascript
loadDoc("url-1", myFunction1);

loadDoc("url-2", myFunction2);

function loadDoc(url, cFunction) {
   const xhttp = new XMLHttpRequest();
   xhttp.onload = function () {
      cFunction(this);
   };
   xhttp.open("GET", url);
   xhttp.send();
}

function myFunction1(xhttp) {
   // action goes here
}
function myFunction2(xhttp) {
   // action goes here
}
```

<br>

```html
<div id="demo">
<h2>The XMLHttpRequest Object</h2>
<button type="button" onclick="loadDoc()">Change Content</button>
</div>

<script>
function loadDoc() {
  const xhttp = new XMLHttpRequest();
  xhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
      document.getElementById("demo").innerHTML =
      this.responseText;
    }
  };
  xhttp.open("GET", "ajax_info.txt");
  xhttp.send();
}
```

<br>
<br>

## **_REQUEST POST_**

[XML file](https://www.w3schools.com/js/cd_catalog.xml)

```javascript
// una simple solicitud post
xhttp.open("POST", "demo_post.asp");
xhttp.send();
```

<br>

Para publicar datos como un formulario HTML, agregue un header - encabezado HTTP con **_setRequestHeader()_**. Especifique los datos que desea enviar en el metodo **_send()_**

```javascript
function loadDoc() {
   const xhttp = new XMLHttpRequest();
   xhttp.onload = function () {
      document.getElementById("demo").innerHTML = this.responseText;
   };
   xhttp.open("POST", "demo_post2.asp");
   xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
   xhttp.send("fname=Henry&lname=Ford"); // esto mismo se puede hacer con el metodo "GET"
}
// result: Hello Henry Ford
```

<br>

**_setRequestHeader(header, value)_**: Agrega encabezados - headers HTTP a la request

**_header_** : specifies el header name

**_value_** : specifies el value name

<br>
<br>

# **SERVER RESPONSE - RESPUESTA DEL SERVIDOR**

[XML File](https://www.w3schools.com/js/cd_catalog.xml)

Server response properties:

**_responseText_** obtiene y devuelve los datos de respuesta como un string

**_responseXML_** obtiene los response data como datos XML

<br>

```javascript
// cambia el contenido de un parrafo
function loadDoc() {
   const xhttp = new XMLHttpRequest();
   xhttp.onload = function () {
      document.getElementById("demo").innerHTML = this.responseText; // retorna los datos de respuesta como string
   };
   xhttp.open("GET", "ajax_info.txt");
   xhttp.send();
}
```

<br>
<br>

El objeto XMLHttpRequest tiene un analizador XML incorporado.

La property **_responseXML_** devuelve la response del servidor como un objeto DOM XML.

```javascript
const xhttp = new XMLHttpRequest();
xhttp.onload = function () {
   const xmlDoc = this.responseXML;
   const x = xmlDoc.getElementsByTagName("ARTIST");
   let txt = "";
   for (let i = 0; i < x.length; i++) {
      txt = txt + x[i].childNodes[0].nodeValue + "<br>";
   }
   document.getElementById("demo").innerHTML = txt;
};
xhttp.open("GET", "cd_catalog.xml");
xhttp.send();
```

<br>
<br>

### **_Metodos del Server Response_**

**_getResponseHeader()_** devuelve la informacion de header specific del recurso del servidor (server resource)

```javascript
const xhttp = new XMLHttpRequest();
xhttp.onload = function () {
   document.getElementById("demo").innerHTML = this.getResponseHeader("Last-Modified");
};
xhttp.open("GET", "ajax_info.txt");
xhttp.send();
```

<br>

**_getAllResponseHeaders()_** devuelve toda la información del encabezado del server resource

```javascript
const xhttp = new XMLHttpRequest();
xhttp.onload = function () {
   document.getElementById("demo").innerHTML = this.getAllResponseHeaders();
};
xhttp.open("GET", "ajax_info.txt");
xhttp.send();
```

<br>
<br>

# **AJAX XML**

[XML File](https://www.w3schools.com/js/cd_catalog.xml)

AJAX se puede utilizar para la comunicación interactiva con un archivo XML

La **_loadDoc()_** function crea un **_XMLHttpRequest_** object, agrega la función que se ejecutará cuando la response del server esté lista y envía la request al server.

Cuando la respuesta del servidor está lista, se construye una tabla HTML

```javascript
function loadDoc() {
   const xhttp = new XMLHttpRequest();
   xhttp.onload = function () {
      myFunction(this);
   };
   xhttp.open("GET", "cd_catalog.xml");
   xhttp.send();
}
function myFunction(xml) {
   const xmlDoc = xml.responseXML;
   const x = xmlDoc.getElementsByTagName("CD");
   let table = "<tr><th>Artist</th><th>Title</th></tr>";
   for (let i = 0; i < x.length; i++) {
      table += "<tr><td>" + x[i].getElementsByTagName("ARTIST")[0].childNodes[0].nodeValue + "</td><td>" + x[i].getElementsByTagName("TITLE")[0].childNodes[0].nodeValue + "</td></tr>";
   }
   document.getElementById("demo").innerHTML = table;
}
```

El [XML File](https://www.w3schools.com/js/cd_catalog.xml) utilizado en el ejemplo anterior tiene este aspecto: **_" cd_catalog.xml "_**.

<br>
<br>

# **APLICACIONES XML**

Este capítulo muestra algunas aplicaciones HTML que utilizan XML, HTTP, DOM y JavaScript. Se usará este [XML File](https://www.w3schools.com/js/cd_catalog.xml)

-  Mostrar datos XML en una tabla HTML

```html
<button type="button" onclick="loadXMLDoc()">Get my CD collection</button>
<br><br>
<table id="demo"></table>

<script>
function loadXMLDoc() {
  const xhttp = new XMLHttpRequest();
  xhttp.onload = function() {
    const xmlDoc = xhttp.responseXML;
    const cd = xmlDoc.getElementsByTagName("CD");
    myFunction(cd)
  }
  xhttp.open("GET", "cd_catalog.xml");
  xhttp.send();
}

function myFunction(cd) {
  let table="<tr><th>Artist</th><th>Title</th></tr>";
  for (let i = 0; i < cd.length; i++) {
    table += "<tr><td>" +
    cd[i].getElementsByTagName("ARTIST")[0].childNodes[0].nodeValue +
    "</td><td>" +
    cd[i].getElementsByTagName("TITLE")[0].childNodes[0].nodeValue +
    "</td></tr>";
  }
  document.getElementById("demo").innerHTML = table;
}
```

<br>
<br>

-  Mostrar el primer CD en un elemento **_HTML div_**

```html
<div id="showCD"></div>

<script>
   const xhttp = new XMLHttpRequest();
   xhttp.onload = function () {
      const xmlDoc = xhttp.responseXML;
      const cd = xmlDoc.getElementsByTagName("CD");
      myFunction(cd, 0);
   };
   xhttp.open("GET", "cd_catalog.xml");
   xhttp.send();

   function myFunction(cd, i) {
      document.getElementById("showCD").innerHTML =
         "Artist: " +
         cd[i].getElementsByTagName("ARTIST")[0].childNodes[0].nodeValue +
         "<br>Title: " +
         cd[i].getElementsByTagName("TITLE")[0].childNodes[0].nodeValue +
         "<br>Year: " +
         cd[i].getElementsByTagName("YEAR")[0].childNodes[0].nodeValue;
   }
</script>
<!-- Artist: Bob Dylan
Title: Empire Burlesque
Year: 1985 -->
```

<br>
<br>

-  Navegar entre los CD

Para navegar cree una función **_next()_** y **_previous()_**

```html
<div id="showCD"></div>
<br />
<input type="button" onclick="previous()" value="<<" />
<input type="button" onclick="next()" value=">>" />

<script>
   let i = 0;
   let len;
   let cd;

   const xhttp = new XMLHttpRequest();
   xhttp.onload = function () {
      const xmlDoc = xhttp.responseXML;
      cd = xmlDoc.getElementsByTagName("CD");
      len = cd.length;
      displayCD(i);
   };
   xhttp.open("GET", "cd_catalog.xml");
   xhttp.send();

   function displayCD(i) {
      document.getElementById("showCD").innerHTML =
         "Artist: " +
         cd[i].getElementsByTagName("ARTIST")[0].childNodes[0].nodeValue +
         "<br>Title: " +
         cd[i].getElementsByTagName("TITLE")[0].childNodes[0].nodeValue +
         "<br>Year: " +
         cd[i].getElementsByTagName("YEAR")[0].childNodes[0].nodeValue;
   }

   function next() {
      if (i < len - 1) {
         i++;
         displayCD(i);
      }
   }

   function previous() {
      if (i > 0) {
         i--;
         displayCD(i);
      }
   }
</script>
<!-- Cambia los artistas por medio de unos buttons -->
```

<br>
<br>

-  Mostrar información del álbum al hacer clic en un CD

```html
<p>Click on a CD to display album information.</p>
<p id="showCD"></p>
<table id="demo"></table>

<script>
   const xhttp = new XMLHttpRequest();
   let cd;
   xhttp.onload = function () {
      const xmlDoc = xhttp.responseXML;
      cd = xmlDoc.getElementsByTagName("CD");
      loadCD();
   };
   xhttp.open("GET", "cd_catalog.xml");
   xhttp.send();

   function loadCD() {
      let table = "<tr><th>Artist</th><th>Title</th></tr>";
      for (let i = 0; i < cd.length; i++) {
         table += "<tr onclick='displayCD(" + i + ")'><td>";
         table += cd[i].getElementsByTagName("ARTIST")[0].childNodes[0].nodeValue;
         table += "</td><td>";
         table += cd[i].getElementsByTagName("TITLE")[0].childNodes[0].nodeValue;
         table += "</td></tr>";
      }
      document.getElementById("demo").innerHTML = table;
   }

   function displayCD(i) {
      document.getElementById("showCD").innerHTML =
         "Artist: " +
         cd[i].getElementsByTagName("ARTIST")[0].childNodes[0].nodeValue +
         "<br>Title: " +
         cd[i].getElementsByTagName("TITLE")[0].childNodes[0].nodeValue +
         "<br>Year: " +
         cd[i].getElementsByTagName("YEAR")[0].childNodes[0].nodeValue;
   }
</script>
<!-- Al hacer click en una cancion se muestra su informacion -->
```
