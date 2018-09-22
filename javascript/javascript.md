[Volver al índice](README.md)

# Javascript

En este apartado exploraremos los aspectos referentes a Javascript en su especificación ECMAScript 5, la cual constituye el Javascript más puro, en su totalidad.

En futuros apartados veremos las posteriores especificaciones, de ECMAScript 6 (2015), en adelante, para conocer todos los añadidos que se han ido incluyendo a lo largo de las especificaciones y que son totalmente soportadas en la gran mayoría de browsers actuales.

## [Lenguajes de programación](#lenguajes-de-programacion)

Cualquiera de nosotros ha oido alguna vez que los programas informáticos acaban siendo ristras infinitas de 0 y 1, código binario.

El ejemplo que vemos a continuación sería un programa en código máquina que suma los valores del 1 hasta el 10:

```javascript
00110001 00000000 00000000
00110001 00000001 00000001
00110011 00000001 00000010
01010001 00001011 00000010
00100010 00000010 00001000
01000011 00000001 00000000
01000001 00000001 00000001
00010000 00000010 00000000
01100010 00000000 00000000
```

Es evidente que esto es tedioso de manejar, por no decir que totalmente incomprensible. Es por eso que se inventaron los lenguages de programación que nos permiten abstraernos de este código difícil, usando palabras y reglas que permiten centrarnos en las acciones a alto nivel que nuestro programa debe realizar, con una sintaxis sencilla para facilitarnos la composición de los distintos bloques que constituirán nuestro programa.

El programa anterior en Javascript tiene esta pinta:

```javascript
var total = 0, count = 1;

while (count <= 10) {
 total += count;
 count += 1;
}
```

Mucho más comprensible, ¿verdad? Entonces pasemos a la siguiente sección y conozcamos el lenguaje Javascript.

## [¿Qué es Javascript?](#que-es-javascript)

JavaScript es un lenguaje de programación creado en 1995 y pensado para ejecutar programas dentro de páginas web renderizadas por el explorador Netscape Navigator browser.

Rápidamente fue adoptado por el resto de browsers, convirtiéndose en el **lenguaje de la web**.

Seguramente has oido hablar mal de Javascript, afirmaciones que perderán sus fundamentos cuando conozcamos en detalle cómo funciona y sus más y sus menos.

Como ya hemos comentado, Javascript es el lenguaje de la web, pero desde hace unos años ha traspasado esa frontera y actualmente se usa en otros entornos como el Desktop, el servidor con Node.js o en las base de datos como MongoDB.

> Nota: Javascript no tiene nada que ver con JAVA.

## [Conceptos básicos](#conceptos-basicos)

### [Valores y tipos](#variables-tipos)

Nuestros programas manejan valores, que pueden ser de distinta tipología: números, cadenas de texto, etc. Este abanico de definiciones es lo que se conoce como **Tipos**. Cada uno de los enguajes de programación soporta un conjunto concreto de tipos que lo caracterizan.

JavaScript define sus tipos como tipos primitivos o tipos de objetos; los exploraremos en las posteriores secciones de este capítulo.

### [Variables](#variables)

Cuando programamos, constantemente necesitamos retener valores para usarlos más adelante. Las variables sirven para este fin, nos definen nombres símbolicos a los que se asignan valores. En el momento que se precise podemos usar estas variables usando estos nombres declarados.

Para explicarlo gráficamente, aunque no es la mejor definición, una variable es como un cajón de una estantería en el que podemos albergar cosas (valores) y al que podemos poner una etiqueta (nombre) para referenciarlo y poder encontrarlo más fácilmente.

Las variables en Javascript se definen usando la plabra clave **var**:

```javascript
var sentence = 'Javascript is cool!!';
```

### [Scopes](#scopes)

Dentro de los programas, sea cual sea el lenguaje usado, existe un concepto muy importante, el **Scope**. El scope nos determina el bloque o parte del programa en el cual una variable concreta es visible.

En la imagen que sigue vemos dos scopes diferentes, representados por rectángulos:

![GitHub Logo](/assets/images/javascript/scopes.png)

