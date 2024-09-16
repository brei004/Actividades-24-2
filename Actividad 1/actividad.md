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

- Estructura de proyecto 

![alt text](image-5.png)