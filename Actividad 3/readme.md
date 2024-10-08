## Git config

Me permite visualizar la configuración actual de mi dispositivo

![alt text](image.png)

## Git init

Este comando me permite crea la carpeta .git la cual me permitirá tener un registro de versiones en mi rama local


- Creación de carpetas 

![alt text](image-1.png)

## Git add 

Este comando sirve para registrar que archivos queremos guardar sus cambios. Como si de un historial de ese archivo se tratara. 

Si creara un archivo y no le diera a git add <nombre> esto pasaría

![alt text](image-2.png)

## Git status

Este comando nos ayuda a revisar el estado de nuestros cambios en nuestras carpetas y que archivos no están siendo rastreados

![alt text](image-3.png)

## Git commit

Este comando permite que los archivos rastreados se guarden en el historial con el nombre especifico de este commit, como si de un punto de guardado se tratara

![alt text](image-4.png)

## Fases

Existen fases de trabajo en el uso de git

- Flujo de edición: Aquí se dan los cambios, edición, etc. En los que los archivos pueden sufrir distintas modificaciones

- Preparación: Aquí se indican que archivos queremos rastrear para su posterior registro con un commit

- Commit: Estos cambios son registrados con un hash, luego de todo el proceso anterior. Para su posterior publicación

## git log

Es te comando nos permite conocer el historial de commits, con el nombre que le dimos cada vez que hacíamos git commit

![alt text](image-5.png)

Nos muestra diferentes elementos, por ejemplo:

- Identificador SHA

- Detalles: Nombre y email de la persona

-  Marca de tiempo


Tambien tiene modificadores 

-p : nos muestra el cambio nuevo en cada commit

--stat : nos abrevia algunas estadistica

--oneline: Minimiza la salida de información

--graph: Muestra la salida tipo un arbol con ramas

 --author <author>: Filtra los commits hechos por el author indicado

### Pregunta

$ git log --graph --pretty=format:'%x09 %h %ar ("%an") %s'
Pregunta: ¿ Cual es la salida de este comando? 

![alt text](image-6.png)

## Trabajar con branches

- git branch : me muestra muemuestra las ramas que tengo

![alt text](image-7.png)

- git branch feature/new-feature : me permite crear una nueva rama con copia de el working tree actual

- git checkout/git switch : Este comando me permite mover el HEAD hacia otro commit y así el working tree se cambian a los registrados en ese commit del HEAD 

- git merge: Este comando permite fusionar dos ramas así podemos traer trabajo hecho en otra rama y si hay conflictos elegir que permanece

## Ejercicios

### 1


 $ git branch feature/advanced-feature

 $ git checkout feature/advanced-feature


![alt text](image-8.png)

### 2

Modificar archivos en la nueva rama:
 - Edita el archivo main.py para incluir una función adicional:
 python
 def greet():
 print('Hello from advanced feature')

 greet()

 - Añade y confirma estos cambios en la rama feature/advanced-feature:

 $ git add main.py

 $ git commit -m "Add greet function in advanced feature"

 ![alt text](image-9.png)

 ### 3

  Simular un desarrollo paralelo en la rama main:
 - Cambia de nuevo a la rama main:

 $ git checkout main

 - Edita el archivo main.py de forma diferente (por ejemplo, cambia el mensaje del print original):
 python
 print('Hello World - updated in main')

 - Añade y confirma estos cambios en la rama main:

 $ git add main.py

 $ git commit -m "Update main.py message in main branch"

![alt text](image-10.png)

### 4

Intentar fusionar la rama feature/advanced-feature en main:
 - Fusiona la rama feature/advanced-feature en main:

 $ git merge feature/advanced-feature


 ![alt text](image-11.png)


### 5 

Resolver el conflicto de fusión:
 - Git generará un conflicto en main.py. Abre el archivo y resuelve el conflicto manualmente,
eligiendo cómo combinar las dos versiones.
 - Después de resolver el conflicto, añade el archivo resuelto y completa la fusión:

 $ git add main.py

 $ git commit -m "Resolve merge conflict between main and feature/advanced-feature"

 ![alt text](image-12.png)


 ### 6

 Eliminar la rama fusionada:
 - Una vez que hayas fusionado con éxito y resuelto los conflictos, elimina la rama
feature/advanced-feature:

 $ git branch -d feature/advanced-feature

 ![alt text](image-13.png)

 