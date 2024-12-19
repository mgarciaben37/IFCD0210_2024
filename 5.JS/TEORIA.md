# ARQUITECTURA CLIENTE / SERVIDOR

Capa de software

http--> clientes solo saben hacer una cosa que se llama request

cliente --------> servidor

## Web Estatica - Web Dinamica

Del cliente al Servidor hace una petición request para pedir un recurso.
El servidor devuelve/response al cliente con ese recurso.

Si en el servidor no existe el recurso, nos devuelve un 404.

SSR

CSR (cliente solicita al servidor "patatas", el servidor no tiene "patatas", y le devuelve algo )

Freamwork:

- Angular
- React
- Vue

App Server:

- Perlr
- PHP
- Java
- C++ /C#
- Phyton
- JS(Node)

API Server: (Datos crudos)
SPA--> Single Page Aplication

https://excalidraw.com/#json=XFY65MH8YReX2_qS_bb7O,Q7HmWNW6Izyvl3E0LCaxkw

# NAVEGADORES WEB

Parseado del HTML para crear el DOM --> árbol de construcción --> se construye el layout--> Pintarlo

CPU (construcción de layout) -- GPU (pintado)

Los Navegadores se caracterizan por utilizar un motor de renderizado concreto Webkit / Gecko/ Blink (chrome/ otro basado en cromiun)

Hay que convertir el lenguaje (parsing)

Document Object Model --> DOM

## JS Engines

Javascript es un interprete, es decir, va linea por linea, que tiene 2 compiladores, (compilador original, compilador optimizado)

Los compiladores son distintos en los distintos navegadores. (TurboFan, SpiderMonkey)

ARTICULO PARA LEER--> javascript engines The Good Parts

# JAVASCRIPT

## 10/12/2024

Math.random --> Numero aleatorio entre 0 y 1

Math.trunc -->numero entero hacia abajo
Math.flor -->

Math.ceil --> numero entero hacia arriba

## JAVASCRIPT CON FRONT

En javascript necesitamos reconocer los elementos que aparecen en la pagina.
Cuando llega el HTML lo parsea:que es esquematicar de forma jerarquica, a partir de esta jerarquia se construye el DOM (Document Object Model)

https://excalidraw.com/#json=5cGyA41vjc14znFuVp1MC,eEzJ93-rcLMkRM-yZyH5jA

![alt text](image.png)

Excalibur Profesor --> https://excalidraw.com/#room=682f4b93591314b4482f,uWtj0erMVYlY-3ll0_LoSQ

## OBJETOS

const obj2 = {...obj1}, son 2 objetos distiontos pero con los mismos datos, los datos son inmutables, no cambian EJ:

![alt text](image-1.png)
![alt text](image-2.png)

los objetos pueden compartir objetos, pero nunca obtener objetos.

![alt text](image-3.png)

las variables siempre apuntan a un dato
las variables pueden apuntar a objetos

## DOM

- DOM como árbol de objetos

Ej para acceder al DOM--> console.dir(document)

- ACCESO SECUENCIAL a cualquier nodo

Ej: console.dir(
(document.children[0].children[0]);
);

- ACCESO DIRECTO ANTIGUO "PREVIO"

