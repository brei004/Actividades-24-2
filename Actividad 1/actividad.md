## 1. Configuración del entorno

Se busca la creación de una web sencilla, con una api rest básica

- Inicializamos el proyecto de node

![alt text](image/image.png)

![alt text](image/image-1.png)

con esto ya tenemos la base del proyecto de node

- Dependencias

Necesitamos la dependencia de express y jest para la creación de la api y pruebas respectivamente

![alt text](image/image-3.png)

![alt text](image/image-2.png)

- Carpetas del proyecto

Creamos la carpeta y subcarpetas para la actividad

 ```javascript
 mkdir src tests
```

![alt text](image/image-4.png)

```javascript
touch src/app.js tests/app.test.js
```

- Implementación de la API REST

```javascript
 src/app.js
```
![alt text](image.png)


- Test Básico en js

```javascript
 tests/test.js
```
![alt text](image-2.png)

- Configuración de package.json

La configuración de este archivo define palabras clave que resuman acciones por ejemplo. Puedo correr el test mediante 

```javascript
 npx jest test.js  o
 npm test
```
![alt text](image-4.png)

Resultado 

![alt text](image-3.png)

## 2. Pipeline CI/CD

### Parte 1 Configuración integración continua
- Estructura de proyecto 

![alt text](image-5.png)


- Archivo ci.yml



![alt text](image-7.png)

- Código a github

![alt text](image-6.png)

Ejecución en github 
![alt text](image-14.png)

Hubo un problema, ya que el servidor seguía en ejecución y no terminaba. Lo que no permitía finalizar la integración

### Parte 2 Configuración entrega continua
- Creación de dockerfile

Necesitamos un Dockerfile para definir como se construirá la imagen Docker. Por ejemplo, el entorno donde trabajará y qué acciones realizará 

![alt text](image-8.png)

- Construcción de imagen docker

```javascript
docker build -t devops-practice
```


- Ejecución del imagen en contenedor

![alt text](image/image-9.png)

- Automatización con github actions

En este archivo definimos las acciones que se están ejecutando en nuestro proyecto, tenemos que agregar la imagen y el contenedor recien creados

![alt text](image-11.png)

- Ejecución local 

![alt text](image-9.png)

- Automatización 

Usamos docker compose ya que facilita la creación de pruebas simulando el entorno local de ejecución

![alt text](image-12.png)

![alt text](image-13.png)