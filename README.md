# Dafiti

# Supone que en un repositorio GIT hiciste un commit y te olvidaste un archivo. Explicar como se soluciona si hiciste push, y como si aun no hiciste. De ser posible, buscar que quede solo un commit con los cambios.
-Para cambiar el commit lo que se debe hacer es configurar el amend y luego usar el siguiente comando
amend se debe configurar en la configuracion global de git con (git -g config)

git add . (Se agrega el nuevo archivo)
git commit --amend

-Si el archivo no a sido pujado.

git push origin head

Si el archivo ya fue empujado.

git push -f origin Head

# Tenes un sitio en tu computadora de desarrollo, y cuando entras desde el navegador, en la consola te aparece esto
https://site.local/favicon.ico Failed to load resource: net::ERR_INSECURE_RESPONSE

Normalmente este tipo de error se identifica por que el certificado SSL no esta autenticado o no se trae, ademas de que puede ser posible que la cabecera tampoco traiga
la información correcta. (Realmente investigué por que desconocia la razón de este error)

# Tenes un archivo comiteado en un repositorio GIT que deseas que quede ignorado. Que pasos debes realizar?
Para este caso hay que crear un archivo .gitignore dentro de ese archivo indicar el archivo que deaseamos ignorar y luego con un

git add .gitignore

# Explica las ventajas de cargar en tu sitio las librerias de terceros por GTM

GTM permite cargar en tu sitio las librerias de terceros, por ejemplo, para que puedas usar el plugin de google maps.
ademas de que permite cargar de una manera asincrona y asi no tener que esperar a que se cargue la libreria y detener otros modulos.
