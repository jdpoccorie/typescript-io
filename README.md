# TypeScript

## ¿Qué es TypeScript?

TypeScript es un lenguaje de programación que se utiliza para el desarrollo de aplicaciones web y de software en general. Fue creado por Microsoft y se ha convertido en una herramienta popular entre los desarrolladores de JavaScript. TypeScript es conocido por ser un **"superset"** de JavaScript, lo que significa que extiende y mejora las capacidades de JavaScript al tiempo que mantiene compatibilidad con él.

Algunas de las características clave de TypeScript incluyen:

1. **Tipado estático:** TypeScript permite declarar tipos de datos para las variables, parámetros de función y estructuras de datos, lo que ayuda a detectar errores en tiempo de compilación antes de que se ejecuten las aplicaciones. Esto mejora la robustez y la calidad del código.
2. **Inferencia de tipos:** Aunque TypeScript permite la declaración de tipos, también es capaz de inferir automáticamente los tipos de las variables si no se especifican explícitamente. Esto facilita la escritura de código más conciso.
3. **Orientado a objetos:** TypeScript admite programación orientada a objetos, incluyendo clases, interfaces y herencia, lo que hace que sea más fácil organizar y estructurar el código.
4. **Compatibilidad con JavaScript:** Puedes utilizar código JavaScript existente en proyectos TypeScript sin problemas. TypeScript es compatible con la mayoría de las bibliotecas y marcos de trabajo de JavaScript.
5. **Compilación:** El código TypeScript se compila en JavaScript para que pueda ser ejecutado en cualquier navegador o entorno de JavaScript. La compilación ayuda a garantizar la compatibilidad y el rendimiento.
6. **Herramientas de desarrollo:** TypeScript ofrece un sistema de autocompletado más robusto y detección de errores en tiempo real en muchos entornos de desarrollo integrado (IDE), lo que facilita la escritura y el mantenimiento del código.
7. **Comunidad activa:** TypeScript tiene una comunidad de desarrolladores activa y en crecimiento, lo que significa que hay una amplia cantidad de recursos, bibliotecas y herramientas disponibles.

> Cualquier código de JavaScript debería funcionar en TypeScript

<div style="display: flex; justify-content:space-evenly;">
  <div style=>

En Typescript:

```typescript
const nombre = 'Miguel'

// 2. Tipado
const nombre: string = 'Miguel'

// 3. Inferencia de tipo de dato
const persona = {
  name: 'Pepe',
  age: 30
}

persona.name = 45 // Error: TypeScript definió a name como string
```

  </div>
  <div>

Compilación a Javascript:

```js
"use strict"
const nombre = "Miguel"

// 2. Tipado
const nombre = 'Miguel'

// 3. Inferencia de tipo de dato
const persona = {
  name: 'Pepe',
  age: 30
}

persona.name = 45
```

  </div>
</div>

### Ventajas de TypeScript

- **Tipado estático:** TypeScript permite la declaración de tipos para variables, parámetros de funciones y objetos, lo que ayuda a detectar errores de tipo en tiempo de compilación. Esto conduce a un código más robusto y menos propenso a errores en tiempo de ejecución.
- **Mejor mantenibilidad:** Debido al tipado estático y a las anotaciones de tipo, el código TypeScript es más legible y autoexplicativo. Esto facilita la comprensión y el mantenimiento del código a medida que el proyecto crece.
- **Detección temprana de errores:** TypeScript puede detectar errores de código en tiempo de compilación, lo que permite a los desarrolladores solucionar problemas antes de que lleguen a la etapa de ejecución, ahorrando tiempo y esfuerzo en depuración

```typescript
// 1. nos indica un posible error por el tipo de dato
let a = 'hola';
a = 2; 

// 2. Por un tema de legibilidad, nos permite agregar el tipo
//    de dato de nuestras funciones
function suma(a, b) {
  return a + b;
}

suma('Union de', ' cadenas?') // Union de cadenas?
```

**OJO: TYPESCRIPT NO FUNCIONA EN TIEMPO DE EJECUCIÓN**

