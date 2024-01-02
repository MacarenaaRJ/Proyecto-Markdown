# Markdown enseñando paso a paso Go

Escrito por **Macarena Ramos Jiménez**

- email: macarenarj96@gmail.com
- Linkedin: www.linkedin.com/in/macarenarj

# Tabla de contenidos

## Go

- [[#Instalación: Linux|Instalación: Linux]]
- [[#Sintaxis básica|Sintaxis básica]]
- [[#Estructuras de control|Estructuras de control]]
- [[#Bucles|Bucles]]
- [[#Array (estructuras de datos)|Array (estructuras de datos)]]
- [[#Funciones (modularidad)|Funciones (modularidad)]]
- [[#POO|POO]]
- [[#Creación de la BBDD|Creación de la BBDD]]
- [[#CRUD con MYSQL|CRUD con MYSQL]]
- [[#Pruebas|Pruebas]]
- [[#Buenas prácticas|Buenas prácticas]]
- [[#Conclusión|Conclusión]]
- [[#Recursos|Recursos]]

# Go

El lenguaje de programación Go, también conocido como Golang, es un lenguaje de código abierto desarrollado por ingenieros de Google. Desde su lanzamiento en 2009, Go ha ganado popularidad rápidamente gracias a su simplicidad, eficiencia y rendimiento. Diseñado para abordar los desafíos del desarrollo de software moderno, Go ha sido adoptado en una variedad de aplicaciones, desde sistemas distribuidos hasta desarrollo web.

### **Características Clave de Go**

#### **1. Simplicidad**

Go ha sido diseñado con una sintaxis clara y minimalista. Elimina muchas de las complejidades de otros lenguajes, lo que facilita su aprendizaje para principiantes y su mantenimiento para desarrolladores experimentados.

#### **2. Rendimiento**

Go ofrece un rendimiento excepcional gracias a su compilador eficiente y su recolector de basura concurrente. Esto lo hace adecuado para sistemas de alto rendimiento y aplicaciones a gran escala.

#### **3. Concurrency y Paralelismo**

La concurrencia es una característica fundamental de Go. Los goroutines, unidades livianas de ejecución, facilitan la concurrencia sin el peso de los hilos tradicionales. Además, Go ofrece primitivas para la comunicación entre goroutines, permitiendo construir sistemas concurrentes de manera sencilla.

#### **4. Compilación Estática**

Go se compila estáticamente en binarios independientes del sistema operativo y la arquitectura. Esto facilita la distribución de aplicaciones sin preocuparse por las dependencias del entorno.

#### **5. Manejo de Errores**

Go tiene un enfoque simple pero efectivo para el manejo de errores. La verificación explícita de errores fomenta un código robusto y legible.

#### **6. Biblioteca Estándar:**

La biblioteca estándar de Go es extensa y proporciona muchas herramientas para el desarrollo de aplicaciones, desde manipulación de texto hasta manipulación de redes.

### **Casos de Uso Típicos de Go**

- **Desarrollo de Servidores y APIs:** Go es ampliamente utilizado para construir servidores y APIs eficientes y escalables.
- **Desarrollo de Herramientas:** Gracias a su rendimiento y capacidad para compilar binarios independientes, Go es ideal para construir herramientas de línea de comandos y utilidades.
- **Desarrollo de Microservicios:** La concurrencia nativa de Go y su capacidad para manejar grandes cargas lo convierten en una opción popular para el desarrollo de microservicios.
- **Desarrollo Web:** Frameworks como Gin y Echo permiten el desarrollo rápido de aplicaciones web en Go.

Go es un lenguaje de programación poderoso y fácil de aprender, ideal tanto para principiantes como para desarrolladores experimentados. Su diseño centrado en la simplicidad, el rendimiento y la concurrencia lo hacen relevante para una amplia gama de aplicaciones en el mundo de la programación. A medida que te aventuras en el aprendizaje de Go, descubrirás su elegancia y eficacia, convirtiéndote en parte de una comunidad vibrante que continúa impulsando el desarrollo de software moderno. ¡Bienvenido al mundo de Go!

## Instalación: Linux

Para la instalación en linux se deberá abrir una línea de comandos y ejecutar los comandos mencionados paso por paso. En Linux, se puede abrir la terminal utilizando el atajo de teclado `Ctrl + Alt + T`.

### 1. Eliminación de Instalaciones anteriores de Go

Eliminar cualquier instalación anterior de Go borrando el archivo /usr/local/go folder (si existe) y, a continuación, extraer el archivo que acaba de descargar en /usr/local, creando un nuevo árbol Go en /usr/local/go:

```bash
rm -rf /usr/local/go && tar -C /usr/local -xzf go1.21.5.linux-amd64.tar.gz
```

(Puede haya que ejecutar el comando como root o a través de `sudo`).
**No** descomprimir el archivo en un árbol /usr/local/go existente. Se sabe que esto produce instalaciones rotas de Go.

### 2. Adición de /usr/local/go/bin a la variable de entorno `PATH`

Puedes hacerlo añadiendo la siguiente línea a su $HOME/.profile o /etc/profile (para una instalación en todo el sistema):

```bash
export PATH=$PATH:/usr/local/go/bin
```

**Nota:** Es posible que los cambios realizados en un archivo de perfil no se apliquen hasta la próxima vez que se inicie sesión en el ordenador. Para aplicar los cambios inmediatamente, basta con ejecutar los comandos del shell directamente o ejecutarlos desde el perfil utilizando un comando como `source $HOME/.profile`.

### 3. Verificación de la Instalación de Go

Para asegurarse de que la instalación de Go se haya realizado correctamente, se debe realizar una verificación mediante la línea de comandos.

Ejecutar el siguiente comando en la terminal:

```bash
go version
```

### 4. Confirmación de la Instalación

Confirmar que el comando `go version`, imprime la versión instalada de Go. Esta confirmación garantiza que Go se ha integrado correctamente en su entorno y está listo para su uso.

¡Felicidades! Ha completado exitosamente la instalación de Go en su máquina. Ahora puede proceder a desarrollar aplicaciones y utilizar todas las funcionalidades que ofrece este entorno de programación. Si se encuentra algún problema durante este proceso, consulta la documentación oficial de Go en https://golang.org/doc/install para obtener asistencia adicional.

## Sintaxis básica

### Paquetes

Todos los archivos en Go pertenecen a un paquete. Cada archivo Go pertenece a un paquete específico. Un paquete es una colección de archivos relacionados que proporcionan funcionalidades específicas. Puedes pensar en un paquete como una carpeta que contiene archivos de código.

En Go, hay un paquete especial llamado `main`. Este paquete principal es único porque es el punto de entrada de un programa Go. Cuando ejecutas un programa escrito en Go, la ejecución comienza desde la función llamada `main()` dentro del paquete `main`.

```go
package main

import "fmt"

func main() {
	fmt.Println("Hola, mundo!")
}
```

En este ejemplo:

- `package main` indica que este archivo pertenece al paquete `main`.
- `import "fmt"` se utiliza para importar el paquete `fmt`, que proporciona funciones para imprimir en la consola.
- `func main()` es la función principal donde comienza la ejecución del programa.

Este programa imprime "Hola, mundo!" en la consola cuando se ejecuta.

### Comentarios

Los comentarios son notas que puedes agregar en tu código para explicar lo que estás haciendo. En Go, hay dos formas de escribir comentarios.

1. **Comentario de una línea:** Puedes usar dos barras inclinadas (`//`) para crear un comentario de una línea. Todo lo que escribas después de las dos barras será tratado como un comentario y no afectará el funcionamiento del programa.

```go
// Este es un comentario de una línea
```

2. **Comentario de varias líneas:** Puedes usar `/*` para iniciar un comentario de varias líneas y `*/` para finalizarlo. Todo lo que esté entre estos delimitadores será tratado como un comentario.

```go
/*
Este es un comentario
de varias líneas
*/
```

Los comentarios son muy útiles para explicar tu código a otras personas (o incluso a ti mismo en el futuro) y para hacer que el código sea más comprensible. Puedes usarlos para describir el propósito de una parte específica del código, dar instrucciones, o cualquier cosa que ayude a entender cómo funciona tu programa.

### Tipos de datos básicos

Los tipos de datos son una parte esencial en cualquier lenguaje de programación. En Go, hay varios tipos de datos básicos que puedes usar para almacenar diferentes tipos de información. Aquí tienes una descripción breve de algunos de los tipos de datos básicos en Go:

- Números enteros
  - `int`: Representa números enteros con signo (pueden ser positivos o negativos).
  - `int8`, `int16`, `int32`, `int64`: Representan enteros con signo de 8, 16, 32 y 64 bits respectivamente.
  - `uint`: Representa números enteros sin signo (solo positivos).
  - `uint8`, `uint16`, `uint32`, `uint64`: Representan números enteros sin signo de 8, 16, 32 y 64 bits respectivamente.
- Números decimales - `float32`, `float64`: Representan números decimales (números de punto flotante) con precisión de 32 y 64 bits respectivamente.
- Texto - `string`: Representa cadenas de texto, es decir, secuencias de caracteres
- Booleano - `bool`: Representa valores booleanos, es decir, `true` o `false`.

He aquí algunos ejemplos básicos.

```go
package main

import "fmt"

func main() {
// Cadenas, que pueden sumarse con +.
	fmt.Println("go" + "lang") // Output: golang

// Números enteros y decimales.
    fmt.Println("1+1 =", 1+1) // Output: 1+1 = 2
    fmt.Println("7.0/3.0 =", 7.0/3.0) // Output: 7.0/3.0 = 2.3333333333333335

// Booleanos, con operadores booleanos
    fmt.Println(true && false) // Output: false
    fmt.Println(true || false) // Output: true
    fmt.Println(!true) // Output: false
}
```

**Nota para aquellos que se estén abrumando por la cantidad de tipos de números enteros en Go**
¡No te preocupes por la variedad de tipos de números enteros en Go! Al principio, puede parecer un poco abrumador, pero en realidad, es bastante simple.

Los diferentes tipos de enteros están ahí para darte flexibilidad en cuanto al rango de valores que puedes representar. En situaciones cotidianas, generalmente usarás simplemente `int` para números enteros regulares. Solo si necesitas un control más preciso sobre el tamaño o la eficiencia de almacenamiento, podrías explorar otros tipos de enteros.

Recuerda, la programación se trata de solucionar problemas y crear cosas increíbles. No te sientas presionado por recordar todos los detalles al principio. Con el tiempo y la práctica, te sentirás más cómodo con estos conceptos. ¡Ánimo y a seguir aprendiendo!

### Declaración de variables

En Go, cuando escribes un programa, necesitas decirle al lenguaje qué tipo de información almacenará cada "caja" de datos llamada variable. Esto se llama declarar una variable explícitamente. La ventaja es que el programa puede atrapar errores antes de ejecutarse, como si estuvieras usando un corrector ortográfico para asegurarte de que las palabras estén escritas correctamente.

```go
// var declara 1 o más variables.
var a = "hola"

// Puedes declarar múltiples variables a la vez.
var b, c int = 1, 2
```

En Go, cuando defines una variable y le asignas un valor al mismo tiempo, es lo que se llama "inferir" el tipo de esa variable. Esto significa que no siempre necesitas decirle explícitamente a Go qué tipo de dato es la variable; el propio lenguaje puede descubrirlo por sí mismo.

```go
// Go inferirá el tipo de las variables inicializadas.
var d = true

// Las variables declaradas sin una inicialización correspondiente tienen valor cero. Por ejemplo, el valor cero para un int es 0.
var e int // El valor de e es 0

// La sintaxis := es una forma abreviada de declarar e inicializar una variable, por ejemplo, para var f string = "manzana" en este caso. Esta sintaxis sólo está disponible dentro de las funciones.
f := "manzana"

// En este caso, Go sabe que "edad" es un número entero (int)
edad := 25

// Y aquí, "nombre" es una cadena de texto (string)
nombre := "Juan"

// También puedes inferir el tipo en otras situaciones, como con booleanos
esMayorDeEdad := true

```

### Declaración de constantes

En programación, una constante es un valor que no cambia durante la ejecución del programa. En Go, puedes declarar constantes para valores de texto, cadenas, booleanos y números.

```go
// const declara un valor constante.
const s string = "constant"
```

Cuando defines una constante en Go, el valor asignado a esa constante no puede cambiar durante la ejecución del programa. Además, al igual que con las variables, si no especificas el tipo de la constante, el compilador de Go lo inferirá a partir del valor proporcionado.

Las constantes son útiles cuando quieres asegurarte de que ciertos valores no cambien accidentalmente en tu código y proporcionan una forma clara de identificar esos valores importantes.

### Punteros

Vamos a definir que es un puntero para entender lo que es antes de explicar como es su aplicación en Go. Lo haremos con una analogía de direcciones postales.

Imagina que tienes una casa (variable) y necesitas que alguien más la visite, pero en lugar de darle tu dirección directamente, decides darle una copia de tu dirección a tu vecino. Ahora, tu vecino tiene una copia de la dirección de tu casa (puntero).

1. **La Casa (Variable):**

   - Tu casa es como una variable en programación. Contiene información valiosa, como un número (valor).

2. **La Dirección de la Casa (Puntero):**

   - La copia de la dirección que le diste a tu vecino es como un puntero en programación. En lugar de darle toda tu casa (variable) a alguien, le das solo la dirección (puntero) para que puedan encontrarla.

3. **Visitar la Casa (Desreferenciación):**

   - Ahora, tu vecino (puntero) puede ir a la dirección que le diste y ver el número de la casa (valor). Aquí, "visitar la casa" es como desreferenciar un puntero en programación. Obtienes el contenido real al seguir la dirección.

4. **Cambiar el Número de la Casa (Modificar a través de Punteros):**

   - Imagina que cambias el número de tu casa, y le informas a tu vecino sobre el cambio. Ahora, si alguien usa la dirección que le diste a tu vecino, llegarán a tu nueva casa con el nuevo número.

5. **Nadie en Casa (Puntero Nulo):**

   - Si en algún momento no quieres que nadie visite tu casa, simplemente le dices a tu vecino que la dirección ya no es válida (puntero nulo). Entonces, aunque tengan la dirección, no hay una casa real para visitar.

Esta analogía representa cómo los punteros funcionan en programación. El puntero es como una dirección que apunta a un valor en la memoria, y puedes acceder o modificar ese valor mediante la dirección proporcionada por el puntero.

### Declaración de Punteros en Go

Como ya hemos explicado, en Go, los punteros son variables que almacenan la dirección de memoria de otra variable. Utilizar punteros puede ser fundamental para trabajar con datos de manera eficiente y para modificar valores en lugar de copias.

#### Declaración de Punteros

Para declarar un puntero en Go, utilizamos el símbolo `*` seguido del tipo de datos al que el puntero apunta. Veamos un ejemplo:

```go
// Declaración de una variable entera
var numero int = 42

// Declaración de un puntero a un entero
var punteroNumero *int
```

En este ejemplo, `punteroNumero` es un puntero que puede almacenar la dirección de memoria de una variable entera (`int`).

#### Asignación de Dirección de Memoria

Para asignar la dirección de memoria de una variable a un puntero, utilizamos el operador de dirección `&`. Veamos cómo hacerlo:

```go
// Asignar la dirección de memoria de 'numero' a 'punteroNumero'
punteroNumero = &numero
```

Ahora, `punteroNumero` contiene la dirección de memoria de la variable `numero`.

#### Dereferenciación de Punteros

Para acceder al valor almacenado en la dirección de memoria apuntada por un puntero, utilizamos el operador de desreferenciación `*`. Veamos un ejemplo:

```go
// Imprimir el valor almacenado en la dirección de memoria apuntada por 'punteroNumero'
fmt.Println(*punteroNumero)
```

Esto imprimirá el valor `42`, que es el valor de la variable `numero`.

#### Modificación de Valores a través de Punteros

Una de las ventajas de utilizar punteros es la capacidad de modificar valores directamente en la memoria. Veamos cómo hacerlo:

```go
// Modificar el valor de 'numero' a través de 'punteroNumero'
*punteroNumero = 100
```

Ahora, si imprimimos el valor de `numero`, veremos que ha cambiado a `100`.

```go
fmt.Println(numero) // Imprimirá 100
```

La modificación se refleja directamente en la variable original.

#### Punteros a Nuevas Asignaciones

También puedes asignar memoria de forma dinámica usando la función `new`. Esta función devuelve un puntero al tipo de datos especificado, inicializado con el valor cero.

```go
// Crear un nuevo puntero a un entero inicializado con el valor cero
nuevoPuntero := new(int)
```

Ahora, `nuevoPuntero` apunta a un nuevo espacio de memoria que contiene el valor cero para un entero.

#### Verificación de Punteros Nulos

Los punteros pueden tener el valor especial `nil` que significa que no apuntan a ninguna dirección de memoria. Antes de desreferenciar un puntero, es buena práctica verificar si es nulo para evitar errores.

```go
if punteroNumero != nil {
    fmt.Println(*punteroNumero)
}
```

Esto evita problemas si el puntero no ha sido asignado previamente.

Utilizar punteros en Go te permite trabajar más eficientemente con datos y es especialmente útil cuando necesitas modificar valores directamente en la memoria. Sin embargo, debes tener cuidado al trabajar con punteros para evitar errores sutiles y comportamientos inesperados.

## Estructuras de control

Las estructuras de control son herramientas que te permiten dirigir el camino que sigue tu código cuando se está ejecutando. Son como los comandos que le das a tu programa para manejar situaciones específicas, como decidir qué hacer en determinadas circunstancias o a dónde dirigirse.

Tipos de estructuras de control en Go:

- **Operadores de comparación**: Símbolos para comparar valores (igual, diferente, mayor, menor, etc.).

```go
edad := 25
nombre := "Claudia"
esMayorDeEdad := true
// Igual a
fmt.Println(edad == 25) // true
fmt.Println(nombre == "Juan") // false
fmt.Println(esMayorDeEdad == true) // true
// Diferente de
fmt.Println(edad != 25) // false
fmt.Println(nombre != "Claudia") // true
fmt.Println(esMayorDeEdad != false) // true
// Mayor que
fmt.Println(edad > 20) // true
fmt.Println(edad > 30) // false
// Menor que
fmt.Println(edad < 30) // true
fmt.Println(edad < 20) // false
// Mayor o igual que
fmt.Println(edad >= 25) // true
fmt.Println(edad >= 30) // false
// Menor o igual que
fmt.Println(edad <= 25) // true
fmt.Println(edad <= 20) // false
```

- **Operadores aritméticos**: Símbolos para realizar operaciones matemáticas (suma, resta, multiplicación, etc.).

```go
// Operadores aritméticos
numero1 := 10
numero2 := 5

// Suma
suma := numero1 + numero2
fmt.Println("Suma:", suma) // Resultado: 15

// Resta
resta := numero1 - numero2
fmt.Println("Resta:", resta) // Resultado: 5

// Multiplicación
multiplicacion := numero1 * numero2
fmt.Println("Multiplicación:", multiplicacion) // Resultado: 50

// División
division := numero1 / numero2
fmt.Println("División:", division) // Resultado: 2

// Resto (módulo)
resto := numero1 % numero2
fmt.Println("Resto (módulo):", resto) // Resultado: 0
```

- **Operadores lógicos**: Símbolos que permiten combinar condiciones lógicas (and(y), or(o), not(no)).

```go
// Operadores lógicos
esMayorDeEdad := true
tieneLicencia := true

// Operador AND (&&)
if esMayorDeEdad && tieneLicencia {
	fmt.Println("Puede conducir legalmente.")
} else {
	fmt.Println("No puede conducir legalmente.")
}
// Output: Puede conducir legalmente.

// Operador OR (||)
esEstudiante := false
trabaja := true

if esEstudiante || trabaja {
	fmt.Println("Es estudiante o trabaja (o ambas).")
} else {
	fmt.Println("No es estudiante ni trabaja.")
}
// Output: Es estudiante o trabaja (o ambas).

// Operador NOT (!)
tieneDescuento := false

if !tieneDescuento {
	fmt.Println("No tiene descuento.")
} else {
	fmt.Println("Tiene descuento.")
}
// Output: No tiene descuento.
```

- **Defer**: Retrasa la ejecución de una función hasta que la función que la contiene haya terminado.
  Cuando usas `defer` en una función, le estás diciendo a Go que ejecute esa función justo antes de que la función que la contiene termine su ejecución. Esto es útil para realizar tareas que deben realizarse al final, como cerrar archivos, liberar recursos o realizar acciones de limpieza.

```go
package main

import "fmt"

func main() {

	fmt.Println("Inicio de la función principal")

	// Usando defer para retrasar la ejecución de la función hasta que main() haya terminado
	defer funcionDefer()

	fmt.Println("Fin de la función principal")
}

func funcionDefer() {
	fmt.Println("Esta función se ejecutará al final debido a defer")
}
```

En este ejemplo, cuando ejecutas el programa, verás que la salida es:

```
Inicio de la función principal
Fin de la función principal
Esta función se ejecutará al final debido a defer
```

Aunque `funcionDefer()` se llama antes de que `main()` termine, debido al uso de `defer`, su ejecución se retrasa hasta después de que `main()` haya finalizado. Esto puede ser útil para casos donde deseas realizar ciertas tareas de limpieza o cierre al final de una función, independientemente de cómo termine esa función.

- **If y else**: Estructuras de control condicionales para ejecutar código en base a una condición.

```go
// Ejemplos para ilustrar el funcionamiento de if y else
    if 7%2 == 0 {
        fmt.Println("7 es par")
    } else {
        fmt.Println("7 es impar")
    }
    // Output: 7 es impar

// Puede tener una sentencia if sin un else.
    if 8%4 == 0 {
        fmt.Println("8 es divisible por 4")
    }
    // Output: 8 es divisible por 4

// Los operadores lógicos como && y || suelen ser útiles en las condiciones.
    if 7%2 == 0 || 8%2 == 0 {
        fmt.Println("8 o 7 son pares")
    }
    // Output: 8 o 7 son pares

    if num := 9; num < 0 {
        fmt.Println(num, "es negativo")
    } else if num < 10 {
        fmt.Println(num, "tiene 1 dígito")
    } else {
        fmt.Println(num, "tiene múltiples dígitos")
    }
    // Output: 9 tiene 1 dígito
}
```

- **Switch**: Estructura para realizar múltiples comparaciones y ejecutar código según el caso.

```go
	// Ejemplo básico de switch.
	i := 2
	fmt.Print("Escribe ", i, " como ")
	switch i {
	case 1:
		fmt.Println("uno")
	case 2:
		fmt.Println("dos")
	case 3:
		fmt.Println("tres")
	}
	// Output: Escribe 2 como dos

	// Puedes usar comas para separar múltiples expresiones en la misma declaración case.
	// También usamos la opción case default en este ejemplo.
	switch time.Now().Weekday() {
	case time.Saturday, time.Sunday:
		fmt.Println("Es fin de semana")
	default:
		fmt.Println("Es un día de la semana")
	}
	// Output: dependerá de cuando se ejecute el programa

	// El switch sin una expresión es una forma alternativa de expresar lógica if/else.
	// Aquí también mostramos cómo las expresiones case pueden ser no constantes.
	t := time.Now()
	switch {
	case t.Hour() < 12:
		fmt.Println("Es antes del mediodía")
	default:
		fmt.Println("Es después del mediodía")
	}
	// Output: dependerá de cuando se ejecute el programa
}
```

- **For**: Bucle que se repite mientras se cumple una condición. (Explicación en el siguiente apartado).

## Bucles

`for` es la única construcción de bucle de Go.

He aquí algunos tipos básicos de bucles for.

El tipo más básico, con una única condición.

```go
    i := 1
    for i <= 3 {
        fmt.Println(i)
        i = i + 1
    }
    // Output:
    // 1
	// 2
	// 3
```

Un clásico bucle for inicial/condición/después.

```go
    for j := 7; j <= 9; j++ {
        fmt.Println(j)
    }
    // Output:
    // 7
	// 8
	// 9
```

`for` sin condición se repetirá repetidamente hasta que salgas del bucle o vuelvas de la función que lo encierra.

```go
    for {
        fmt.Println("bucle")
        break
    }
    // Output:
    // bucle
```

También puede continuar con la siguiente iteración del bucle.
Se utiliza para saltar el resto del código en una iteración y pasar a la siguiente.

```go
    for n := 0; n <= 5; n++ {
        if n%2 == 0 {
            continue
        }
        fmt.Println(n)
    }
    // Output:
    // 1
	// 3
	// 5
```

Este bucle `for` imprime los números impares en el rango de 0 a 5, ya que omite los números pares utilizando la declaración `continue`.

## Array (estructuras de datos)

En Go, un array es una secuencia numerada de elementos de una longitud específica. En el código Go típico, los `slices` son mucho más comunes; los arrays son útiles en algunos escenarios especiales.

Aquí creamos un array a que contendrá exactamente 5 ints. El tipo de elementos y la longitud son parte del tipo del array. Por defecto un array tiene valor cero, que para los ints significa 0s.

```go
var a [5]int
fmt.Println("emp:", a) // Output: emp: [0 0 0 0 0]
```

Aquí, `var a [5]int` declara un array de ints con longitud 5. Los arrays en Go se inicializan con valores cero por defecto, en este caso, `[0 0 0 0 0]`.

### Slices

Los slices son un tipo de datos importante en Go, ya que proporcionan una interfaz más potente para las secuencias que los arrays.

A diferencia de los arrays, los slices se tipan sólo por los elementos que contienen (no por el número de elementos). Un slice no inicializado es igual a nil y tiene longitud 0.

```go
var s []string
fmt.Println("uninit:", s, s == nil, len(s) == 0) // Output: uninit: [] true true
```

### Uso Práctico de Slices en Go

Veamos ejemplos prácticos del uso de **slices** en Go:

```go
// Ejemplo del uso de slices en Go
var marcasDeCoches = make([]string, 2)
    marcasDeCoches[0] = "Mazda"
    marcasDeCoches[1] = "Toyota"
    fmt.Println(marcasDeCoches) // Output: [Mazda Toyota]

    // Ejemplo de como agregar un nuevo valor a un slice en Go
	nuevoSlice := append(marcasDeCoches, "Nissan")
    fmt.Println(nuevoSlice) // Output: [Mazda Toyota Nissan]

	// Ejemplo de como agregar varios valores a un slice en Go
	nuevoSlice := append(marcasDeCoches, "Mitsubishi", "Suzuki", "Mazda")
```

Aquí, creamos un slice de strings llamado `marcasDeCoches` y utilizamos la función `append` para agregar nuevos valores al slice. Es importante notar que `append` devuelve un nuevo slice.

### Iteración sobre Slices con un Bucle `for`

Una aplicación común del bucle `for` es iterar sobre secuencias, como arreglos o slices:

```go
números := []int{1, 2, 3, 4, 5}

for índice, valor := range números {
    fmt.Println("Índice:", índice, "Valor:", valor) // Imprime cada valor y cada número del array
    // Output:
	//	Índice: 0 Valor: 1
	//	Índice: 1 Valor: 2
	//	Índice: 2 Valor: 3
	//	Índice: 3 Valor: 4
	//	Índice: 4 Valor: 5
}

```

En este ejemplo, usamos `range` para iterar sobre el slice `números`, obteniendo tanto el índice como el valor en cada iteración del bucle `for`.

El uso de `range` en Go es una característica que facilita la iteración sobre diversas estructuras de datos como arrays, slices, maps, canales y cadenas.

Un ejemplo con una cadena de texto:

```go
for i, c := range "go" {
    fmt.Printf("%d: %s\n", i, string(c))
}
// Output:
// 0: g
// 1: o
```

En este caso, obtenemos el índice y el código Unicode de cada carácter en la cadena.

### Maps: Asociación de Claves y Valores

Además de arrays y slices, **maps** son otra estructura de datos clave en Go. Un map es una colección no ordenada de pares clave-valor. Veamos un ejemplo:

```go
// Creación de un map que asocia nombres de frutas con sus cantidades.
frutas := map[string]int{"manzana": 5, "banana": 2, "naranja": 3}
fmt.Println(frutas) // Output: map[manzana:5 banana:2 naranja:3]
```

Aquí, `map[string]int` declara un map que asocia cadenas (claves) con enteros (valores). Puedes acceder y modificar los valores utilizando las claves.

#### Operaciones Básicas con Maps

Para establecer valores en un mapa, utilizamos la sintaxis `nombre[clave] = valor`. Veamos un ejemplo:

```go
m["k1"] = 7
m["k2"] = 13
```

Aquí, hemos asignado los valores 7 y 13 a las claves "k1" y "k2", respectivamente.

#### Impresión y Acceso a Valores

Podemos imprimir un mapa completo para ver todos sus pares clave/valor:

```go
fmt.Println("mapa:", m) // Output: mapa: map[k1:7 k2:13]
```

Para acceder a un valor en el mapa, utilizamos la sintaxis `nombre[clave]`. Si la clave no existe, se devuelve el valor cero del tipo de valor.

```go
v1 := m["k1"]
fmt.Println("v1:", v1) // Output: v1: 7

v3 := m["k3"]
fmt.Println("v3:", v3) // Output: v3: 0
```

#### Iteración sobre un Mapa

```go
kvs := map[string]string{"a": "apple", "b": "banana"}
for k, v := range kvs {
    fmt.Printf("%s -> %s\n", k, v)
}
// Output:
// a -> apple
// b -> banana
```

Con `range`, podemos iterar sobre los pares clave/valor de un mapa. En este ejemplo, imprimimos las claves y los valores asociados.

#### Iteración Solo sobre las Claves de un Mapa

```go
for k := range kvs {
    fmt.Println("key:", k)
}
// Output:
// key: a
// key: b
```

Si solo necesitamos las claves, podemos utilizar `range` de esta manera para iterar sobre las claves de un mapa.

#### Longitud y Eliminación de Elementos

La función `len` devuelve el número de pares clave/valor en un mapa:

```go
fmt.Println("len:", len(m)) // Output: len: 2
```

Para eliminar un par clave/valor, usamos la función integrada `delete`:

```go
delete(m, "k2")
fmt.Println("mapa:", m) // Output: mapa: map[k1:7]
```

#### Declaración e Inicialización Rápida

Podemos declarar e inicializar un mapa en una sola línea utilizando la siguiente sintaxis:

```go
n := map[string]int{"foo": 1, "bar": 2}
fmt.Println("mapa:", n) // Output: mapa: map[]
```

#### Valor Presente en el Mapa

Cuando buscamos un valor en el mapa, el segundo valor de retorno indica si la clave estaba presente o no:

```go
_, prs := m["k2"]
fmt.Println("prs:", prs) // Output: prs: false
```

### Utilidades en el Paquete Maps

El paquete `maps` contiene funciones útiles. En este ejemplo, se compara la igualdad de dos mapas:

```go
n2 := map[string]int{"foo": 1, "bar": 2}
if maps.Equal(n, n2) {
    fmt.Println("n == n2")
}
// Output: "n == n2"
```

## Funciones (modularidad)

En Go, las funciones son bloques de construcción esenciales que te permiten organizar tu código de manera modular. Imagina que estás construyendo algo con piezas de Lego; cada función sería como una pieza que encajas de manera sencilla para construir programas más grandes y complejos. Aquí te explicaremos con detalle cómo funcionan las funciones en Go, utilizando un ejemplo práctico.

**Definiendo una Función**

En Go, definir una función es como escribir un conjunto de instrucciones que luego puedes reutilizar en diferentes partes de tu programa. Veamos un ejemplo de una función llamada `suma` que toma dos números enteros como entrada y devuelve su suma:

```go
// Definición de la función suma que toma dos parámetros de tipo entero (a y b) y devuelve un entero.
func suma(a, b int) int {
    // Dentro de la función, se realiza la suma de los dos parámetros y se asigna el resultado a la variable local "resultado".
    resultado := a + b
    // La función devuelve el resultado de la suma.
    return resultado
}
```

Aquí, `func` es la palabra clave que indica que estamos definiendo una función llamada `suma`. Los parámetros `a` y `b` son valores que pasaremos cuando llamemos a esta función.

**Llamando a la Función desde la Función Principal (main)**
La función principal, llamada `main`, es como el punto de entrada de tu programa. Aquí es donde puedes usar y combinar diferentes funciones para lograr lo que deseas. Veamos cómo llamamos a nuestra función `suma` desde `main`:

```go
// Función principal (main) que es la entrada principal de ejecución del programa.
func main() {
    // Llamada a la función suma con los valores 3 y 5 como argumentos y se guarda el resultado en la variable "resultadoSuma".
    resultadoSuma := suma(3, 5)
    // Imprime en la consola el mensaje "El resultado es: " seguido del valor almacenado en "resultadoSuma".
    // En este caso, imprimirá "El resultado es: 8" porque 3 + 5 es igual a 8.
    fmt.Println("El resultado es: ", resultadoSuma)
}
```

Aquí, `main` llama a la función `suma` con los valores 3 y 5, y el resultado se almacena en la variable `resultadoSuma`. Luego, imprimimos el resultado en la consola.

Las funciones en Go trabajan juntas para hacer que tu código sea modular y fácil de entender. Con estas piezas de Lego llamadas funciones, puedes construir programas cada vez más complejos a medida que avanzas en tu aprendizaje de programación en Go.

### Goroutines y canales

En Go, las goroutines y los canales son conceptos que permiten la concurrencia y la comunicación entre hilos de ejecución de manera eficiente.

#### Goroutines

Una goroutine es una unidad de ejecución liviana que permite que las funciones se ejecuten concurrentemente de manera eficiente.

Para declarar una goroutine, simplemente agrega la palabra clave `go` antes de llamar a una función.

```go
func imprimirNumeros() {
    for i := 1; i <= 5; i++ {
        fmt.Println(i)
    }
}

func main() {
    go imprimirNumeros()
}
```

En este ejemplo, la función `imprimirNumeros` se ejecutará como una goroutine.

**Concurrencia vs Paralelismo**
Paralelismo es la ejecución simultánea de varias tareas, donde cada tarea se ejecuta en su propio hilo de ejecución o núcleo del procesador. Es un concepto relacionado con la concurrencia, pero con una diferencia crucial: en el paralelismo, las tareas se ejecutan al mismo tiempo físicamente, mientras que en la concurrencia, las tareas pueden avanzar de manera aparentemente simultánea, pero no necesariamente al mismo tiempo real.

Las goroutines permiten la concurrencia, lo que significa que varias funciones pueden ejecutarse en el mismo hilo de ejecución sin necesidad de paralelismo explícito.

**Esperar a que Finalicen las Goroutines**
Para esperar que una goroutine termine, puedes utilizar técnicas como `sync.WaitGroup` o canales. Veremos canales a continuación.

#### Canales

Un canal es una estructura de datos que proporciona comunicación segura entre goroutines. Es como un conducto a través del cual las goroutines pueden intercambiar información.

Se declara un canal utilizando el operador `make` y especificando el tipo de datos que se transmitirá a través del canal.

```go
canalEnteros := make(chan int)
```

**Enviar y Recibir Datos a través de un Canal**
Para enviar datos a un canal, utilizamos la flecha `<-` en la dirección del canal. Para recibir datos, la flecha se invierte.

```go
// Enviar datos al canal
canalEnteros <- 42

// Recibir datos del canal
numero := <-canalEnteros
```

**Cierre de Canales**
Puedes cerrar un canal para indicar que no se enviarán más datos. Esto es útil para que las goroutines receptoras sepan cuándo han recibido todos los datos.

```go
close(canalEnteros)
```

**Select**
La declaración `select` permite esperar múltiples operaciones de canal. Es como un interruptor que elige la operación que puede proceder.

```go
select {
case mensaje := <-canal1:
    fmt.Println("Recibido del Canal 1:", mensaje)
case numero := <-canal2:
    fmt.Println("Recibido del Canal 2:", numero)
}
```

**Rango en Canales**
Puedes utilizar la forma `for valor := range canal` para iterar sobre los valores recibidos de un canal hasta que se cierre.

```go
package main

import (
	"fmt"
	"time"
)

func enviarDatos(canal chan int) {
	// Enviar algunos valores al canal
	for i := 1; i <= 5; i++ {
		canal <- i
		time.Sleep(time.Second) // Añadir una pausa para simular un procesamiento lento
	}

	// Cerrar el canal después de enviar todos los valores
	close(canal)
}

func main() {
	// Crear un canal de enteros
	canalEnteros := make(chan int)

	// Iniciar una goroutine para enviar datos al canal
	go enviarDatos(canalEnteros)

	// Utilizar un bucle 'for range' para recibir valores del canal
	for mensaje := range canalEnteros {
		fmt.Println("Recibido:", mensaje)
	}

	// Este punto se alcanzará cuando el canal se cierre
	fmt.Println("El canal se ha cerrado. Fin del programa.")
}

// Output:
Recibido: 1
Recibido: 2
Recibido: 3
Recibido: 4
Recibido: 5
El canal se ha cerrado. Fin del programa.

```

**Comunicación Secuencial**
Los canales proporcionan una manera segura de comunicarse entre goroutines, facilitando la creación de sistemas concurrentes y paralelos.

## POO

En Go, la programación orientada a objetos (POO) se aborda de manera diferente en comparación con otros lenguajes de programación más tradicionales, como Java o Python. Go no tiene clases ni herencia de clases típicas de la POO. En su lugar, Go utiliza un enfoque basado en tipos llamado "composición de interfaces" para lograr objetivos similares.

Imagina que una interfaz es como un contrato que dice: "Si un tipo quiere ser considerado como algo en particular, debe poder hacer ciertas cosas". Estas "cosas" son los métodos en la interfaz.

Cuando un tipo (como una estructura o un objeto) implementa todos los métodos mencionados en ese contrato (interfaz), decimos que el tipo cumple con ese contrato. Entonces, cualquier cosa que necesite cumplir con ese contrato puede usar ese tipo.

Veámoslo mejor con un ejemplo. En este caso, crearemos una interfaz llamada `Animal` que definirá un método llamado `Sonido`. Luego, implementaremos esta interfaz para dos tipos de animales: el perro y el gato.

**Definición de la Interfaz**
Comencemos por definir nuestra interfaz `Animal` en la que especificamos que cualquier tipo que implemente esta interfaz debe tener un método llamado `Sonido` que devuelve un string.

```go
package main

import "fmt"

// Definición de una interfaz
type Animal interface {
    Sonido() string
}
```

Aquí, `type Animal interface` establece la interfaz, y `Sonido() string` es la firma del método que cualquier tipo que implemente esta interfaz debe proporcionar.

**Implementación para el Perro**
Ahora, crearemos un tipo `Perro` y proporcionaremos la implementación del método `Sonido` para este tipo.

```go
// Implementación para el perro
type Perro struct{}

func (d Perro) Sonido() string {
    return "Woof"
}
```

Aquí, `(d Perro)` indica que estamos implementando el método `Sonido` para el tipo `Perro`.

**Implementación para el Gato**
Similar al paso anterior, implementamos el método `Sonido` para el tipo `Gato`.

```go
// Implementación para el gato
type Gato struct{}

func (c Gato) Sonido() string {
    return "Meow"
}
```

**Uso de la Interfaz en la Función Principal (main)**
Ahora, en la función `main`, creamos instancias de tipos que implementan la interfaz `Animal` (en este caso, `Perro` y `Gato`). Luego, almacenamos estas instancias en un slice de `Animal` y llamamos al método `Sonido` a través de la interfaz.

```go
func main() {
    // Crear instancias de tipos que implementan la interfaz
    perro := Perro{}
    gato := Gato{}

    // Llamar al método Sound a través de la interfaz
    animales := []Animal{perro, gato}
    for _, animal := range animales {
        fmt.Println(animal.Sonido())
        // Output:
	        // Woof
			// Meow
    }
}

```

Aquí, creamos un slice de `Animal` que puede contener tanto instancias de `Perro` como de `Gato`. En el bucle, llamamos al método `Sonido` para cada animal en el slice, y obtenemos los sonidos específicos de cada tipo.

En este ejemplo, la interfaz `Animal` nos permite llamar al método `Sonido` sin preocuparnos por los detalles específicos de cada tipo de animal.

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

Primero deberemos establecer una conexión con la base de datos. Para ello utilizaremos el paquete **database/sql** de Go.

```go
// Abrir conexión a la base de datos
db, err := sql.Open("mysql", "usuario:contraseña@/mi_base_de_datos")
if err != nil {
    panic(err)
}
defer db.Close()
```

En Go, los paquetes externos, como `database/sql`, son bibliotecas desarrolladas por la comunidad o terceros para proporcionar funcionalidades específicas que no están incluidas en la biblioteca estándar de Go. El paquete `database/sql` en particular se utiliza para interactuar con bases de datos SQL desde programas Go.

Gracias a este paquete, podemos realizar operaciones como consultas, inserciones, actualizaciones y eliminaciones en bases de datos SQL de manera eficiente y segura. Además de que aporta eficiencia con bases de datos SQL, proporcionando una interfaz uniforme y una abstracción para trabajar con diferentes sistemas de gestión de bases de datos.

### Crear (Create)

En el contexto de bases de datos, la operación de "Crear" se refiere a la acción de agregar nuevos registros o datos a una tabla. Es como añadir una nueva entrada a una lista. En la mayoría de los sistemas de gestión de bases de datos relacionales, esto se realiza mediante la instrucción SQL `INSERT`.

```go
// Insertar datos en la tabla "usuarios"
result, err := db.Exec("INSERT INTO usuarios (nombre, edad) VALUES (?, ?)", "Ejemplo", 25)
if err != nil {
    panic(err)
}
```

En este código:

- `db.Exec` ejecuta una instrucción SQL en la base de datos. En este caso, estamos insertando datos en la tabla "usuarios".
- `"INSERT INTO usuarios (nombre, edad) VALUES (?, ?)"` es la instrucción SQL que indica que queremos insertar datos en la tabla "usuarios". Los `?` son marcadores de posición para los valores reales que se insertarán.
- `"Ejemplo"` y `25` son los valores reales que se insertarán en las columnas "nombre" y "edad", respectivamente.
- `result` contiene información sobre el resultado de la ejecución de la instrucción, y `err` es una variable que captura cualquier error que pueda ocurrir durante la ejecución.

Después de insertar datos, es posible que desees obtener información adicional, como el ID del último registro insertado. Esto puede ser útil, por ejemplo, si la tabla tiene una columna de identificación automática (`AUTO_INCREMENT` en MySQL). Nuestra columna id es `AUTO_INCREMENT` como añadimos mediante la creación de la base de datos en el apartado anterior.

```go
// Obtener el ID del último registro insertado
lastInsertID, err := result.LastInsertId()
if err != nil {
    panic(err)
}

fmt.Println("ID del último registro insertado:", lastInsertID)
// El output será del registro que hemos insertado en la tabla de usuarios
```

### Leer (Read)

La operación de "Leer" se refiere a la acción de recuperar información almacenada en la base de datos. Es como obtener información de una lista. En la mayoría de los sistemas de gestión de bases de datos relacionales, esto se realiza mediante la instrucción SQL `SELECT`.

Para consultar datos desde MySQL en Go, puedes utilizar la función `Query` y luego iterar sobre los resultados.

```go
// Consultar todos los usuarios
rows, err := db.Query("SELECT id, nombre, edad FROM usuarios")
if err != nil {
    panic(err)
}
defer rows.Close()
```

En este código:

- `db.Query` ejecuta una instrucción SQL en la base de datos. En este caso, estamos consultando todos los usuarios de la tabla "usuarios".
- `"SELECT id, nombre, edad FROM usuarios"` es la instrucción SQL que indica que queremos seleccionar las columnas "id", "nombre" y "edad" de la tabla "usuarios".
- `rows` es un conjunto de resultados que contiene los datos recuperados de la base de datos.
- `defer rows.Close()` asegura que el conjunto de resultados se cierre después de que hayamos terminado de trabajar con él. Esto es importante para liberar recursos.

Después de ejecutar la consulta, necesitas iterar sobre los resultados para procesar la información recuperada. En este caso, utilizamos un bucle `for` junto con `rows.Next()` para avanzar a través de cada fila de resultados.

```go
// Iterar sobre los resultados
for rows.Next() {
    var id, edad int
    var nombre string
    err := rows.Scan(&id, &nombre, &edad)
    if err != nil {
        panic(err)
    }
    fmt.Printf("ID: %d, Nombre: %s, Edad: %d\n", id, nombre, edad)
}
```

En este código:

- `rows.Scan(&id, &nombre, &edad)` escanea los valores de la fila actual en las variables `id`, `nombre` y `edad`. Esto asocia los valores de las columnas con las variables que proporcionamos.
- `fmt.Printf("ID: %d, Nombre: %s, Edad: %d\n", id, nombre, edad)` imprime los datos de la fila en la consola.

En resumen, la operación de "Leer" en una base de datos implica recuperar información almacenada en la base de datos. En el ejemplo de Go, utilizamos la instrucción `SELECT` para consultar todos los usuarios de la tabla "usuarios". Luego, iteramos sobre los resultados y procesamos la información recuperada. Esta operación es fundamental para obtener datos de una base de datos y es una parte clave de muchas aplicaciones.

### Actualizar (Update)

La operación de "Actualizar" se refiere a la acción de modificar los datos existentes en la base de datos. Es como cambiar la información de un elemento en una lista. En la mayoría de los sistemas de gestión de bases de datos relacionales, esto se realiza mediante la instrucción SQL `UPDATE`.

```go
// Actualizar la edad del usuario con ID 1
_, err := db.Exec("UPDATE usuarios SET edad = ? WHERE id = ?", 30, 1)
if err != nil {
    panic(err)
}
```

En este código:

- `db.Exec` ejecuta una instrucción SQL en la base de datos. En este caso, estamos actualizando la edad del usuario con ID 1 en la tabla "usuarios".
- `"UPDATE usuarios SET edad = ? WHERE id = ?"` es la instrucción SQL que indica que queremos actualizar la columna "edad" en la tabla "usuarios" donde el ID es igual a 1. Los `?` son marcadores de posición para los valores reales que se utilizarán en la actualización.
- `30` es el nuevo valor que estamos estableciendo para la columna "edad" del usuario con ID 1.
- `1` es el ID del usuario al que queremos aplicar la actualización.
- `_` es una convención en Go para indicar que estamos ignorando el resultado de `db.Exec`. En este caso, estamos interesados en comprobar si hay algún error (`err`).

Es importante manejar los errores al realizar operaciones en la base de datos. En este caso, si hay un error durante la ejecución de la instrucción `UPDATE`, el programa entra en estado de pánico y muestra el error.

### Eliminar (Delete)

La operación de "Eliminar" se refiere a la acción de eliminar datos existentes de la base de datos. Es como quitar un elemento de una lista. En la mayoría de los sistemas de gestión de bases de datos relacionales, esto se realiza mediante la instrucción SQL `DELETE`.

```go
// Eliminar el usuario con ID 1
_, err := db.Exec("DELETE FROM usuarios WHERE id = ?", 1)
if err != nil {
    panic(err)
}
```

En este código:

- `db.Exec` ejecuta una instrucción SQL en la base de datos. En este caso, estamos eliminando el usuario con ID 1 de la tabla "usuarios".
- `"DELETE FROM usuarios WHERE id = ?"` es la instrucción SQL que indica que queremos eliminar la fila de la tabla "usuarios" donde el ID es igual a 1. El `?` es un marcador de posición para el valor real que se utilizará en la eliminación.
- `1` es el ID del usuario que queremos eliminar.
- `_` es una convención en Go para indicar que estamos ignorando el resultado de `db.Exec`. En este caso, estamos interesados en comprobar si hay algún error (`err`).

En esta sección, hemos explorado las operaciones fundamentales de CRUD (Crear, Leer, Actualizar y Eliminar) utilizando MySQL, un sistema de gestión de bases de datos relacional. Estas operaciones son la esencia de la interacción con bases de datos y son esenciales para cualquier aplicación que requiera persistencia de datos.

Ya sea creando nuevas entradas, consultando información específica, actualizando datos existentes o eliminando registros, estas habilidades son indispensables para cualquier desarrollador que trabaje con bases de datos.

Continúa explorando y practicando estas operaciones CRUD, ya que son conceptos clave que encontrarás en una variedad de proyectos. A medida que ganas experiencia, descubrirás cómo aplicar estas habilidades de manera efectiva para construir aplicaciones robustas y eficientes.

## Pruebas

Los tests o pruebas son herramientas cruciales para asegurarte de que tu código funcione como esperas y para facilitar futuras modificaciones sin introducir errores. En Go, escribir tests es una parte esencial del desarrollo.

### Configuración Inicial

Crea un archivo con el sufijo `_test.go` en el mismo directorio que tu código. Por ejemplo, si tienes un archivo `funciones.go`, tu archivo de tests podría llamarse `funciones_test.go`.

### **Escribir un Test Simple**

Define una función de test utilizando el paquete `testing`. Asegúrate de que el nombre comience con la palabra `Test`.

```go
// funciones_test.go
package main

import "testing"

func TestSuma(t *testing.T) {
    resultado := suma(3, 5)
    if resultado != 8 {
        t.Errorf("Esperado: 8, Obtenido: %d", resultado)
    }
}
```

### **Ejecutar el Test**

Utiliza el comando `go test` en la terminal para ejecutar tus tests.

```shell
go test
```

Si todo está bien, verás un mensaje indicando que el test ha pasado.

### **Test con Varias Verificaciones**

Puedes tener múltiples verificaciones dentro de un test. Si alguna de ellas falla, el test completo fallará.

```go
func TestMultiplicacion(t *testing.T) {
    resultado := multiplicacion(4, 3)
    if resultado != 12 {
        t.Errorf("Esperado: 12, Obtenido: %d", resultado)
    }

    resultado = multiplicacion(5, 0)
    if resultado != 0 {
        t.Errorf("Esperado: 0, Obtenido: %d", resultado)
    }
}
```

### **Subtests**

Puedes crear subtests para organizar mejor tus pruebas y recibir información más detallada sobre los errores.

```go
func TestDivision(t *testing.T) {
    t.Run("División válida", func(t *testing.T) {
        resultado, err := division(10, 2)
        if err != nil || resultado != 5 {
            t.Errorf("Esperado: 5, Obtenido: %d", resultado)
        }
    })

    t.Run("División por cero", func(t *testing.T) {
        _, err := division(5, 0)
        if err == nil {
            t.Error("Se esperaba un error pero no se recibió")
        }
    })
}
```

### **Benchmarks**

Puedes escribir benchmarks para evaluar el rendimiento de tu código. Usa la función `testing.B` para medir el tiempo.

```go
func BenchmarkSuma(b *testing.B) {
    for i := 0; i < b.N; i++ {
        suma(3, 5)
    }
}
```

Ejecuta benchmarks con el comando:

```shell
go test -bench=.
```

### **Cobertura de Código**

Verifica la cobertura de tu código para asegurarte de que tus tests están probando todas las partes esenciales.

```shell
go test -cover
```

Esto es una breve introducción sobre tests en Go que te servirá como conceptos básicos para escribir tests efectivos en Go. Estos tests no solo garantizarán el correcto funcionamiento de tu código, sino que también facilitarán futuras modificaciones y colaboración con otros desarrolladores.

## Buenas prácticas

Las "buenas prácticas" en el mundo de la programación se refieren a enfoques, técnicas, y pautas recomendadas que los desarrolladores adoptan para escribir código de alta calidad, mantenible y eficiente. Estas prácticas han surgido a lo largo del tiempo como respuestas a desafíos comunes en el desarrollo de software y buscan mejorar la legibilidad, la escalabilidad y la robustez de los programas.

"Effective Go" es una guía de buenas prácticas y convenciones para escribir código en Go, proporcionada por el equipo oficial de Go. Algunas de las buenas prácticas más esenciales:

### 1. **Formato de Código:**

- **Espacios en Blanco:**
  - Usa espacios en blanco de manera consistente, preferiblemente con sangrías de 4 espacios.
- **Líneas Vacías:**
  - Usa líneas vacías para separar lógicamente bloques de código relacionados.

### 2. **Nombres de Variables y Funciones:**

- **Elige Nombres Significativos:**
  - Usa nombres descriptivos para variables y funciones. Evita nombres cortos y crípticos.
- **Evita Iniciales Duplicadas:**
  - Evita nombres como `responseCode` y `responseErrorCode`. Prefiere `code` y `errorCode`.

### 3. **Comentarios:**

- **Comentarios Concisos:**
  - Escribe comentarios concisos que expliquen el porqué y no el qué (a menos que no sea obvio).
- **Evita Comentarios Obvios:**
  - No comentes cosas obvias; el código debe ser claro por sí mismo.

### 4. **Panic y Recover:**

- **Evita Usar Panic/Recover para Errores Rutinarios:**
  - Usa el manejo de errores en lugar de panic/recover para situaciones rutinarias.

### 5. **Errores:**

- **Devuelve Errores como Último Valor:**
  - Si una función devuelve un error, hazlo como el último valor de retorno y verifica el error antes que cualquier otro valor.

### 6. **Punteros:**

- **Usa Punteros con Cuidado:**
  - Utiliza punteros cuando sea necesario, pero evita el uso excesivo. El acceso directo a valores es preferible en muchos casos.

### 7. **Interfaces:**

- **Diseña Interfaces con Cuidado:**
  - Diseña interfaces que reflejen el comportamiento necesario, pero no crees interfaces por adelantado.

### 8. **Paquetes y Visibilidad:**

- **Controla la Visibilidad:**
  - Controla la visibilidad de las variables y funciones en tus paquetes. Usa mayúsculas para exportar y minúsculas para no exportar.

### 9. **Canales:**

- **Cierre de Canales:**
  - No cierres nunca un canal desde el lado que lo recibe; hazlo desde el lado que lo envía.

### 10. **Testing:**

- **Nombres de Funciones de Pruebas:**
  - Nombra las funciones de prueba con el prefijo `Test`, seguido por el nombre de la función que estás probando.

## Conclusión

¡Felicidades, has completado tu guía de introducción a Go! Has adquirido los fundamentos esenciales de este poderoso lenguaje de programación y estás listo para comenzar tu viaje en el desarrollo de software.

#### Siguientes Pasos:

1. **Practica, Practica, Practica:** La práctica es clave para consolidar tus conocimientos. Crea pequeños proyectos, resuelve desafíos y participa en comunidades en línea.

2. **Explora Proyectos de Código Abierto:** Examina proyectos de código abierto escritos en Go. Esto te brindará una visión valiosa sobre las mejores prácticas y la estructura de proyectos más grandes.
3. **Colabora y Aprende de Otros:** Únete a la comunidad Go. Participa en foros, grupos de discusión y eventos locales. La colaboración y el intercambio de conocimientos te harán crecer como desarrollador.

4. **Amplía tus Conocimientos:** Investiga más sobre temas avanzados como concurrencia, testing, y desarrollo web en Go. La documentación oficial y otros recursos en línea son excelentes fuentes para continuar aprendiendo.

5. **Desarrolla tus Proyectos Personales:** ¡Sé creativo! Construye aplicaciones que te interesen y que resuelvan problemas reales. La mejor manera de aprender es aplicar tus conocimientos en proyectos prácticos.

El aprendizaje continuo es la clave para destacar en el desarrollo de software. Go es un lenguaje versátil y eficiente que te permitirá abordar una variedad de desafíos. A medida que avanzas, no tengas miedo de enfrentarte a nuevos conceptos y experimentar. La experiencia práctica te convertirá en un desarrollador más sólido.

Recuerda, el camino para convertirte en un maestro de Go comienza con el primer paso. Disfruta del viaje, mantente curioso y sigue construyendo cosas asombrosas con Go. Buena suerte en tu emocionante travesía de programación.

## Recursos

Esta lista de recursos te ayudará en tu camino de aprendizaje de Go.

- [A Tour of Go](https://go.dev/tour/list)
  "A Tour of Go" (Un Recorrido por Go) es un tutorial interactivo en línea que proporciona una introducción práctica al lenguaje de programación Go. Fue creado por los desarrolladores de Go y está disponible en el sitio web oficial de Go.

- [Learn Go with Tests](https://quii.gitbook.io/learn-go-with-tests/)
  "Learn Go with Tests" es un recurso educativo creado por Chris James (también conocido como Chris Pine) que se centra en enseñar el lenguaje de programación Go (Golang) mediante el desarrollo de pruebas unitarias. La idea principal es aprender Go a través de la escritura de pruebas, lo que promueve la práctica del desarrollo impulsado por pruebas (TDD, por sus siglas en inglés).
  Es un recurso muy interesante para seguir familiarizándose con el idioma.

- [Go by Example](https://gobyexample.com/)
  Go by Example es una excelente referencia para aprender Go a través de ejemplos prácticos. Cada ejemplo aborda un concepto específico. Es un buen lugar de consulta cuando se tienen dudas sobre la sintaxis de Go.

- [Effective Go](https://go.dev/doc/effective_go)
  Proporciona consejos y mejores prácticas para escribir código Go de manera efectiva.

- [Documentación Oficial de Go](https://golang.org/doc/)
  La documentación oficial de Go es un recurso fundamental. Incluye tutoriales, guías de referencia y documentación detallada sobre el lenguaje y sus bibliotecas estándar.

- [Go Playground](https://play.golang.org/)
  Es un entorno en línea donde puedes escribir, probar y compartir código Go sin necesidad de instalar nada en tu computadora.

- [Roadmap Go](https://roadmap.sh/golang)
  La página en Roadmpa(Go) presenta un "mapa de ruta" (roadmap) para aprender Go (Golang), proporcionando una guía estructurada para aquellos que desean adquirir habilidades en este lenguaje de programación. Este mapa de ruta está organizado en varias secciones, cada una representando un área clave del desarrollo en Go.

- [Friends of Go](https://friendsofgo.tech/)
  Este blog creado por dos chicos de Barcelona explica de manera clara y concisa diferentes conceptos de Go. Buen recurso para seguir indagando y aprendiendo de diferentes temas de Go.

- [Codewars](https://www.codewars.com/)
  Codewars es una plataforma en línea que ofrece desafíos de programación y ejercicios para desarrolladores. Su objetivo es proporcionar una manera divertida y educativa para que los programadores mejoren sus habilidades a través de la resolución de problemas de codificación.

- [Good First Issue (Go)](https://goodfirstissue.dev/language/go)
  Good First Issue es un sitio web que recopila y presenta problemas de código etiquetados como "good first issue" (buen primer problema) en repositorios de proyectos de código abierto en GitHub. Si te quieres introducir en el mundo del Open Source, este puede ser un buen lugar de comienzo.

- [Go Wiki](https://go.dev/wiki/)
  Contiene una variedad de recursos, incluyendo guías, tutoriales y enlaces a proyectos y bibliotecas populares.