Ej. document.getElementById('id1)

- ACCESO DIRECTO NUEVO

document.querySelector('h1')
document.querySelectorAll('img')

Ej: console.dir(headerElement.querySelectorAll('img'));

children representa los nodos de tipo elemento.

Modela a traves de objetos de todo el documento.

¿Que caracteriza a todos los nodos? que son objetos de javascript.

los element HTML tienen esas propiedades,EJ: Objeto H1 y propiedad --> azules claras y lilas. Propiedades (azules) son valores y los metodos (lilas)

```JS
console.dir(
    document.children[0].children[0]
);
```

/_traducido esto significa que mires en el document el children que seria el html y el segundo children seria el head_/

console.dir(document) --> es la manera de ver todas las propiedades de un objeto JavaScript específicado por consola

## 11/12/2024

## DATOS PRIMITIVOS Y REFERENCIADOS

### ------DATOS PRIMITIVOS:------

- Number
- String
- Boolean
- Undefined
- NaN
- bigInt (no usaremos en principio)
- Symbol (no usaremos en principio)

Para que los datos signifiquen algo, hay que incorporar las Variables. Las variables no contienen NADA, sino que apuntan a los datos. variable ---> Dato. Las variables tienen un identificador y apuntan a un dato, del tipo que queramos.

Tipos de formas de declarar variables:

- let
- const --> No se puede reasignar. (SOLO EN LOS VALORES PRIMITIVOS)

### ------OBJETOS------

object.freeze(obj) --> propiedad de congelación. En este caso se congela el objeto, es decir, no puede cambiar el objeto

### ------TIPOS DE VARIABLES------

```TS (typescript)
    let foo: string;
    foo = '';
```

//foo vale undefined, cuanto puede valer en el futuro cualquier string

débil/dinamico-->se hereda a raíz del dato. En javascript se hereda

```JS (javascript)
    let foo
    foo = 4;
```

- coercion y casting:
  Hay 8 cosas que se convierten a falso:
  - Falsy: false, null, undefined, NaN, 0, -0, 0n, ''
  - Truty: TODO LO DEMAS

### ------SENTENCIAS Y EXPRESIONES:------

- Sentencias (statements)--> instrucciones, es decir, le digo a javascript "haz esto" y javascript hace algo. Las sentencias es cada trocito de codigo que acaba en ";" y a base de muchas sentencias construyo el lenguaje
- Expresiones--> ¿JS dime algo?. Siempre te da 2 " 1 contestacion, un unico valor". Primero se evalua a una sola cosa y una vez que te ha contestado se lo asignas(guardas) a una variable

```JS
    const foo = Math.random();
    const baz = 2+2;
```

- Sentencias de control -->

```JS
    if(!foo){...}
    if(foo === 0){....}
```

SIEMPRE VA A CONSIDERAR LO QUE HAY DENTRO DE LOS PARÉNTESIS DE FORMA BOOLEANA

### ------FUNCIÓN------

Nos permite hacer un bloque de código. Invocaremos a la función posteriormente cuando queramos.

```JS
    function foo() {}
    const foo = function() {}
```

### ------OBJETOS------

Colecciones de datos. Podemos acceder de dos maneras:

- Indexado los datos --> array []
- Nombrando los datos --> object {}

Todo lo que se le puede hacer a un objeto se le puede hacer a un array

```JS
    const data = [
        'Pepe',
        22
    ]

    data.foo = "Soy un array"
```

```JS
    let x = 2  //x vale 2
    let y = x //y vale 2
    x = 5 //x ahora vale 5
    y  //y seguirá valiendo 2
```

> [!IMPORTANT]
>
> {...}
>
> {...foo} Operador de desestructuraron. Sirve para replicar un objeto.

## SEGUIMOS CON LA WEB

podemos usar como identificadores "data-id"

> [!IMPORTANT]
>
> ERROR
>
> Type = "Module" en el Script

## 12/12/2024

### PARÁMETROS:

Si a Javascript le pasamos 3 parámetros y la función solo tiene 2, el resultado sera de los 2 primeros.

FUNCIONES:

Función Pura, no depende ni modifica nada del exterior y siempre que devuelve los mismo parámetros recibe los mismos valores.
El consol.log--> es un EFECTO, hace que las funciones no sean puras.

Si las funciones no tienen RETURN no devuelve nada.

Las funciones en javascript son objetos, con lo que podemos hacer cosas raras:

```JS
const baz = function(){
    return Math.random();
}

baz.description = "Soy Baz";

console.log(baz());
```

Manera moderna de crear funciones:
=> fact arrow

> [!IMPORTANT]
>
> ARROW FUNCTIONS
>
> SI SOLO TENGO UNA LINEA DE CODIGO podemos quitar las {} y el return

```JS

const Pepita = () =>{
    return Math.random();
}

console.log(Pepita()); // resultado de la funcion
console.log(Pepita); // dice lo que es--> en este caso una funcion

```

> [!IMPORTANT]
>
> CALL BACK
>
> Es una funcion que llama a otra funcion , pero NO se ejecuta, es decir, no se ponen los parentesis.

insertAdjacentHTML()--> INSERTA, NO BORRA NADA. Dame la posicion de insertado y el string:

- beforeBegin
- afterBegin
- beforeEnd
- afterEnd

EJEMPLO EN HTML:

```HTML
beforebegin
    <div class="sample">
        afterbegin
        <p></p>
        <p></p>
        beforeend
    </div>
    afterend
```

EJEMPLO EN JS:

```JS

document
    .querySelector("body")
    .item.insertAdjacentHTML("afterbegin", createHeader_brown(title));
```

FUNCIÓN PARA CUANDO QUERAMOS SUSTITUIR UN LOGO:

```JS

function createHeader(title, logoMarron = true) {
    let img =''
    if(logoMarron){
        img = "./assets/logo-brown-bisque.svg";
    } else{
        img = "./assets/logo-golden-bisque.svg";
}
}

```

### COMO MODIFICAR DESDE JAVASCRIPT LOS ATRIBUTOS DE HTML

A NIVEL DE HTML: ATRIBUTO
Los botones un comportamiento implícito, por ejemplo click parpadea.
Se puede cambiar con el atributo disabled, se pone clarito.
Por debajo, podemos ver que esta disabled, pero tiene una serie de estilos.

```HTML
<button disabled>Ahora lo borro</button>
```

<button disabled></button>
es un atributo de HTML que NO TIENE VALOR, traducido a javascript, si lo pones esta true, si no lo pones esta false.

A NIVEL DE JAVASCRIPT: PROPIEDAD

```JS
 elementButton.disabled = true;
```

SETEAME EL ATRIBUTO DESABLED DE HTML EN JAVASCRIPT

Es mejor practica hacerlo asi que el ejemplo anterior.En el valor vacío no es necesario poner nada.

```JS
 elementButton.setAttribute('disabled', '');
```

QUITAR ATRIBUTO

```JS
 elementButton.removeAttribute('disabled');
```

### SEGUIMOS CON EL JUEGO

```HTML
.currentPlayer{
        color: var(--color-accent);
        transform: scale(110%);
    }
```

> [!IMPORTANT]
>
> .classList
>
> Puedo añadir clases, sustituir, cambiar, toggle(si no tienes la clase te la pone, si la tienes te la quito)

> [!IMPORTANT]
>
> toggle
>
> Es una función que nos permite un token

FOREACH forEach

Es la misma forma de recorrer el buble el forEach. Es lo mismo la linea 411 que la 413 y 414

```JS
ddElements.forEach((item) =>{});

for (let i = 0; i < ddElements.length; i++) {
        const item = ddElements[i];
}
```

> [!IMPORTANT]
>
> forEach
>
> tu le das una función y el ya hace el bucle

### EVENTOS (ACCIÓN USUARIO) - SISTEMA OPERATIVO - NAVEGADOR

click, doble click, scroll, dentro de un formulario, que cambie el valor...etc

document.addEventListener('click', ())--> Registra un evento a un objeto en específico

```JS

document.querySelector ('button')

document.addEventListener('click', () => console.log('click'));

```

## 13/12/2024

¡¡¡IMPORTANTE REPASAR!!!

querySelector / querySelectorAll

innerHTML ??

event??

event.target ??

initialData??

callback??

addEventListener??

dataset--> todos los atributos data se guardan en dataset y desde el dataset cojo lo que quiera.

```JS
function handleButtonClick(event) {
        console.log('click', event);
        console.dir(event.target);
        const id = +event.target.dataset.id;
        console.log(id);

        if (id === 0) {
            simulateGame();
        } else {
            clearGame();
        }
}
```

```JS
    const board =['Posiciones en el tablero'] //Para guardar el tablero con 9 posiciones y una casilla de inicio con el texto posiciones
    for (let i = 1; i < 10; i++) { // Esto seria lo mismo que la linea de arriba.
        board[i] =''
    }
```

checkWinner:

- board.forEach--> Da vueltas al array y tu dentro haces lo que quieras. No devuelve nada, es void, te deja recorrer el array.
- board.map--> te devuelve algo Ej: const newArray. Esto es una proyeccion de un array. Por cada item que llegue, devuelveme item \* 2. Mapea
- board.filter-->

Las 3 funciones reciben un callback para hacer cosas. Las 3 funciones, te dan el item, i y array.

- FUNCIONES MUTABLES VS NO MUTABLES

sort: devuelve el array ordenado y muta el array original.

toSorted: devuelve el array ordenado sin modificar el original.

- FILTER y FIND

filter--> Sirve para filtrar y devuelve o true o indefined.

```JS
const names =['Pepe', 'Pedro', 'Ramon', 'Luis']

names.filter((item) =>{
    if[(item [0] === P')return true
})
```

find-->Buscador. Busca uno que coincida te devuelve un array y se va. Si tenemos 1000 nombres y buscamos un nombre que empiece por R, nos devolverá un array con el nombre de Ramon dentro.

Usa find cuando busques 1, usa filter cuando busques varios.

- FUNCIONES DE ARRAY

[].push(1)

myPush

PARA REPASAR

https://www.testgorilla.com/es/blog/preguntas-de-entrevista-sobre-front-end/

### FORMULARIOS JAVASCRIPT

```HTML
<section class ="players">
    <label>
        <span>User 1</span>
        <input type="text" id ="user1" placeholder="dime tu alias">
    </label>
    <label>
        <span>User 2</span>
        <input type="text" id ="user2" placeholder="dime tu alias">
    </label>
    <div>
        <button type>
    </div>
</section>
```

```JS


//registro de handler

const saveButtonElement = document.querySelector('.players button')
eButtonElement.addEventListener('click', handleSave());

//funcion

function handleSetUsers() {
    const inputElements = document.querySelectorAll('.players input');

    consoleg
}


```

## 16/12/2024

## JSON

JSON.parse()-->El JSON.parse()método estático analiza una cadena JSON y construye el valor o el objeto de JavaScript descrito por la cadena. Se puede proporcionar una función de recuperación opcional para realizar una transformación en el objeto resultante antes de que se devuelva.

JSON.stringify()--> El JSON.stringify()método estático convierte un valor de JavaScript en una cadena JSON, reemplazando opcionalmente los valores si se especifica una función de reemplazo u incluyendo opcionalmente solo las propiedades especificadas si se especifica una matriz de reemplazo.

### EVENT DE FORMULARIO EN UNA WEB

Foco, con tabulador, disparan un evento, hagas click o no y pierden el foco cuando cambias con el tabulador.

- bluur--> es perder el foco
- focus--> es para ganar el ganar foco

Ej: perder el foco cuando se pasa de uno a otro

- input--> Se dispara un evento input, cuando escribimos

- change--> Radio button o check box, desplegable. Siempre el evento que queremos escuchar es el evento change

### formData

Depende de los names, por cada name que encuentre guardalo en el formData. Lo guarda en un iterable.

```JS
const formData = new formData(form);
const playerData = Object.fromEntries(formData);
const player = {
    firstName: playerData['first-name'],
    surName: playerData['surname'],
    alias: playerData['nickname'],
    icon: playerData['icon'],
};

players.push(player);
```

### Validated (Validar)

tiene 2 funciones:

- setCustomValidity--> añade cadena de caracteres con error que tu quieras. Si se encuentra que se ha seteado un error te lo muestra. Si hay mensaje de error te lo enseño, sino hay error te dejo pasar.

- reportValidity--> te lo muestro en este momento. Ej mensaje: "Este alias ya esta en uso".

### Inspeccionar elementros --> Aplicacion --> Almacenamiento local

localStorage.setItem--> para guardar algo en local storage
localStorage.getItem--> para coger algo de local storage
localStorage.removeItem-->borrar
localStorage.clear-->borrar TODO

## 17/12/2024

/--> Posicion relativa al origen de la web

IMPORTANTE!!!

1. Arrancamos settings

ponemos:

"liveServer.settings.root": "./5JS/router" --> en settings se puede establecer la ruta de navegacion y definir el origen.

2. Entonces podemos trabajar con posicion relativa a origen con: /

Esto tiene beneficios como no tener que cambiar las rutas de la web ya que en index estara en un nivel y las otras paginas en otro. Esto nos servira para que el nav pueda ser el moismo en las diferentes paginas.

La otra manera de solucionarlo seria tener todos los HTMLs al mismo nivel.

### RUTAS

#### ESTRUCTURA DE CARPETAS

- Por tipos:

  - assets (img, video, audio)
  - html
  - css / styles
  - js / scripts

- Por Característica (features):
  - inicio
  - about
  - portfolio

Es buena idea trabajar siempre en la carpeta del proyecto.

#### CREAR TODOS LOS SCRIPTS DEL HTML POR MODULE

Crearemos el main.js importando el resto de js con import y exportandolos en sus correspondientes js.
Ej: en carpeta de router

https://-->Protocolo
www.github.com-->Host
443-->Puerto

> [!IMPORTANT]
>
> at(-1)
>
> ultimo elemento del array--> es lo mismo que [], la ventaja de at es que permite números negativos.

```JS
at(-1)
```

#### COMPONENTES

Todos los freamworks modernos han ido hacia los componentes.Es decir, cuando construimos una web, no vamops a estar repitiendo los menus en 50 paginas, utilizaremos componentes.
react, vue,...etc

INTALAMOS EL PLUGIN es6-string-html-->

> [!IMPORTANT]
>
> insertAdjacentHTML
>
> AÑADE, NO QUITA NADA. Recordamos que sirve para añadir HTML adyacente.

La función hace y coloca lo que tiene que colocar en su sitio, eso es un componente.

Le pasamos la responsabilidad al propio componente, la pagina de header.js seria un componente.

#### PROPIEDADES EN EL OBJETO

Estas propiedades son de target:

- target.nextElementSibling()
- target.lastElementChild()
- target.firstElementChild()
- target.previousElementSibling()

## 18/12/2024

COMANDOS:

- npm list -g: listame los programas/ plugin que tenemos listados a nivel global.
- sudo: superusuario.
- live-server --port= 4444: para que nos abra el puerto 4444 en live server.
- live-server --help: ayúdame y dame lista de comandos.
- configurar la extension si no queremos usar live server, entonces ESCRIBIMOS EN SETTINGS. Se crea ABRIENDO ENGRANAJE--> configuración--> CAMBIAS CUALQUIER COSA, cierras y luego lo vuelves a poner en su sitio.

- code -help: para que nos liste los comandos que tiene code.

### Gestion de Datos

C-reate
R-ead
U-pdate
D-elete

Vamos a crear una lista de tareas, donde vamos añadir tareas nuevas, leerlas, actualizarlas, boprrarlas...que hacemos? un CRUD. Cualquier Web que maneje datos lleva CRUD.

CRUD de Tareas o TODO.

Lo siguiente que tenemos que tener en cuenta cuando trabajamos con datos es lo que se conoce como EL MODELO DE LOS DATOS o ENTIDADES. hacer un CRUD de algo es una ENTIDAD. La entidad es algo real. Cuando tenemos "COSAS" tienen que tener un identificador id

```js

tenemos que tener muy claro que al otro lado del igual tendremos un OBJETO

EJ. de CRUD

type Task = {
    id: string,
    title: string,
    owner: string
    isDone: boolean
}

```

> [!IMPORTANT]
>
> UUID
>
> identificador universal ÚNICO. chorro de 128 bits en hexadecimal que identifica de forma única y universal cualquier cosa. Nos podemos quedar con el primer trozo

> [!IMPORTANT]
>
> crypto
>
> tiene un metodo con un randomUUID, que nos genera un UUID
>
> Para generar un randomUUID en javascript
> console.log(crypto.randomUUID());

> [!IMPORTANT]
>
> MOOC
>
> Conjunto de datos moqueados

```JS

PAGE = TRUE && FALSE // (SIGUE SI EL ANTERIOR ES TRUE). NO ES UN BOOLEAN, si lo primero es igual deja pasar.

true && true // true
true && false //false
false && true //false
false && false //false

PAGE = TRUE || FALSE // (SIGUE SI EL ANTERIOR ES FALSE)

true || true // true
true || false //true
false || true //true
false || false //false

PAGE = FALSE ?? FALSE // Nullish (SIGUE SI EL ANTERIOR ES NULLISH)

```

> [!IMPORTANT]
>
> Tipos de javascripts son 8
>
> falsey de javascript son 8:
> 2 nulish --> null / undifined
> otros 6 falsies --> 0, -0, 0n, '', NaN, false

### SERVICES

No tienen nada que ver con el inteface de usuario

```js
function getTaskFromBackend() {}
```

### COMPONENTES

La idea de los componentes es crear "partes" de las paginas web. Elementos o funcionalidades que la componen como, por ejemplo, las secciones o menús, que hacen que se pueda navegar por ella y sea funcional.

> [!IMPORTANT]
>
> Render
>
> Pinta en la pantalla, es como un console.log, pero pinta en pantalla, no en consola. Lo más importante es que render es una función que podemos usar para definir el código HTML dentro del elemento HTML.

## 19/12/2024

REPASO
Carpeta componentes--> Task-cards (es el que "gestiona el negocio")-->funcion de borrado, vive en el entorno de negocio pero la pasamos a card que es donde se ejecuta.

-----

### Trabajamos en el archivo add-task.js

event.preventDefault()--> En un formulario cuando queremos que valide tenemos que poner preventDefault y luego programarlo.

```js
const formData = new FormData(event, target);
const data = object.fromEntries(formData);

const newTask = {
  id: '',
  title: data.title,
  owner: data.owner,
  isDone: false,
};
```
Las lineas 806 y 807 nos soluciona muchos problemas de formularios.


REPASAR COMPONENTES y HACER COMPONENTES CON JAVASCRIPTS DESDE 0

### Check-box de las tarjetas

Queremos que cambie de false a True. Hay que escuchar al checkbox en cada tarjeta.

En las tarjetas cards.js vamos a hacer un addEventListener.

```js
const check = element.querySelector('input');

check.addEventListener('change',() => {
  task;
})
```

eso no nos cambiara el valor interno, es decir, nos cambiara la primera vez de false a true, pero si volvemos a hacer check nos seguira diciendo true.

```js
const check = element.querySelector('input');

check.addEventListener('change',() => {
  task.isDone = !task.isDone;
})
``` 
Con la linea 841 conseguiremos que si hacemos check se marque a true, si desclicamos marque internamente en consola false.


Ahora pasamos al padre (task-cards.js), que haga esto en el padre.

CLONAR OBJETOS. Sirve para clonar objetos y no tocar el original.

const task = {...task}

### CODIGO BLOQUEANTE Y COMO GESTIONA JAVASCRIPT EL CODIGO


Es codigo que bloquea por un tiempo X el procesador, si eso pasa en un servidor, es algo TERRIBLE.

-Javascript es monohilo--> malo para hacer codigo que requiera mucho procesamiento.

-Python es multihilo-->bueno, ya que se pùede trabajar en otros hilos.

Servidores Web que no usan NODE:

- Por concurrencia: Ej camarero que atiende de manera distinta con distintas tareas a diferentes personas.

- Sin concurrencia: Ej Bar, camarero, cocina (se queda esperando hasta que te terminan de atender y luego pasa al siguiente cliente).

#### PROCESOS ASINCRONOS

----SETTIMEOUT----
setTimeout--> espera 1 segundo pero mientras haz otras tareas.

Ej: 

Tarea 1
Tarea 2
setTimeout(1seg) Tarea 3
Tarea 4

Esto daria un resultado de el camarero hace la tarea 1, la 2, la 4 y la 3 porque mientras espera a la 3 ha hecho la 4.

  - asincrono - diferido
  - asincrono - inmediato

promise--> es como serTimeout, pero va prioridad, lo saca antes de otras tareas.

Mecanismo para solucionar el problema de asincronia fue makeAsync, dale un callback y que haga lo que tiene que hacer.
```js
const time = 1000;
makeAsync(time, (n) =>{ // cuando pase este tiempo, ejecuta esta funcion
  console.log(n);
})

makeAsync(time, handleTime); // esto es lo mismo que la linea 889
```

desestructurizacion --> normalmente los objetos estan en el lado derecho, en la desustructurizacion se declara a la izquierda todo junto.


----PROMESAS----

Las promesas son objetos, Ej. es un ticket que te dan para recoger una hamburgesa. Pueden decirte que no hay carne o que te la den. Executor -->fullfile (se resuelve en sentido positivo) reject ( se revuelve en sentido negativo). 

metodo .then() lo que "yo me como la hamburguesa", lo que tu harias si te llega el dato.

.catch(data)-->lo que yo haria si me llega el error. se le suele llamar (data)
.finally(error)-->lo que yo haria en cualquier caso. se le suele llamar (error)

La promesas se poueden tratar en paralelo. Quiero ejecutar varios procesos asincronos en paralelos.

Funciones:

- allSettled. Quiero todos los datos de usarios
- all
- race. Me quedo con la primera que llegue
- any. 

IMPORTANTE!! REPASAR PROMESAS CALLBACK

----ASYNC----

Convierte cualquier funcion en asincrona, es una promesa.

----ASYNC-AWAIT----

IIFE--> funcion anonima inmediatamente autoinvocada


INSTALAR JSON VIEWER

ir a la pagina https://dummyjson.com/ para montar una pagina de recetas, por ejemplo.