TypeScript no funciona en tiempo de ejecución en los navegadores o en entornos de tiempo de ejecución de JavaScript. Esto se debe a que TypeScript es un superset de JavaScript y se compila a JavaScript antes de que se ejecute en un navegador o en cualquier otro entorno de tiempo de ejecución de JavaScript

_Compilación:_

La compilación es el proceso mediante el cual el código fuente escrito por un programador se traduce en un lenguaje que una máquina o un entorno de ejecución pueda entender y ejecutar. Este proceso generalmente se realiza utilizando un compilador o un intérprete, dependiendo del lenguaje de programación utilizado.

### Herramientas

* **Visual Studio Code (https://code.visualstudio.com/)**.- Visual Studio Code integra por defecto TypeScript
  * Extensiones recomendadas: Pretty TypeScript Errors (yoavbls)

## Tipos de datos

> **Recomendación:** Siempre que podamos, en TypeScript debemos tratar de no escribir el tipo de datos

TypeScript, al ser un superset de JavaScript, hereda muchos de los tipos de datos de JavaScript y también añade algunas características adicionales para el sistema de tipos estáticos. Aquí tienes una lista de los tipos de datos más comunes en TypeScript:

1. **number:** Representa números, ya sean enteros o decimales
   ```ts
   let cantidad: number = 42;
   ```
2. **string:** Representa cadenas de texto
   ```ts
   let nombre: string = "Juan";
   ```
3. **boolean:** Representa valores booleanos (verdadero o falso)
   ```ts
   let activo: boolean = true;
   ```
4. **any:** Es un tipo que permite cualquier tipo de valor. Se usa cuando no se conoce o no se necesita especificar el tipo.
   ```ts
   let variable: any = 42;
   variable = "Hola";
   ```
5. **array:** Representa una lista de elementos del mismo tipo.
   ```ts
   let numeros: number[] = [1, 2, 3, 4, 5];
   ```
6. **tuple:** Es un tipo que permite definir una matriz con un número fijo de elementos, donde cada elemento puede tener un tipo diferente.
   ```ts
   let persona: [string, number] = ["Juan", 30];
   ```
7. **enum:** Representa un conjunto de valores nombrados. Por defecto, los valores de un enum son enteros, pero también se pueden personalizar.
   ```ts
   enum DiaSemana {
     Lunes,
     Martes,
     Miércoles,
     Jueves,
     Viernes,
     Sábado,
     Domingo
   }
   let hoy: DiaSemana = DiaSemana.Miércoles;
   ```
8. **object:** Representa cualquier objeto no específico.
   ```ts
   let persona: object = { nombre: "Juan", edad: 30 };
   ```
9.  **null y undefined:** Representan la falta de valor o el valor nulo respectivamente.
    ```ts
    let valorNull: null = null;
    let valorUndefined: undefined = undefined;
    ```
10. **void:** Se usa principalmente como tipo de retorno de funciones que no devuelven ningún valor.
    ```ts
    function saludar(): void {
      console.log("Hola");
    }
    ```
11. **never:** Representa un tipo de valor que nunca ocurre. Se utiliza principalmente como tipo de retorno para funciones que siempre lanzan una excepción o nunca terminan.
    ```ts
    function error(mensaje: string): never {
      throw new Error(mensaje);
    }
    ```
12. **union types:** Permite combinar varios tipos en uno solo.
    ```ts
    let resultado: number | string;
    resultado = 42;
    resultado = "Hola";
    ```
13. **symbol:** Los símbolos son una característica de JavaScript que se utiliza para crear identificadores únicos e inmutables.
    ```ts
    const simbolo1: symbol = Symbol("descripción1");
    const simbolo2: symbol = Symbol("descripción2");

    console.log(simbolo1 === simbolo2); // Esto imprimirá "false" porque los símbolos son siempre únicos.
    ```
14. **interfaces:** Permiten definir una estructura de objeto con nombres de propiedades y tipos correspondientes.
    ```ts
    interface Persona {
      nombre: string;
      edad: number;
    }
    ```
15. **Tipos literales:** Puedes definir tipos que solo admiten un valor específico.
    ```ts
    let dia: "Lunes" | "Martes" | "Miércoles" | "Jueves" | "Viernes";
    dia = "Lunes"; // Válido
    dia = "Sábado"; // Error de tipo
    ```
16. **Tipos de función:** Puedes definir tipos para funciones, especificando el tipo de los argumentos y el tipo de retorno.
    ```ts
    type Operacion = (a: number, b: number) => number;
    const suma: Operacion = (a, b) => a + b;
    ```
17. **Tipos genéricos:** TypeScript permite definir tipos y funciones genéricas que pueden trabajar con múltiples tipos de datos.
    ```ts
    function listaReversa<T>(lista: T[]): T[] {
      return lista.reverse();
    }
    ```
18. **Tipos de referencia:** Puedes utilizar tipos de referencia para referenciar un tipo existente.
    ```ts
    type Numero = number;
    const valor: Numero = 42;
    ```
19. **Tipos condicionales:** Puedes crear tipos condicionales que dependan de ciertas condiciones.
    ```ts
    type EsNumero<T> = T extends number ? true : false;
    type Resultado = EsNumero<42>; // true
    ```
20. **Tipos indexados:** Puedes trabajar con tipos indexados para acceder a propiedades de objetos de manera dinámica.
    ```ts
    type Color = "rojo" | "verde" | "azul";
    type Paleta = { [K in Color]: string };
    const colores: Paleta = {
      rojo: "FF0000",
      verde: "00FF00",
      azul: "0000FF",
    };
    ```

> **¿Qué pasa cuando TypeScript no sabe inferir que tipo de dato es?** TypeScript le asigna el tipo **any**, con any ignoramos el tipado en TypeScript, Debemos evitar los any

```ts
let a; // ???
// TypeScript le asigna el tipo `any`
```

## Funciones en TypeScript

### Parámetros de función y argumentos

> Si no le asignamos un tipo de dato, por defecto se usa el `any`, lo recomendable es usar los tipos de datos

Cuando defines una función en TypeScript, puedes especificar los tipos de parámetros que espera la función. Los parámetros son variables locales que toman valores cuando se llama a la función. Los valores que se pasan a la función se denominan argumentos. Veamos un ejemplo:

```ts
function saludar(nombre: string, edad: number) {
    console.log(`Hola, ${nombre}. Tienes ${edad} años.`);
}

saludar("Juan", 30);
```
En este caso, `nombre` y `edad` son parámetros de función. Cuando llamamos a la función saludar, proporcionamos los argumentos "Juan" y 30, que se asignan a nombre y edad, respectivamente.

Cuando queremos tipar objetos:
1era Forma
```ts
function saludar({name, age}: {name: string, age:number}) {
  console.log(`Hola ${name}, tienes ${age} años`)
}
```
2da Forma
```ts
function saludar(persona: {name: string, age:number}) {
  const {name, age} = persona
  console.log(`Hola ${name}, tienes ${age} años`)
}
```

Si queremos retornar un valor desde la funcion, existe la inferencia de typescript
```ts
function saludar(persona: {name: string, age:number}) {
  const {name, age} = persona
  console.log(`Hola ${name}, tienes ${age} años`)
  return age
} // typescript infiere que la funcion saludar retorna un :number
```

### Funciones como expresiones

En TypeScript, las funciones también pueden ser tratadas como expresiones y asignarse a variables o pasarse como argumentos a otras funciones. Esto se conoce como funciones de orden superior. Por ejemplo:

```ts
const suma = function(a: number, b: number): number {
    return a + b;
};
```

Aquí, hemos asignado una función anónima a la variable `suma`, que puede llamarse de la misma manera que una función normal.

Más ejmplos:
```ts
const sayHiFromFunction = (fn: (name: string) => void) => {
  fn('Miguel')
}

const sayHi = (name: string) => {
  console.log(`Hola ${name}`)
}

sayHiFromFunction(sayHi)
```
Otra forma de solucionar es esta:
```ts
const sayHiFromFunction = (fn: (name: string) => void) => {
  fn('Miguel')
}

const sayHi = (name: string) => {
  console.log(`Hola ${name}`)
}

sayHiFromFunction(sayHi)
```