Inicialmente una determinada variable solamente es visible en el scope en la que fue creada y en los scopes inferiores.

En un programa de Javascript podemos tener diferentes scopes, como veremos más adelante.

### [Statements y expresiones](#statements-expresiones)

Debemos aclarar estos dos conceptos importantísimos en cualquier programa de cualquier lenguaje:

#### Expresión

Es un fragmento de código que produce un valor como resultado.

Podemos tener expresiones muy distintas como un simple número:

```javascript
30
```

o algo con más entidad como:

```javascript
(i + 1) * 10
```

Las expresiones pueden escribirse entre paréntesis, usando operadores, que conoceremos en los próximos puntos o pueden contener subexpresiones.

Usando un símil con nuestro lenguaje natural, una expresión sería una parte de una frase.

#### Statement

Siguiendo el ejemplo anterior, si una expresión sería un fragmento de una frase, un statement sería la propia frase: se compone de una o más expresiones.

Los statements suelen delimitarse con un **;** al final.

## [Comentarios](#comentarios)

En nuestro programas podemos poner comentarios para aclarar para explicar qué hace un bloque concreto o simplemente anotar cosas importantes en el código. Es cosiderada una buena práctica el hecho de comentar nuestro código.

Los compentarios se pueden codificar de dos maneras:

```javascript
// usando la doble barra para un comentario de una línea 

/* Con barra asterisco si queremos
poner comentarios
de más de una línea */
```

## [Tipos y estructuras de datos](#tipos-estructuras)

En este apartado exploraremos los tipos y estructuras de datos disponibles en Javascript.

### [Tipado dinámico](#tipado-dinamico)

Javascript es un lenguaje de tipado dinámico, es decir, no podemos determinar el tipo de una variable en su declaración, quedará tipada en el momento que se le asigne un valor, pero podemos reasignarle el tipo. Veamos unos ejemplos comentados:

```javascript
var a; // su tipo es undefined

// si le asignamos un valor númerico:

a = 10; // su tipo es "number"

// podemos cambiar dinámicamente el tipo asignando otro tipo de valor:

a = 'esto es una cadena de texto'; // ahora el tipo es "string".
```

### [Tipos primitivos](#tipos-primitivos)

Los tipos de datos primitivos son aquellos tipos que nos proporciona un lenguaje de programación en su núcleo.

Expliquemos los tipos primitimos y el resto de tipos, llamados objetos.

#### Tipos primitivos

Son estructuras atomicas que nos proporciona el lenguaje de programación. Se pasan y tratan por valor, es decir, cuando comparamos dos tipos primitivos, éstos se comparan por valor, esto significa que se comparan sus contenidos. Los tipos de datos primitivos de Javascript son: **undefined**, **null**, **boolean**, **number** y **string**.

Los tipos primitivos son tipos immutables, significa que no pueden ser modificados.

#### Objetos

Los objetos se componen the piezas de datos y son tratados por referencia, es decir, tratamos sus referencias en memoria, no su contenido.

Aquí mostramos el diagrama de jerarquía de tipos de javascript.

Estos tipos son mutables, quere decir que podemos modificar parte de su contenido.

![Javascript types](/assets/images/javascript/javascript-types.png)

Algunos tipos venen con las nuevas especificaciones de Javascript, que veremos en apartados posteriores.
___

#### [undefined](#undefined)

Cuando declaramos una variable y no le asignamos un valor, esa avariable es de tipo **undefined**. Este tipo identifica las variables que no han sido inicializadas.

#### [null](#null)

Este tipo sirve para identificar la absencia de valor.

Comparado con **undefined**, si usamos bien este tipo, nos permite saber que una cierta variable anteriormente tenía valor y que ahora no, porque se le ha asignado **null**.

A una variable que tiene contenido podemos asignarle **undefined**, pero no es considerado una buena práctica, si queremos indicar que no tiene valor debemos usar **null**, el valor **undefined** debería ser asignado únicamente por el lenguaje, cuando una variable es declarada pero no ha recibido ningún valor asignado.

