# Dafiti

# Supone que en un repositorio GIT hiciste un commit y te olvidaste un archivo. Explicar como se soluciona si hiciste push, y como si aun no hiciste. De ser posible, buscar que quede solo un commit con los cambios.
>Para cambiar el commit lo que se debe hacer es configurar el amend y luego usar el siguiente comando
amend se debe configurar en la configuracion global de git con (git -g config)
(Se agrega el nuevo archivo)
```
git add . 
```
>Se edita el commit
```
git commit --amend
```
>Si el archivo no a sido pujado.
```
git push origin head
```
>Si el archivo ya fue empujado.
```
git push -f origin Head
```
# Tenes un sitio en tu computadora de desarrollo, y cuando entras desde el navegador, en la consola te aparece esto
```
https://site.local/favicon.ico Failed to load resource: net::ERR_INSECURE_RESPONSE
```
>Normalmente este tipo de error se identifica por que el certificado SSL no esta autenticado o no se trae, ademas de que puede ser posible que la cabecera tampoco traiga
la información correcta. (Realmente investigué por que desconocia la razón de este error)

# Tenes un archivo comiteado en un repositorio GIT que deseas que quede ignorado. Que pasos debes realizar?
>Para este caso hay que crear un archivo .gitignore dentro de ese archivo indicar el archivo que deaseamos ignorar y luego con un
```
git add .gitignore
```
# Explica las ventajas de cargar en tu sitio las librerias de terceros por GTM

>GTM permite cargar en tu sitio las librerias de terceros, por ejemplo, para que puedas usar el plugin de google maps.
ademas de que permite cargar de una manera asincrona y asi no tener que esperar a que se cargue la libreria y detener otros modulos.

# Escribir una funcion que determine si un conjunto de cartas de una lista representan una escalera de poker (5 cartas con valores consecutivos) o no.
```javascript
console.clear();
//funcion isStraight
const isStraight = (cartas) => {
   let resultado = false;
   //Tranformo la carta 14 en 1 para poder ordenarla
   const tipoCartas = cartas.map((item) => (item === 14 ? 1 : item));
   //Ordeno las cartas
   const ordenado = tipoCartas.sort((a, b) => a - b);
   // ciclo que valida si son consecutivos
   if (cartas.length < 8) {
      for (let i = 0; i < ordenado.length; i++) {
         if (ordenado[i] < ordenado[i + 1]) {
            resultado = true;
         } else if (ordenado[i] === ordenado[ordenado.length - 1]) {
            resultado = true;
         } else {
            resultado = false;
            break;
         }
      }
   } else {
      resultado = false;
   }
    console.log(resultado);
}

isStraight([2, 3, 4, 5, 6]);
isStraight([14, 5, 4, 2, 3]);
isStraight([7, 7, 12, 11, 3, 4, 14]);
isStraight([7, 3, 2]);

```

# Cual es el jugador mas viejo
```
SELECT equipos.nombre, jugadores.nombre, jugadores.fecha_nacimiento
FROM jugadores INNER JOIN equipos ON equipos.id_equipos = jugadores.fk_equipos 
GROUP BY jugadores.nombre ORDER BY jugadores.fecha_nacimiento ASC;
```
# Cuantos partidos jugo de visitante cada equipo 
```
SELECT equipos.nombre, COUNT(partidos.fk_equipos_visitante) AS CantidadPartidos 
FROM equipos INNER JOIN partidos ON equipos.id_equipos = partidos.fk_equipos_visitante GROUP BY equipos.id_equipos;
```
# Que equipos jugaron el 01/01/2016 y el 12/02/2016
```
SELECT equipos.nombre FROM equipos WHERE equipos.id_equipos IN 
(SELECT partidos.id_equipos_local FROM partidos WHERE partidos.fecha = '2016-01-01' OR partidos.fecha = '2016-02-12')
```
# Total de goles que hizo el equipo Chacarita
```
SELECT * FROM partidos INNER JOIN equipos ON equipos.id_equipos = partidos.fk_equipos_local WHERE equipos.nombre = 'Chacarita' 
UNION ALL (SELECT * FROM partidos INNER JOIN equipos ON equipos.id_equipos = partidos.fk_equipos_visitante WHERE equipos.nombre = 'Chacarita');
```
# Contanos en pocas lineas cual crees que es la mayor innovacion en el mundo del desarrollo en los ultimos 5 años, y por que
>En la actualidad hay algo que me sorprendió y de hecho tuvo algo de furor en el momento cuando fue mencionada por la comunidad del desarrollo, es (CoPilot) sinceramente había muchas personas asépticas otras que lo aclamaban como el fin de los programadores, pero solo aquellos que probamos la beta e incluso su preview entendemos que realmente no es el “el fin de los programadores” definitivamente hay que tener un conocimiento claro del desarrollo para poder usarlo. Y definitivamente este lejos de ser el remplazo de un programador solo es un copiloto que te ayuda en ocasiones a terminar códigos simples de una manera más rápido y limpia, ayudando y mejorando al desarrollador; creo este es un gran avance y bueno para todos aquellos que programamos.
