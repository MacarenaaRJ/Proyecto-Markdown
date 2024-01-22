# Manual React

Escrito por **Macarena Ramos Jiménez**

- email: macarenarj96@gmail.com
- Linkedin: www.linkedin.com/in/macarenarj

# Tabla de contenidos

## React

- [[#Instalación: Linux|Instalación: Linux]]
- [[#Sintaxis básica de JavaScript|Sintaxis básica de JavaScript]]
- [[#Estructuras de Control en JavaScript|Estructuras de Control en JavaScript]]
- [[#Bucles en JavaScript|Bucles en JavaScript]]
- [[#Array (Estructuras de Datos) en JavaScript|Array (Estructuras de Datos) en JavaScript]]
- [[#POO (Programación Orientada a Objetos) en JavaScript|POO (Programación Orientada a Objetos) en JavaScript]]
- [[#Funciones (Modularidad) en JavaScript|Funciones (Modularidad) en JavaScript]]
- [[#Funciones de flecha (Arrow Functions)|Funciones de flecha (Arrow Functions)]]
- [[#Sintaxis básica de React|Sintaxis básica de React]]
- [[#El uso de los Hooks|El uso de los Hooks]]
- [[#CRUD con MYSQL|CRUD con MYSQL]]
- [[#Caso práctico|Caso práctico]]
- [[#Recursos|Recursos]]

# React

React es una herramienta que nos ayuda a construir cosas geniales en internet. Imagina que estás construyendo una casa de juguete con bloques LEGO. React sería como esos bloques, pero para construir páginas web.

### Componentes

En React, todo es como un conjunto de bloques LEGO llamados "componentes". Cada componente es como una pieza individual de tu página web. Puedes tener un componente para el encabezado, otro para el botón, y así sucesivamente.

### JavaScript

JavaScript es un lenguaje de programación que se puede utilizar para hacer que las páginas web sean interactivas.

Imagina que tu aplicación web es una orquesta, y JavaScript es el director que coordina a todos los músicos (o componentes) para tocar la sinfonía perfecta. React, por otro lado, sería uno de esos músicos talentosos.

### JavaScript, HTML, CSS y React

HTML (Lenguaje de Marcado de Hipertexto) es el lenguaje utilizado para estructurar y organizar el contenido de una página web. Piensa en HTML como el esqueleto o la estructura de una página.

CSS (Hojas de Estilo en Cascada) es el lenguaje utilizado para dar estilo y presentación a una página web. HTML sería como la estructura de una casa y CSS como la pintura, los muebles y la decoración que la hacen lucir bien.

Imagina que HTML y CSS son los cimientos y la apariencia de una casa, respectivamente, y JavaScript es el ingeniero que permite que las luces se enciendan, las puertas se abran y la música suene.

React es una biblioteca de JavaScript. Piensa en React como un conjunto de herramientas (o juguetes) que JavaScript utiliza para hacer cosas geniales en tu página web.

### Manipulación del DOM (Document Object Model)

JavaScript tiene la capacidad de interactuar con el DOM, que es la estructura que representa tu página web. Con React, puedes decirle a JavaScript qué partes de la página deben cambiar y cómo deben hacerlo cuando algo sucede, como un clic en un botón.

Ahora ya sabemos algunos conceptos básicos de React. Si no han quedado claro todavía paciencia, con tiempo, práctica y dedicación se irán aclarando. Así que por ahora, continuemos con la instalación.

## Instalación: Linux

Para desarrollar una aplicación React localmente en tu ordenador, necesitarás instalar Node.js. Node.js actúa como un motor que ejecuta JavaScript en tu computadora, permitiendo así su ejecución fuera del navegador.

Para la instalación en Linux se deberá abrir una línea de comandos y ejecutar los comandos mencionados paso por paso. En Linux, se puede abrir la terminal utilizando el atajo de teclado `Ctrl + Alt + T`.

### 1. Actualiza el sistema

```bash
sudo apt update
```

`apt` (Advanced Package Tool) es una herramienta de gestión de paquetes en sistemas operativos basados en Debian, como Ubuntu. Su función principal es facilitar la instalación, actualización y eliminación de software en tu sistema. Este comando asegura tener la información más reciente sobre los paquetes disponibles.

### 2. Instala Node.js y npm

```bash
sudo apt install nodejs npm
```

Este comando instalará tanto Node.js como npm (Node Package Manager) en tu sistema. `npm` es como una tienda en línea para herramientas y bibliotecas de programación en JavaScript. Te permite encontrar, instalar y gestionar todas las piezas de código que necesitas para construir tus aplicaciones.

### 3. Iniciar un nuevo proyecto de React

En la documentación oficial de React recomiendan elegir uno uno de los frameworks hechos con React y más populares en la comunidad si se desea crear una nueva aplicación o un nuevo sitio web completamente con React. Los frameworks brindan funciones que la mayoría de las aplicaciones y los sitios eventualmente necesitan

Las opciones para utilizar React a nivel de producción que se listan en la documentación a día de hoy son las siguientes:

#### Nextjs

[Next.js](https://nextjs.org/) es un framework de React muy completo. Es versátil y permite crear aplicaciones React de cualquier tamaño, desde un blog estático hasta una aplicación dinámica compleja. Para crear un nuevo proyecto Next.js, ejecuta en tu terminal:

```bash
npx create-next-app@latest
```

#### Remix

[Remix](https://remix.run/) es un framework de React muy completo. Con él, puedes organizar tu página en secciones especiales que pueden cargar cosas al mismo tiempo y actualizarse en respuesta a las acciones del usuario. Para crear un nuevo proyecto Remix, ejecuta:

```bash
npx create-remix
```

#### Gatsby

[Gatsby](https://www.gatsbyjs.com/) es un framework de React para sitios web rápidos respaldados por un CMS. Un CMS, o Sistema de Gestión de Contenidos por sus siglas en inglés (Content Management System), es una herramienta que te permite crear, gestionar y modificar contenido en línea sin necesidad de conocimientos avanzados de programación. Para crear un nuevo proyecto de Gatsby, ejecuta:

```bash
npx create-gatsby
```

#### Expo (para aplicaciones nativas)

[Expo](https://expo.dev/) es un framework de React que te permite crear aplicaciones web, iOS y Android universales con interfaces de usuario verdaderamente nativas. Para crear un nuevo proyecto Expo, ejecuta:

```bash
npx create-expo-app
```

Cada uno de estos frameworks ofrecen tutoriales paso a paso para aprender las herramientas en sus páginas web.

Tal vez te estés preguntando ¿puedo usar React sin un framework?

La respuesta es que sí, se puede, pero desde React recomiendan utilizar un framework. La razón es que te resuelven problemas comunes automáticamente y proporcionan una estructura organizada para tu código, facilitando el crecimiento de tu aplicación con el tiempo.

## Sintaxis básica de Javascript

Antes de comenzar con la sintaxis de React, es conveniente conocer unos conceptos básicos de Javascript.

### Tipos de datos

En JavaScript, las variables, tipos de datos y operadores forman la base esencial para la construcción de programas dinámicos y interactivos.

**Variable**
Una variable es como una caja en la que puedes poner información. Imagina que tienes una caja llamada "edad" y dentro de esa caja pones el número 10. Puedes cambiar lo que hay dentro de la caja, y eso es una variable.

Ejemplo de declaración de una variable:

```javascript
let edad = 10;
```

**Constante**
Una constante es similar a una variable, pero con una diferencia clave: una vez que le asignas un valor, no puedes cambiarlo. Imagina que tienes una constante llamada "PI" y le asignas el valor 3.14159. A lo largo de tu programa, este valor permanece constante; no puedes modificarlo. Las constantes son útiles cuando necesitas almacenar información que no debe cambiar durante la ejecución de tu programa.

Ejemplo de declaración de una constante:

```javascript
const PI = 3.14159;
```

**Tipo de Dato**
Los tipos de datos son como etiquetas que le dicen a la computadora qué tipo de información hay dentro de la caja (variable). Por ejemplo, si tienes una caja llamada "nombre" y dentro pones "Ana", el tipo de dato es una cadena de texto, porque estás guardando palabras.

Algunos tipos de datos comunes en Javascript son:

#### 1. Números

Representan valores numéricos.

```javascript
let edad = 25;
let promedio = 8.5;
```

#### 2. **Cadenas de Texto**

Representan una letra o secuencias de caracteres.

```javascript
let nombre = "Carlos";
let mensaje = "Hola, ¿cómo estás?";
let letra = "a";
```

Se pueden definir con una o dos comillas.

#### 3. **Booleanos**

Representan valores de verdad o falsedad.

```javascript
let esEstudiante = true;
let llueve = false;
```

#### 4. Arreglos

Almacenan listas de valores.

```javascript
let frutas = ["manzana", "plátano", "uva"];
```

#### 5. Objetos

Almacenan conjuntos de datos relacionados.

```javascript
let persona = { nombre: "Ana", edad: 30, estudiante: false };
```

#### 6. Indefinido y Nulo

Representan la ausencia de valor.

```javascript
let indefinido = undefined;
let nulo = null;
```

**¿Cuál es la diferencia entre undefined y null?**

- `undefined` representa la ausencia de asignación a una variable o la falta de valor.

Ejemplo: Si tienes una variable llamada `edad` pero aún no has puesto ningún número dentro, `edad` será `undefined`.

```javascript
let edad;
console.log(edad); // Imprimirá undefined
```

- `null` se utiliza para indicar explícitamente que una variable no tiene ningún valor o contenido.

Ejemplo: Si decides vaciar una caja llamada `frutas`, podrías asignarle el valor `null` para indicar que ahora está vacía.

```javascript
let frutas = ["manzana", "plátano", "uva"];
frutas = null; // Ahora frutas está vacío, no tiene ningún valor
```

En resumen, `undefined` generalmente se usa para indicar que algo no ha sido definido o asignado, mientras que `null` se utiliza para expresar deliberadamente que una variable no tiene valor. Ambos son herramientas útiles para manejar la ausencia de datos en tus programas.

**Operador**
Los operadores son como instrucciones que le dicen a la computadora qué hacer con la información dentro de las cajas (variables). Por ejemplo, si tienes una caja llamada "manzanas" con el número 5 dentro, y otra caja llamada "peras" con el número 3 dentro, el operador "+" puede decirle a la computadora que sume el contenido de ambas cajas para obtener el total de frutas.

```javascript
// Operadores
const peras = 3;
const manzanas = 5;
let frutas = peras + manzanas; // Output: 7

// Operadores de Asignación
let x = 5;
let y = 10;
```

- **Operadores aritméticos**: Símbolos para realizar operaciones matemáticas (suma, resta, multiplicación, etc.).

```javascript
// Operadores Aritméticos
let suma = x + y; // Output: 15
let resta = x - y; // Output: -5
let multiplicacion = x * y; // Output: 50
let division = x / y; // Output: 0.5
let modulo = x % y; // Output: 5
```

- **Operadores de comparación**: Símbolos para comparar valores (igual, diferente, mayor, menor, etc.).

```javascript
// Operadores de Comparación
let esIgual = x === y; // Output: false
let noEsIgual = x !== y; // Output: true
let esMayorQue = x > y; // Output: false
let esMenorQue = x < y; // Output: true
let mayorOigual = x >= y; // Output: false
let menorOigual = x <= y; // Output: true
```

- **Operadores lógicos**: Símbolos que permiten combinar condiciones lógicas (and(y), or(o), not(no)).

```javascript
// Operadores Lógicos
let andLogico = x < 20 && y > 5; // Output: true
let orLogico = x > 3 || y < 15; // Output: true
let notLogico = !(x === y); // Output: true
```

- **Operador de concatenación**: El operador de concatenación en JavaScript se utiliza para unir o combinar cadenas de texto. Cuando usas el operador `+` con cadenas, en lugar de realizar una suma matemática, concatena o une las cadenas.

```javascript
// Operador de Concatenación
let saludo = "Hola";
let nombre = "Miguel";
let mensaje = saludo + " " + nombre; // Output: Hola Miguel
```

- **Operador de Incremento/Decremento**: el operador de incremento/decremento en JavaScript se utiliza para aumentar o disminuir el valor de una variable numérica en 1. Hay dos versiones de este operador:

1. Incremento (`++`): Aumenta el valor de la variable en 1.
2. Decremento (`--`): Disminuye el valor de la variable en 1.

```javascript
// Operador de Incremento/Decremento
let numero = 5;

// Incremento
numero++;
console.log(numero); // Mostrará: 6

// Decremento
numero--;
console.log(numero); // Mostrará: 5
```

- **Operador `+=` (Operador de Suma y Asignación):** Se utiliza para agregar el valor de la expresión a la variable y asignar el resultado a la misma variable.

```javascript
let numero = 10;

// Equivalente a: numero = numero + 5
numero += 5;

console.log(numero); // Mostrará: 15
```

- **Operador `-=` (Operador de Resta y Asignación):** Se utiliza para restar el valor de la expresión de la variable y asignar el resultado a la misma variable.

```javascript
let numero = 20;

// Equivalente a: numero = numero - 8
numero -= 8;

console.log(numero); // Mostrará: 12
```

Estos dos últimos operadores son útiles cuando deseas realizar operaciones de suma o resta en una variable y actualizar su valor de manera concisa.

### Comentarios

Los comentarios son notas en tu código que no se ejecutan y son útiles para explicar partes de tu código o hacer anotaciones. En algunos de los ejemplos ya mencionados se incluían comentarios.

Hay dos formas de escribir comentarios.

1. **Comentario de una línea:** Puedes usar dos barras inclinadas (`//`) para crear un comentario de una línea. Todo lo que escribas después de las dos barras será tratado como un comentario y no afectará el funcionamiento del programa.

```javascript
// Este es un comentario de una línea
```

2. **Comentario de varias líneas:** Puedes usar `/*` para iniciar un comentario de varias líneas y `*/` para finalizarlo. Todo lo que esté entre estos delimitadores será tratado como un comentario.

```javascript
/*
Este es un comentario
de varias líneas
*/
```

Los comentarios son muy útiles para explicar tu código a otras personas (o incluso a ti mismo en el futuro) y para hacer que el código sea más comprensible. Puedes usarlos para describir el propósito de una parte específica del código, dar instrucciones, o cualquier cosa que ayude a entender cómo funciona tu programa.

### Console Log

`console.log` es una herramienta para imprimir mensajes en la consola del navegador o en el entorno de ejecución de JavaScript. Es útil para depurar y entender lo que está sucediendo en tu código.

```javascript
let nombre = "Ana";
console.log("Hola, " + nombre); // Imprimirá 'Hola, Ana' en la consola
```

Puedes usar `console.log` para mostrar el valor de variables, mensajes informativos o cualquier cosa que quieras ver mientras desarrollas.

## Estructuras de Control en Javascript

Las estructuras de control en JavaScript son como las instrucciones que le das a tu programa para que tome decisiones y actúe de cierta manera. Son herramientas poderosas que te permiten controlar el flujo de ejecución de tu código. Vamos a explorar cómo estas estructuras te ayudan a tomar decisiones y personalizar la forma en que tu programa se comporta.

### if (Si)

El `if` es como una puerta que se abre solo si se cumple una condición específica. Si la condición es verdadera, se ejecuta un bloque de código. Si es falsa, ese bloque se ignora.

```javascript
let edad = 20;

if (edad >= 18) {
  console.log("Eres mayor de edad"); // Se ejecutará si la edad es mayor o igual a 18
}
// Output: Eres mayor de edad
```

### else(Sino)

A veces, quieres que algo suceda si la condición del `if` no es verdadera. Aquí es donde entra el `else`. Es como una instrucción de respaldo que se activa si el `if` no lo hace.

```javascript
let edad = 15;

if (edad >= 18) {
  console.log("Eres mayor de edad");
} else {
  console.log("Eres menor de edad"); // Se ejecutará si la edad no es mayor o igual a 18
}
// Output: Eres menor de edad
```

### else if (Sino Si)

A veces, hay más de dos opciones y necesitas evaluar varias condiciones. `else if` te permite agregar más condiciones al proceso de toma de decisiones.

Supongamos que estás construyendo un programa para calificar películas basado en su puntuación. Queremos imprimir mensajes personalizados dependiendo de la puntuación obtenida. Aquí es donde `else if` se vuelve útil:

```javascript
let puntuacion = 85;

if (puntuacion >= 90) {
  console.log("¡Excelente! Esta película es realmente increíble.");
} else if (puntuacion >= 80) {
  console.log("¡Buena elección! Esta película es bastante buena.");
} else if (puntuacion >= 70) {
  console.log("Parece que disfrutarás esta película. No está mal.");
} else {
  console.log(
    "Tal vez deberías considerar otra opción. Esta película no tiene una puntuación muy alta."
  );
}
// Output: ¡Buena elección! Esta película es bastante buena.
```

### switch

`switch` es otra estructura de control en JavaScript que te permite evaluar una expresión contra múltiples casos posibles. Es especialmente útil cuando tienes muchas condiciones que podrían cumplirse y quieres ejecutar diferentes bloques de código en función de cuál sea la coincidencia.

```javascript
let diaDeLaSemana = "Lunes";

switch (diaDeLaSemana) {
  case "Lunes":
    console.log("Es el primer día de la semana.");
    break;

  case "Miércoles":
    console.log("Estamos a mitad de semana.");
    break;

  case "Domingo":
    console.log("Es el último día de la semana");
    break;

  default:
    console.log("Es un día común.");
}
// Output: Es el primer día de la semana.
```

## Bucles en Javascript

Los bucles son herramientas que te permiten repetir una tarea varias veces. Hay dos tipos principales de bucles en JavaScript: `for` y `while`.

### for

El bucle `for` es útil cuando sabes cuántas veces deseas repetir una tarea.

```javascript
// Contando hasta 10
for (let i = 1; i <= 10; i++) {
  console.log("Número:", i);
}
/* Output: 
Número: 1
Número: 2
[ continuación hasta número 10 ]
Número: 10
*/
```

**Explicación:**

1. **`for`**: `for` es una palabra clave en JavaScript que se utiliza para crear un bucle. Un bucle es como una instrucción que le dice al programa que repita ciertas acciones varias veces.
2. **`let i = 1`**: Aquí estamos declarando una variable llamada `i` e inicializándola con el valor 1. Esta variable se usará para contar el número de repeticiones del bucle.
3. **`i <= 10`**: Esta es la condición que determina cuándo debe continuar el bucle. Mientras `i` sea menor o igual a 10, el bucle seguirá ejecutándose.
4. **`i++`**: Después de cada ejecución del bucle, incrementamos el valor de `i` en 1. Esto asegura que en cada repetición, `i` se incremente.
5. **`console.log('Número:', i);`**: Dentro del bucle, imprimimos en la consola el valor actual de `i` junto con el texto 'Número:'.

### while

El bucle `while` es útil cuando no sabes cuántas veces se repetirá una tarea, pero tienes una condición que determina cuándo detenerse.

```javascript
let aplausos = 0;

while (aplausos < 10) {
  console.log("👏 ¡Aplauso!");
  aplausos++;
}
// Output: 👏 ¡Aplauso! [este mensaje se imprime 10 veces]
```

Este bucle `while` imprime un aplauso en la consola y cuenta cuántos aplausos llevamos. El bucle continuará hasta que hayamos dado 10 aplausos.

**Explicación**

1. **`let aplausos = 0;`**: Aquí estamos declarando una variable llamada `aplausos` e inicializándola con el valor 0. Esta variable se usará para contar cuántas veces queremos imprimir el mensaje de aplauso.
2. **`while (aplausos < 10)`**: `while` es otra palabra clave en JavaScript que se utiliza para crear un bucle. Este bucle continuará ejecutándose siempre que la condición `aplausos < 10` sea verdadera.
3. **`console.log('👏 ¡Aplauso!');`**: Dentro del bucle, imprimimos en la consola el mensaje de aplauso, que consiste en el emoji de aplauso y el texto "¡Aplauso!".
4. **`aplausos++;`**: Después de imprimir el mensaje de aplauso, incrementamos el valor de la variable `aplausos` en 1. Esto se hace con el operador `++`, que significa "aumentar en 1". Esto es importante para evitar que el bucle se ejecute indefinidamente.

## Array (Estructuras de Datos) en Javascript

Un array en JavaScript es una estructura de datos que te permite almacenar varios elementos en una sola variable. Puedes imaginarlo como una lista ordenada donde cada elemento tiene una posición única, y puedes acceder a ellos mediante un índice.

```javascript
let frutas = ["Manzana", "Plátano", "Fresa"];
```

### Operaciones Comunes con Arrays en JavaScript

#### Acceder a elementos

Puedes acceder a elementos individuales de un array utilizando su índice (posición).

```javascript
let frutas = ["Manzana", "Plátano", "Uva"];
console.log(frutas[1]); // Output: Plátano
// Acceder al segundo elemento (índice 1)
```

#### Modificar elementos

Puedes modificar un elemento específico en el array asignándole un nuevo valor mediante su índice.

```javascript
let colores = ["Rojo", "Verde", "Azul"];
colores[1] = "Amarillo";
console.log(colores); // Output: ['Rojo', 'Amarillo', 'Azul']
```

#### Añadir elementos al final

El método `push()` se utiliza para agregar elementos al final del array.

```javascript
let numeros = [1, 2, 3];
numeros.push(4);
console.log(numeros); // Output: [1, 2, 3, 4]
```

#### Eliminar el último elemento

El método `pop()` elimina el último elemento del array.

```javascript
let ciudades = ["Nueva York", "París", "Tokio"];
ciudades.pop();
console.log(ciudades); // Output: ['Nueva York', 'París']
```

#### Añadir elementos al principio

El método `unshift()` añade elementos al principio del array.

```javascript
let letras = ["B", "C"];
letras.unshift("A");
console.log(letras); // Output: ['A', 'B', 'C']
```

#### Eliminar el primer elemento

El método `shift()` elimina el primer elemento del array.

```javascript
let dias = ["Lunes", "Martes", "Miércoles"];
dias.shift();
console.log(dias); // Output: ['Martes', 'Miércoles']
```

#### Encontrar la posición de un elemento

El método `indexOf()` devuelve la posición de la primera ocurrencia de un elemento.

```javascript
let alimentos = ["Manzana", "Plátano", "Uva"];
let posicion = alimentos.indexOf("Plátano");
console.log(posicion); // Output: 1
```

#### Eliminar elementos en una posición específica

El método `splice()` permite eliminar elementos desde una posición específica.

```javascript
let numeros = [1, 2, 3, 4, 5];
numeros.splice(2, 2); // Elimina 2 elementos a partir de la posición 2
console.log(numeros); // Output: [1, 2, 5]
```

En Javascript hay más operaciones para manipulación de arrays, para más información recomiendo consultar la página de MDN.

## POO (Programación Orientada a Objetos) en Javascript

La Programación Orientada a Objetos (POO) es como organizar y trabajar con cosas del mundo real en el mundo virtual de la programación. En lugar de escribir líneas de código sueltas, puedes imaginar que estás creando pequeños "mundos" con reglas específicas.

Piensa en un coche. Un coche tiene ciertas características como color, modelo, y puede realizar acciones como arrancar, detenerse y girar a la izquierda o derecha. En POO, este coche sería un "objeto".

Ahora, antes de tener el coche real, alguien podría haber diseñado un "plano" para construir ese tipo de coche en particular. Este "plano" es como una "clase" en POO. La clase define cómo se verán y comportarán todos los coche que se creen basándose en ese plano.

**Clase y Objeto en JavaScript**
En JavaScript, podemos crear clases y objetos. Una clase es como un plano, y un objeto es una instancia real basada en ese plano.

Ejemplo con JavaScript:
Vamos a crear una clase `Coche` y un objeto `miCoche` basado en esa clase.

```javascript
// Definimos la clase
class Coche {
  constructor(color, modelo) {
    this.color = color;
    this.modelo = modelo;
  }

  arrancar() {
    console.log("El coche ha arrancado.");
  }

  girar(izquierda) {
    if (izquierda) {
      console.log("Girando a la izquierda.");
    } else {
      console.log("Girando a la derecha.");
    }
  }
}

// Creamos un objeto basado en la clase Coche
const miCoche = new Coche("Rojo", "Sedán");

// Usamos métodos y propiedades del objeto
console.log(
  `Mi coche es de color ${miCoche.color} y modelo ${miCoche.modelo}.`
);
miCoche.arrancar();
miCoche.girar(true);
```

La POO nos permite pensar en nuestros programas de una manera más organizada y parecida al mundo real. Creamos "clases" que son como planos, y luego creamos "objetos" basados en esos planos. Cada objeto tiene características (propiedades) y acciones (métodos) que lo hacen único. La POO nos ayuda a estructurar nuestro código de manera más comprensible y fácil de mantener.

## Funciones (Modularidad) en JavaScript

En el mundo de la programación, las funciones son como pequeñas tareas específicas que puedes realizar cuando las necesitas. Imagina que estás cocinando una receta complicada. En lugar de hacer todo de una vez, divides las tareas: picar verduras, cocinar arroz, freír carne, etc. Cada una de estas tareas es como una función en programación.

En JavaScript, una función es un conjunto de instrucciones que realiza una tarea específica. Puedes pensar en una función como una mini receta que puedes usar cuando quieras realizar una acción particular.

Vamos a crear una función simple que sume dos números.

```javascript
// Definimos la función llamada sumar
function sumar(numero1, numero2) {
  // Dentro de la función, realizamos la operación de suma
  let resultado = numero1 + numero2;
  // Devolvemos el resultado
  return resultado;
}

// Utilizamos la función sumar
let resultadoSuma = sumar(5, 3);
console.log(resultadoSuma); // Mostrará 8 en la consola
```

**¿Por qué usar Funciones?**

- **Reutilización:** Puedes usar la misma función varias veces en diferentes partes de tu código.
- **Organización:** Ayudan a organizar tu código al dividir tareas en unidades más pequeñas y manejables.
- **Mantenimiento:** Si necesitas cambiar algo, solo lo haces en un lugar (dentro de la función) en lugar de buscar y cambiar cada instancia de la tarea en todo tu código.

## Funciones de flecha (Arrow Functions)

Las Arrow Functions son una forma más concisa de escribir funciones en JavaScript. Son útiles cuando deseas crear funciones simples y de una sola expresión. Vamos a comparar una función tradicional con una Arrow Function.

```javascript
// Función Tradicional
function sumar(a, b) {
  return a + b;
}

// Función de flecha
const sumar = (a, b) => a + b;
```

**Características de las Arrow Functions:**
Sintaxis Concisa

- No necesitas la palabra clave `function`.
- Si la función tiene solo una expresión, puedes omitir las llaves `{}` y la palabra clave `return`.
  `this` en Arrow Functions
- En funciones tradicionales, el valor de `this` puede cambiar dependiendo del contexto. En las Arrow Functions, `this` mantiene el valor del ámbito donde se creó la función.

**Cuándo Usar Arrow Functions:**

- Útiles para funciones cortas y simples.
- Especialmente útiles cuando se trabaja con funciones de devolución de llamada (`callback`) o métodos de array.

## Sintaxis básica de React

Ahora que ya tenemos unas bases de Javascript, vamos con la sintaxis de React.

### Componentes

En React, construimos interfaces mediante la creación de "componentes". Un componente es como un bloque de construcción que puede contener HTML, CSS y JavaScript.

Un componente puede ser tan pequeño como un botón, o tan grande como toda una página.

#### Crear y anidar componentes

Los componentes de React son funciones de JavaScript que devuelven _markup_ (marcado). Cuando hablamos de componentes de React que "devuelven marcado", nos referimos a que estas funciones tienen la capacidad de generar y devolver código HTML o JSX.

JavaScript XML, o JSX, es una sintaxis que combina JavaScript con HTML para facilitar la creación de interfaces de usuario. La mayoría de los proyectos de React usan JSX por la comodidad que ofrece.

Ejemplo de un componente en React llamado MyButton:

```javascript
function MyButton() {
  return <button>Soy un botón</button>;
}
```

Ahora que has declarado `MyButton`, puedes anidarlo en otro componente:

```javascript
export default function MyApp() {
  return (
    <div>
      <h1>Bienvenido a mi aplicación</h1>
      <MyButton />
    </div>
  );
}
```

Nota que `<MyButton />` empieza con mayúscula. Así es como sabes que es un componente de React. Los nombres de los componentes de React siempre deben comenzar con mayúscula, mientras las etiquetas HTML deben estar minúsculas.

Las palabras clave `export default` especifican el componente principal en el archivo.

JSX es más estricto que HTML. Tienes que cerrar etiquetas como `<br />`. Tu componente tampoco puede devolver múltiples etiquetas de JSX. Debes envolverlas en un padre compartido, como `<div>...</div>` o en un envoltorio vacío `<>...</>`:

```javascript
function AboutPage() {
  return (
    <>
      <h1>Acerca de</h1>
      <p>
        Hola.
        <br />
        ¿Cómo vas?
      </p>
    </>
  );
}
```

### Añadir estilos

En React, especificas una clase de CSS con `className`. Funciona de la misma forma que el atributo class de HTML:

```jsx
<img className="avatar" />
```

Luego escribes las reglas CSS para esa clase en un archivo CSS aparte:

```css
.avatar {
  border-radius: 50%;
}
```

### Mostrar datos

JSX te permite poner marcado dentro de JavaScript. Las llaves te permiten «escapar de nuevo» hacia JavaScript de forma tal que puedas incrustar una variable de tu código y mostrársela al usuario. Por ejemplo, esto mostrará `user.name`:

```jsx
return <h1>{user.name}</h1>;
```

También puedes «escaparte hacia JavaScript» en los atributos JSX, pero tienes que utilizar llaves _en lugar de_ comillas. Por ejemplo, `className="avatar"` pasa la cadena `"avatar"` como la clase CSS, pero `src={user.imageUrl}` lee el valor de la variable de JavaScript `user.imageUrl` y luego pasa el valor como el atributo `src`:

```jsx
return <img className="avatar" src={user.imageUrl} />;
```

Puedes también poner expresiones más complejas dentro de llaves, por ejemplo, concatenación de cadenas:

```jsx
const user = {
  name: "Hedy Lamarr",
  imageUrl: "https://i.imgur.com/yXOvdOSs.jpg",
  imageSize: 90,
};

export default function Profile() {
  return (
    <>
      <h1>{user.name}</h1>
      <img
        className="avatar"
        src={user.imageUrl}
        alt={"Foto de " + user.name}
        style={{
          width: user.imageSize,
          height: user.imageSize,
        }}
      />
    </>
  );
}
```

En el ejemplo de arriba, `style={{}}` no es una sintaxis especial, sino un objeto regular `{}` dentro de las llaves de JSX de `style={ }`. Puedes utilizar el atributo `style` cuando tus estilos dependen de variables de JavaScript.

### Renderizado condicional

En React, no hay una sintaxis especial para escribir condicionales. En cambio, usarás las mismas técnicas que usas al escribir código regular de JavaScript. Por ejemplo, puedes usar una sentencia `if` para incluir JSX condicionalmente:

```jsx
let content;

if (isLoggedIn) {
  content = <AdminPanel />;
} else {
  content = <LoginForm />;
}

return <div>{content}</div>;
```

Si prefieres un código más compacto, puedes utilizar el operador `?` condicional. A diferencia de `if`, funciona dentro de JSX:

```jsx
<div>{isLoggedIn ? <AdminPanel /> : <LoginForm />}</div>
```

Cuando no necesites la rama `else`, puedes también usar la sintaxis lógica `&&`, más breve:

```jsx
<div>{isLoggedIn && <AdminPanel />}</div>
```

Todos estos enfoques también funcionan para especificar atributos condicionalmente. Si no estás familiarizado con toda esta sintaxis de JavaScript, puedes comenzar por usar siempre `if...else`.

### Renderizado de listas

Dependerás de funcionalidades de JavaScript como los bucles for y la función map() de los arreglos para renderizar listas de componentes.

Por ejemplo, digamos que tienes un arreglo de productos:

```jsx
const products = [
  { title: "Col", id: 1 },
  { title: "Ajo", id: 2 },
  { title: "Manzana", id: 3 },
];
```

Dentro de tu componente, utiliza la función `map()` para transformar el arreglo de productos en un arreglo de elementos `<li>`:

```jsx
const listItems = products.map((product) => (
  <li key={product.id}>{product.title}</li>
));

return <ul>{listItems}</ul>;
```

Nota que `<li>` tiene un atributo `key` (llave). Para cada elemento en una lista, debes pasar una cadena o un número que identifique ese elemento de forma única entre sus hermanos. Usualmente, una llave debe provenir de tus datos, como un ID de una base de datos. React dependerá de tus llaves para entender qué ha ocurrido si luego insertas, eliminas o reordenas los elementos.

El componente completo sería:

```jsx
const products = [
  { title: "Col", isFruit: false, id: 1 },
  { title: "Ajo", isFruit: false, id: 2 },
  { title: "Manzana", isFruit: true, id: 3 },
];

export default function ShoppingList() {
  const listItems = products.map((product) => (
    <li
      key={product.id}
      style={{
        color: product.isFruit ? "magenta" : "darkgreen",
      }}
    >
      {product.title}
    </li>
  ));

  return <ul>{listItems}</ul>;
}
```

La visualización sería una lista de col y ajo en verde oscuro, mientras que manzana se renderizaría en magenta.

### Responder a eventos

Puedes responder a eventos declarando funciones _controladoras de eventos_ dentro de tus componentes:

```jsx
function MyButton() {
  function handleClick() {
    alert("¡Me hiciste clic!");
  }

  return <button onClick={handleClick}>Hazme clic</button>;
}
```

¡Nota que `onClick={handleClick}` no tiene paréntesis al final! No _llames_ a la función controladora de evento: solamente necesitas _pasarla hacia abajo_. React llamará a tu controlador de evento cuando el usuario haga clic en el botón.

### Actualizar la pantalla

A menudo, querrás que tu componente «recuerde» alguna información y la muestre. Por ejemplo, quizá quieras contar el número de veces que hiciste clic en un botón. Para lograrlo, añade _estado_ a tu componente.

Primero, importa `useState` de React:

```jsx
import { useState } from "react";
```

Ahora puedes declarar una _variable de estado_ dentro de tu componente:

```jsx
function MyButton() {

const [count, setCount] = useState(0);
```

Obtendrás dos cosas de `useState`: el estado actual (`count`), y la función que te permite actualizarlo (`setCount`). Puedes nombrarlos de cualquier forma, pero la convención es llamarlos algo como `[something, setSomething]`.

La primera vez que se muestra el botón, `count` será `0` porque pasaste `0` a `useState()`. Cuando quieras cambiar el estado llama a `setCount()` y pásale el nuevo valor. Al hacer clic en este botón se incrementará el contador:

```jsx
function MyButton() {
  const [count, setCount] = useState(0);

  function handleClick() {
    setCount(count + 1);
  }

  return <button onClick={handleClick}>Hiciste clic {count} veces</button>;
}
```

React llamará de nuevo a la función del componente. Esta vez, `count` será `1`. Luego será `2`. Y así sucesivamente.

Si renderizas el mismo componente varias veces, cada uno obtendrá su propio estado.

## El uso de los Hooks

Un Hook es una función especial en React que te permite agregar características de React a tus componentes funcionales.

`useState` es un Hook que te permite añadir estado a tus componentes funcionales. El estado es como una memoria donde puedes guardar datos que pueden cambiar con el tiempo.

Puedes usar Hooks solo en componentes funcionales y en el nivel más alto de esos componentes. No puedes usarlos dentro de bucles o condicionales directamente.

Ejemplo simple de cómo usar `useState` para manejar un contador en un componente funcional.

```jsx
import React, { useState } from "react";

const Contador = () => {
  // Usamos useState para inicializar el estado del contador en 0
  const [contador, setContador] = useState(0);

  // La función setContador nos permite actualizar el valor del contador

  return (
    <div>
      <p>Contador: {contador}</p>
      <button onClick={() => setContador(contador + 1)}>Incrementar</button>
    </div>
  );
};

export default Contador;
```

**Regla sobre dónde usar Hooks**
Solo puedes usar Hooks al principio de tus componentes funcionales o en otros Hooks. Si necesitas usar un Hook dentro de una condición o bucle, coloca ese código en un nuevo componente funcional.

Esta regla se debe a cómo React realiza su seguimiento interno de los componentes y su estado. Siguiendo estas reglas, React puede hacer un mejor seguimiento de lo que está sucediendo en tu aplicación.

### Compartir datos entre componentes

Compartir datos entre componentes es una parte esencial de trabajar con React. Para ello, debemos de seguir una serie de pasos:

#### 1. Crear un Componente Padre

Imagina que tienes dos componentes, `ComponenteA` y `ComponenteB`, y quieres compartir datos entre ellos. Para hacer esto, crea un componente "padre" que contenga ambos componentes.

```jsx
// App.js (componente padre)
import React, { useState } from "react";
import ComponenteA from "./ComponenteA";
import ComponenteB from "./ComponenteB";

const App = () => {
  // Define el estado que quieres compartir entre componentes
  const [datosCompartidos, setDatosCompartidos] = useState("");

  return (
    <div>
      <ComponenteA setDatosCompartidos={setDatosCompartidos} />
      <ComponenteB datosCompartidos={datosCompartidos} />
    </div>
  );
};

export default App;
```

#### 2. Crear ComponenteA

En `ComponenteA`, crea un formulario o cualquier elemento que permita al usuario ingresar datos. Cuando se ingresan datos, utiliza la función `setDatosCompartidos` para actualizar el estado en el componente padre.

```jsx
// ComponenteA.js
import React, { useState } from "react";

const ComponenteA = ({ setDatosCompartidos }) => {
  const [inputValue, setInputValue] = useState("");

  const manejarCambio = (e) => {
    setInputValue(e.target.value);
  };

  const manejarEnvio = () => {
    // Actualiza el estado en el componente padre
    setDatosCompartidos(inputValue);
  };

  return (
    <div>
      <input type="text" value={inputValue} onChange={manejarCambio} />
      <button onClick={manejarEnvio}>Enviar Datos</button>
    </div>
  );
};

export default ComponenteA;
```

#### 3. Crear ComponenteB

En `ComponenteB`, recibe los datos compartidos como una prop y úsalos según sea necesario.

```jsx
// ComponenteB.js
import React from "react";

const ComponenteB = ({ datosCompartidos }) => {
  return (
    <div>
      <p>Datos Compartidos: {datosCompartidos}</p>
    </div>
  );
};

export default ComponenteB;
```

Ahora, cuando el usuario ingresa datos en `ComponenteA` y hace clic en "Enviar Datos", esos datos se actualizan en el estado del componente padre (`App`). Luego, esos datos se pasan como una prop a `ComponenteB`, donde puedes mostrarlos o utilizarlos según tus necesidades.

## Creación de la BBDD

En el desarrollo de aplicaciones, una **base de datos** es como un almacén estructurado donde podemos almacenar y recuperar datos de manera eficiente. Nos permite organizar la información de manera que sea fácil de entender y administrar.

SQL es un lenguaje estándar utilizado para comunicarse con bases de datos relacionales. Una base de datos relacional organiza los datos en tablas con columnas y filas, y SQL proporciona una forma estructurada de realizar operaciones sobre estos datos.

**Diferentes funciones de SQL**

1. **Gestión de Datos:** SQL se utiliza para crear, modificar y eliminar bases de datos y tablas.
2. **Consulta de Datos:** Permite realizar consultas para recuperar información específica de una base de datos.
3. **Actualización de Datos:** Se utiliza para actualizar registros existentes en la base de datos.
4. **Inserción de Datos:** Permite agregar nuevos registros a la base de datos.
5. **Eliminación de Datos:** Se utiliza para eliminar registros o tablas completas.

Utilizaremos SQL para crear la base de datos y las tablas necesarias que utilizaremos para gestión de datos en el siguiente apartado.

```sql
-- Crear la base de datos
CREATE DATABASE IF NOT EXISTS mi_base_de_datos;

-- Usar la base de datos
USE mi_base_de_datos;

-- Crear la tabla de usuarios
CREATE TABLE IF NOT EXISTS usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(50),
    edad INT
);
```

Explicación:

- `CREATE DATABASE`: Crea una nueva base de datos si no existe.
- `USE`: Indica que queremos trabajar con la base de datos especificada.
- `CREATE TABLE`: Crea una tabla en la base de datos con columnas específicas, como `id`, `nombre`, y `edad`. La columna `id` es una clave primaria que se autoincrementa.

**Clave Primaria**
En una base de datos, una clave primaria es un campo (o conjunto de campos) que identifica de manera única cada registro en una tabla. No puede haber dos registros con el mismo valor en la columna de la clave primaria. Es esencialmente la "identificación única" de cada fila.

**Autoincremento**
Cuando se dice que la columna `id` se autoincrementa, significa que la base de datos asignará automáticamente un valor único a esta columna cada vez que se inserta un nuevo registro. No necesitas preocuparte por asignar manualmente valores a la columna `id`; la base de datos se encargará de incrementar automáticamente el valor para cada nuevo registro.

En el ejemplo de creación de la base de datos:
`id INT AUTO_INCREMENT PRIMARY KEY`

Aquí, estamos diciendo que la columna `id` es un número entero (`INT`) que se autoincrementa automáticamente cada vez que se inserta un nuevo registro. Además, esta columna se define como la clave primaria (`PRIMARY KEY`), asegurando que cada valor en la columna `id` sea único en la tabla.

## CRUD con MYSQL

El término CRUD se utiliza comúnmente en el ámbito de las bases de datos y la gestión de datos para describir las operaciones fundamentales que se pueden realizar sobre los datos almacenados.

CRUD se refiere a las operaciones básicas de Crear (Create), Leer (Read), Actualizar (Update) y Eliminar (Delete) datos en una base de datos.

Realizar operaciones CRUD con MySQL en React implica una arquitectura de servidor y un backend que se comunique con la base de datos. Aquí, proporcionaré una explicación básica y sencilla utilizando un backend simple con Node.js y Express para interactuar con MySQL. Asegúrate de tener Node.js y MySQL instalados antes de comenzar.

### Paso 1: Configurar el Backend

**1. Instalar dependencias:**

- Crea una nueva carpeta para tu proyecto.
- Ejecuta `npm init -y` para inicializar el archivo `package.json`.
- Instala las dependencias necesarias:

```shell
npm install express mysql body-parser
```

**2. Crear un archivo `server.js`:**

- Este será tu archivo principal del backend.

```javascript
const express = require("express");
const mysql = require("mysql");
const bodyParser = require("body-parser");

const app = express();
const port = 3001;

app.use(bodyParser.json());

// Configuración de la conexión a la base de datos MySQL
const db = mysql.createConnection({
  host: "localhost",
  user: "tu_usuario",
  password: "tu_contraseña",
  database: "nombre_de_tu_bd",
});

db.connect((err) => {
  if (err) {
    console.error("Error de conexión a MySQL:", err);
  } else {
    console.log("Conexión a MySQL exitosa");
  }
});

// Rutas CRUD del siguiente paso

app.listen(port, () => {
  console.log(`Servidor backend en ejecución en http://localhost:${port}`);
});
```

### Paso 2: Configurar las Rutas CRUD

#### Crear (Create)

En el contexto de bases de datos, la operación de "Crear" se refiere a la acción de agregar nuevos registros o datos a una tabla. Es como añadir una nueva entrada a una lista. En la mayoría de los sistemas de gestión de bases de datos relacionales, esto se realiza mediante la instrucción SQL `INSERT`.

```javascript
// Crear un nuevo elemento
app.post("/items", (req, res) => {
  const newItem = req.body;
  db.query("INSERT INTO tus_tabla SET ?", newItem, (err, result) => {
    if (err) {
      res.status(500).send("Error al crear un nuevo elemento");
    } else {
      res.status(201).send("Elemento creado exitosamente");
    }
  });
});
```

#### Leer (Read)

La operación de "Leer" se refiere a la acción de recuperar información almacenada en la base de datos. Es como obtener información de una lista. En la mayoría de los sistemas de gestión de bases de datos relacionales, esto se realiza mediante la instrucción SQL SELECT .

```javascript
// Obtener todos los elementos
app.get("/items", (req, res) => {
  db.query("SELECT * FROM tus_tabla", (err, result) => {
    if (err) {
      res.status(500).send("Error al obtener elementos");
    } else {
      res.json(result);
    }
  });
});
```

#### Actualizar (Update)

La operación de "Actualizar" se refiere a la acción de modificar los datos existentes en la base de datos. Es como cambiar la información de un elemento en una lista. En la mayoría de los sistemas de gestión de bases de datos relacionales, esto se realiza mediante la instrucción SQL UPDATE .

```javascript
// Actualizar un elemento
app.put("/items/:id", (req, res) => {
  const itemId = req.params.id;
  const updatedItem = req.body;
  db.query(
    "UPDATE tus_tabla SET ? WHERE id = ?",
    [updatedItem, itemId],
    (err, result) => {
      if (err) {
        res.status(500).send("Error al actualizar el elemento");
      } else {
        res.send("Elemento actualizado exitosamente");
      }
    }
  );
});
```

#### Eliminar (Delete)

La operación de "Eliminar" se refiere a la acción de eliminar datos existentes de la base de datos. Es como quitar un elemento de una lista. En la mayoría de los sistemas de gestión de bases de datos relacionales, esto se realiza mediante la instrucción SQL DELETE .

```javascript
// Eliminar un elemento
app.delete("/items/:id", (req, res) => {
  const itemId = req.params.id;
  db.query("DELETE FROM tus_tabla WHERE id = ?", itemId, (err, result) => {
    if (err) {
      res.status(500).send("Error al eliminar el elemento");
    } else {
      res.send("Elemento eliminado exitosamente");
    }
  });
});
```

### Paso 3: Configurar el Frontend con React

**1.Instalar Axios:**

- Axios es una biblioteca para hacer solicitudes HTTP desde el navegador.

```shell
npm install axios
```

**2. Crear un componente React para la interfaz de usuario:**

- Utiliza componentes de React para mostrar y manipular los datos.

```javascript
import React, { useState, useEffect } from "react";
import axios from "axios";

const CRUDApp = () => {
  const [items, setItems] = useState([]);
  const [newItem, setNewItem] = useState("");

  useEffect(() => {
    // Obtener datos al cargar la página
    axios
      .get("http://localhost:3001/items")
      .then((response) => setItems(response.data))
      .catch((error) => console.error("Error al obtener datos:", error));
  }, []);

  const handleCreate = () => {
    // Crear un nuevo elemento
    axios
      .post("http://localhost:3001/items", { name: newItem })
      .then(() => {
        // Actualizar la lista después de crear
        axios
          .get("http://localhost:3001/items")
          .then((response) => setItems(response.data))
          .catch((error) => console.error("Error al obtener datos:", error));
      })
      .catch((error) =>
        console.error("Error al crear un nuevo elemento:", error)
      );
  };

  return (
    <div>
      <h1>CRUD App</h1>
      <ul>
        {items.map((item) => (
          <li key={item.id}>
            {item.name}
            <button onClick={() => handleUpdate(item.id)}>Actualizar</button>
            <button onClick={() => handleDelete(item.id)}>Eliminar</button>
          </li>
        ))}
      </ul>
      <input
        type="text"
        value={newItem}
        onChange={(e) => setNewItem(e.target.value)}
      />
      <button onClick={handleCreate}>Crear</button>
    </div>
  );
};

export default CRUDApp;
```

**3. Integrar el componente React en tu aplicación:**

- Utiliza este componente React en tu aplicación principal.

```javascript
import React from "react";
import CRUDApp from "./CRUDApp";

const App = () => {
  return (
    <div>
      <CRUDApp />
    </div>
  );
};

export default App;
```

**4. Ejecutar la aplicación:**

- Inicia tu servidor backend ejecutando `node server.js` en la terminal.
- Inicia tu aplicación React ejecutando `npm start` en otra terminal.

Ahora tendrás una aplicación CRUD básica con React y MySQL. Ten en cuenta que este ejemplo es bastante simplificado y en un entorno de producción, deberías implementar medidas de seguridad adicionales y gestionar los errores de manera más robusta. Además que desde la documentación oficial de React se recomienda el uso de un framework como mecionamos al principio del manual.

## Caso práctico
Vamos a crear un caso práctico simple de una aplicación React para un manual de principiantes. En este ejemplo, construiremos una aplicación de gestión de tareas con las secciones mencionadas en el manual. A medida que avanzamos en el caso práctico, cubriremos la instalación, la sintaxis básica, estructuras de control, bucles, arrays, funciones, programación orientada a objetos (POO), y la conexión a una base de datos MySQL para realizar operaciones CRUD.

### Instalación: Linux

#### 1. Instalación de Node.js y npm

Asegúrate de tener Node.js y npm instalados en tu sistema. Puedes instalarlos ejecutando los siguientes comandos en tu terminal:

```bash
sudo apt update
sudo apt install nodejs
sudo apt install npm
```

Utilizaremos el framework Next.js ya que en la documentación oficial de React recomiendan usar unos de los frameworks propuestos.

#### 2. Crear una aplicación Next.js

Luego, crea una nueva aplicación Next.js utilizando el siguiente comando:

```bash
npx create-next-app gestion-tareas-nextjs
cd gestion-tareas-nextjs
```

### Sintaxis básica

Abre el archivo `pages/index.js` y reemplaza su contenido con el siguiente código:

```js
// pages/index.js
import React from 'react';

function Home() {
  return (
    <div>
      <h1>Gestión de Tareas</h1>
      <p>Bienvenido a la aplicación de gestión de tareas.</p>
    </div>
  );
}

export default Home;
```

### Estructuras de control

Agrega una estructura de control simple al archivo `pages/index.js` para mostrar un mensaje condicional basado en una variable:

```js
// pages/index.js
import React from 'react';

function Home() {
  const isLoggedIn = true;

  return (
    <div>
      <h1>Gestión de Tareas</h1>
      <p>Bienvenido a la aplicación de gestión de tareas.</p>
      {isLoggedIn ? <p>Usuario autenticado</p> : <p>Iniciar sesión</p>}
    </div>
  );
}

export default Home;
```

Esto mostrará el texto según el usuario esté autenticado o no. Ahora mismo, siempre estará autenticado ya que definimos la variable como verdadera al iniciarla y no la cambiamos.

### Bucles

Agrega un bucle que muestra una lista de tareas al archivo `pages/index.js`:

```js
// pages/index.js
import React from 'react';

function Home() {
// Resto del código
  const tareas = ['Imprimir', 'Cortar', 'Pegar'];

  return (
    <div>
      <h1>Gestión de Tareas</h1>
      // Resto del código
      <ul>
        {tareas.map((tarea, index) => (
          <li key={index}>{tarea}</li>
        ))}
      </ul>
    </div>
  );
}

export default Home;
```

Este código mostrará la lista de tareas en el arreglo tareas. Ul viene de "unordered list" en inglés o lista no ordenada.

### Array (estructuras de datos)
Supongamos que tienes un array de objetos, cada uno representando un producto con un nombre y un precio. Queremos mostrar estos productos en una lista en un componente React.
```js
import React from 'react';

// Array de productos
const productos = [
  { id: 1, nombre: 'Camiseta', precio: 20 },
  { id: 2, nombre: 'Pantalón', precio: 30 },
  { id: 3, nombre: 'Zapatos', precio: 50 },
  { id: 4, nombre: 'Sombrero', precio: 15 },
];

// Componente que muestra la lista de productos
const ListaProductos = () => {
  return (
    <div>
      <h1>Lista de Productos</h1>
      <ul>
        {productos.map((producto) => (
          // La propiedad "key" es importante para React y ayuda a identificar de manera única cada elemento en la lista
          <li key={producto.id}>
            <strong>{producto.nombre}</strong> - ${producto.precio}
          </li>
        ))}
      </ul>
    </div>
  );
};

// Componente principal que utiliza ListaProductos
const App = () => {
  return (
    <div>
      <ListaProductos />
    </div>
  );
};

export default App;

```

En este ejemplo:

1. Definimos un array llamado `productos` que contiene objetos con información sobre productos.
2. Creamos un componente llamado `ListaProductos` que utiliza el método `map` para recorrer el array de productos y renderizar cada elemento como un elemento de lista (`<li>`).
3. El componente principal `App` simplemente incluye el componente `ListaProductos`.

### Funciones (modularidad)
Refactoriza el código para mover la lógica de agregar tareas a una función separada en el archivo `pages/index.js`:

```js
// pages/index.js
import React, { useState } from 'react';

function Home() {
  // Estado para la nueva tarea y lista de tareas existentes
  const [newTask, setNewTask] = useState('');
  const [tasks, setTasks] = useState(['Tarea 1', 'Tarea 2', 'Tarea 3']);

  // Función para agregar una nueva tarea
  const addTask = () => {
    // Utilizamos el spread operator (...) para crear un nuevo array con todas las tareas existentes y la nueva tarea
    setTasks([...tasks, newTask]);
    // Limpiamos el campo de la nueva tarea después de agregarla
    setNewTask('');
  };

  return (
    <div>
      <h1>Gestión de Tareas</h1>
      {/* Mostramos la lista de tareas como elementos de una lista no ordenada */}
      <ul>
        {/* Utilizamos el método map para iterar sobre cada tarea y mostrarla como un elemento de lista */}
        {tasks.map((task, index) => (
          // La propiedad key es importante para React y ayuda a identificar de manera única cada elemento en la lista
          <li key={index}>{task}</li>
        ))}
      </ul>
      {/* Formulario para agregar una nueva tarea */}
      <input type="text" value={newTask} onChange={(e) => setNewTask(e.target.value)} />
      <button onClick={addTask}>Agregar Tarea</button>
    </div>
  );
}

export default Home;

```

Ahora, desglosemos el código:

1. **useState:** Se utiliza el hook `useState` para gestionar el estado de dos variables: `newTask` (que almacena la descripción de la nueva tarea) y `tasks` (que almacena la lista de tareas existentes).

2. **addTask:** Esta es una función que se llama cuando el botón "Agregar Tarea" se hace clic. Agrega la nueva tarea al array de tareas utilizando el spread operator (`[...tasks, newTask]`), creando así un nuevo array que incluye todas las tareas existentes más la nueva tarea. Después de agregar la tarea, limpia el campo `newTask` para prepararse para la próxima entrada.

3. **Renderizado de Tareas:** Utilizamos el método `map` para iterar sobre el array de tareas y renderizar cada tarea como un elemento de la lista (`<li>`).

4. **Formulario:** Se incluye un formulario simple con un campo de entrada de texto (`<input>`) para la nueva tarea y un botón para agregar la tarea.



### POO

Implementa una clase `Tarea` en un archivo separado `src/Task.js`:
```js
// src/Task.js
class Task {
  constructor(description) {
    this.description = description;
  }
}

export default Task;
```

En `pages/index.js`, utiliza la clase `Task` para representar las tareas:
```js
// pages/index.js
import React, { useState } from 'react';
import Task from '../src/Task';

function Home() {
  const [newTask, setNewTask] = useState('');
  const [tasks, setTasks] = useState([new Task('Tarea 1'), new Task('Tarea 2'), new Task('Tarea 3')]);

  const addTask = () => {
    setTasks([...tasks, new Task(newTask)]);
    setNewTask('');
  };

  return (
    <div>
      <h1>Gestión de Tareas</h1>
      <ul>
        {tasks.map((task, index) => (
          <li key={index}>{task.description}</li>
        ))}
      </ul>
      <input type="text" value={newTask} onChange={(e) => setNewTask(e.target.value)} />
      <button onClick={addTask}>Agregar Tarea</button>
    </div>
  );
}

export default Home;

```

### CRUD con MySQL
Implementaremos funciones CRUD básicas en `pages/index.js` para simular operaciones con MySQL:

```js
// pages/index.js
import React, { useState, useEffect } from 'react';
import Task from '../src/Task';

function Home() {
  const [newTask, setNewTask] = useState('');
  const [tasks, setTasks] = useState([]);

  // Simulación de operaciones CRUD con MySQL
  useEffect(() => {
    fetchTasks();
  }, []);

  const fetchTasks = () => {
    // Simulamos la obtención de tareas desde MySQL
    setTasks([new Task('Tarea 1'), new Task('Tarea 2'), new Task('Tarea 3')]);
  };

  const addTask = () => {
    // Simulamos la inserción de tarea en MySQL
    setTasks([...tasks, new Task(newTask)]);
    setNewTask('');
  };

  const deleteTask = (index) => {
    // Simulamos la eliminación de tarea en MySQL
    const updatedTasks = [...tasks];
    updatedTasks.splice(index, 1);
```

Este caso práctico proporciona una introducción práctica y paso a paso para construir una aplicación React desde cero, cubriendo varios aspectos fundamentales.

## Recursos

### MDN

MDN Web Docs (Mozilla Developer Network) es una plataforma en línea proporcionada por Mozilla que ofrece una amplia documentación y recursos relacionados con tecnologías web. Está destinada a desarrolladores web y proporciona información detallada sobre HTML, CSS, JavaScript, APIs de navegador, estándares web y otras tecnologías relacionadas.

MDN es un lugar fantástico para consultar sintaxis y buenas prácticas de Javascript. Además es un lugar que se mantiene actualizado convirtiéndolo en un lugar muy interesante a modo de guía. MDN te ayudará en la programación con React para seguir buenas prácticas.

[Link de MDN](https://developer.mozilla.org/en-US/)

### Documentación de React

La documentación oficial de React es una fuente esencial para cualquier desarrollador de React. Proporciona información detallada sobre conceptos fundamentales, API, patrones de diseño y mejores prácticas. Explorar la documentación de React te ayudará a comprender profundamente cómo trabajar de manera efectiva con esta biblioteca.

[React Documentation](https://es.react.dev/)

### JavaScript.info

JavaScript.info es un recurso educativo completo que cubre JavaScript desde los conceptos básicos hasta temas más avanzados. Ofrece tutoriales claros, ejemplos prácticos y tareas para poner en práctica lo aprendido. Es un recurso valioso tanto para principiantes como para desarrolladores intermedios.

[JavaScript.info](https://javascript.info/)

### freeCodeCamp

freeCodeCamp es una plataforma interactiva que ofrece cursos gratuitos de desarrollo web, incluyendo JavaScript y React. Proporciona desafíos prácticos, proyectos reales y una comunidad activa. Completa proyectos de React en freeCodeCamp para aplicar tus conocimientos y construir un portafolio sólido.

[freeCodeCamp](https://www.freecodecamp.org/)

### W3Schools

W3Schools es un recurso en línea que proporciona tutoriales y referencias prácticas sobre una amplia variedad de tecnologías web, incluyendo JavaScript y React. Es conocido por su enfoque práctico y sus ejemplos de código. Utiliza W3Schools para aprender conceptos específicos de React y resolver dudas rápidas.

[W3Schools](https://www.w3schools.com/)

### Awesome React

Awesome React es un repositorio en GitHub que recopila recursos, bibliotecas y herramientas relacionadas con React. Explora este repositorio para descubrir bibliotecas útiles, patrones de diseño y recursos adicionales que complementarán tu aprendizaje de React.

[Awesome React](https://github.com/enaqx/awesome-react)

### Stack Overflow

Stack Overflow es una plataforma de preguntas y respuestas donde los desarrolladores comparten conocimientos y resuelven problemas. Utiliza Stack Overflow para buscar respuestas a preguntas específicas, aprender de la comunidad y resolver desafíos técnicos.

[Stack Overflow](https://stackoverflow.com/)

### CodeWars

CodeWars es una plataforma que ofrece desafíos de codificación para mejorar tus habilidades en JavaScript y otros lenguajes. Resuelve katas (pequeños desafíos) para enfrentarte a problemas de programación de manera creativa y mejorar tu capacidad de resolución de problemas.

[CodeWars](https://www.codewars.com/)

### Roadmap.sh

Roadmap.sh proporciona hojas de ruta de desarrollo para diferentes tecnologías, incluyendo React y JavaScript. Estas hojas de ruta te guiarán a través de los conceptos clave y te ayudarán a planificar tu aprendizaje de manera estructurada.

[Roadmap.sh - React](https://roadmap.sh/react)
[Roadmap.sh - JavaScript](https://roadmap.sh/javascript)

### Good First Issue

Good First Issue es una etiqueta utilizada en repositorios de proyectos de código abierto en plataformas como GitHub. Estas issues están etiquetadas para ser amigables con los principiantes. Explora Good First Issues en proyectos de React para contribuir al código abierto y ganar experiencia práctica.

[Good First Issue](https://goodfirstissue.dev/language/javascript)
