## Ejercicios

### Clona un repositorio Git con múltiples ramas y fusiona ramas usando git merge --ff

El uso de git merge --ff es decir fast forward, no se recomienda cuando se quiera tener el historial más detallado de las caracteristicas. Porque aplana directamente la rama con los cambios del otro y es dificil de revertir

### Simula un flujo de trabajo de equipo utilizando git merge --no-ff

Pregunta: ¿Cuáles son las principales ventajas de utilizar --no-ff en un proyecto en equipo?

- Claridad en el historial: podemos mantener el contexto de cuándo se desarrollaron y fusionaron las características.
- Facilidad de revertir: se puede revertir un merge completo si algo sale mal, lo que no es tan sencillo con fast-forward.
- Separación de responsabilidades: se puede identificar fácilmente el trabajo realizado en cada rama.
### Fusiona una rama utilizando git merge --squash

- Historial más limpio: Agrupa múltiples commits pequeños en uno solo, lo que es ideal para proyectos grandes donde no necesitas preservar todos los pasos intermedios.

- Mayor simplicidad: Hace que el historial de commits sea más fácil de leer y gestionar.

### Resolver conflictos en una fusión non-fast-forward

```Javascript
Git detectará un conflicto en index.html. Abre el archivo y resuelve el conflicto. Elimina las líneas de
conflicto generadas por Git (<<<<<<<, =======, >>>>>>>) y crea la versión final del archivo con ambos
cambios:
 <html>
 <body>
 <h1>....</h1>
 <p>....</p>
 <footer>...example@example.com</footer>
 </body>
 </html>
 ```

 Esto permite diferenciar entre los cambios entrantes y los actuales de nuestra rama

 Preguntas:
− ¿Qué pasos adicionales tuviste que tomar para resolver el conflicto?
 Encontrar que información si necesitaba de cada rama
− ¿Qué estrategias podrías emplear para evitar conflictos en futuros desarrollos colaborativos?
 Asignar a cada usuario qué archivos editaran para evitar conflictos de merge

 ### Comparar los historiales con git log después de diferentes fusiones

 Para el último ejercicio se requiere ver el efecto de usar los 3 tipos de merge

 ```Javascript
 Primera rama
git checkout -b feature-1
echo "Característica 1 agregada" >> version.txt
git add version.txt
git commit -m "Agregar característica 1"
```

```Javascript
git checkout main
git checkout -b feature-2
echo "Característica 2 agregada" >> version.txt
git add version.txt
git commit -m "Agregar característica 2"
```

```
git log --graph --oneline --merges
```

Con este comando solo veremos los commits que usaron merge en su creación

```
git log --graph --oneline --merges --first-parent --branches
```

Esto mostrará un historial donde la rama main se movió hacia adelante sin un commit de fusión visible, ya que el fast-forward aplana la historia

```
git log --graph --oneline --merges --decorate --all
```
Este historial mostrará que los múltiples commits de feature-3 fueron comprimidos en un solo commit, limpiando el historial de cambios intermedios y haciendo que parezca como si solo hubiera habido un commit para toda la característica

```
* 3a6f2a8 Merge commit for feature-2
| * 5b3e2b4 Feature-2 commit
* 8c6a9c7 Feature-1 commit (fast-forward)
* 1234abc Commit inicial
```


```
*   3a6f2a8 Merge branch 'feature-2' (non-fast-forward)
|\
| * 5b3e2b4 Feature-2 commit
* | 8c6a9c7 Feature-1 commit (fast-forward)
* 1234abc Commit inicial
```

```
* 4f6e9d8 Agregar característica 3 en un commit (squash)
*   3a6f2a8 Merge branch 'feature-2' (non-fast-forward)
|\
| * 5b3e2b4 Feature-2 commit
* | 8c6a9c7 Feature-1 commit (fast-forward)
* 1234abc Commit inicial
```

Estos historiales describen justo lo esperado.

- Fast Forward: es lineal y no hay commit de fusión
- Non fast forward: es más detallado y tiene commit de fusión
- Squash : evita mostrar los cambios pequeños, comprimiendolo solo en un commmit
