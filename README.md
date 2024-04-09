# Random Quote Machine
# 
Este es un proyecto de la plataforma **FreeCodeCamp** del curso **Front-End Development Libraries** para la certificación del programa.


------------

**Objetivo**: Construir una aplicación que sea funcionalmente similar a esta: https://random-quote-machine.freecodecamp.rocks/.

**Requisitos**: Los requisitos para construir la apliación se pueden encontrar en:
https://www.freecodecamp.org/learn/front-end-development-libraries/front-end-development-libraries-projects/build-a-random-quote-machine

-------------
###Funcionamiento
Este código implementa una aplicación simple para mostrar citas aleatorias en una página web. <br>

Define una interfaz llamada Quote que especifica la estructura de una cita, que consta de dos propiedades: `quote` para el contenido de la cita y `author` para el autor de la cita

```javascript
 interface Quote{
  quote:string;
  author:string;
}
```

Esta función devuelve una cita aleatoria seleccionada de un array llamado quotes. Utiliza `Math.floor(Math.random() * quotes.length)` para generar un índice aleatorio y seleccionar una cita aleatoria del array.
```javascript
const getRandomQuote = (): Quote =>{
  return quotes[Math.floor(Math.random() * quotes.length)];
}
```

Esta función genera un color aleatorio en formato RGB. Genera valores aleatorios para los componentes rojo (red), azul (blue) y verde (green) y luego los concatena en una cadena en formato de color RGB..
```javascript
const getRandomColor = (): string =>{
 	const red= Math.floor(Math.random()*128);
 	const blue= Math.floor(Math.random()*128);
 	const green= Math.floor(Math.random()*128);
 	return `rgb(${red}, ${blue},${green})`;
}
```
<br>

`quote` almacena la cita actualmente mostrada en la aplicación. Se inicializa con una cita aleatoria obtenida mediante la función getRandomQuote.
`randomColor`almacena el color de fondo actual de la aplicación. Se inicializa con un color aleatorio obtenido mediante la función getRandomColor.
Función de Cambio de Cita (changeQuote):

Esta función se ejecuta cuando se activa un evento (por ejemplo, hacer clic en un botón) para cambiar la cita mostrada. Actualiza el estado de quote llamando a setQuote con una nueva cita aleatoria obtenida mediante la función getRandomQuote. Además, actualiza el estado de randomColor llamando a setRandomColor con un nuevo color aleatorio obtenido mediante la función getRandomColor.
```javascript
Function App() {
  const [quote, setQuote] = useState<Quote>(getRandomQuote());

  const [randomColor, setRandomColor] = useState<string>(getRandomColor());

  const changeQuote = () => {
    setQuote(getRandomQuote());
    setRandomColor(getRandomColor())
  }
```
