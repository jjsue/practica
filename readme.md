- ¿Qué comando utilizaste en el paso 11? ¿Por qué?
 
git reset --hard head~1
Se usa ese comando ya que queremos volver solo un paso atrás y además tenemos el --hard que nos deshace los cambios en el working copy.

- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

Primero git reflog para ver el nombre del commit que acababa de deshacer, luego copie el sha e introduje: git reset --hard bb24c8b lo hago de esta forma para que mi working copy vuelva a ser la que tenía en ese commit.

- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?

Uso el comando git merge master el cual no me produce ningún conflicto, de hecho me dice que ya está “mergeado”, pongo la salida completa:
$ git merge master
Already up to date.
No podemos hacer merge ya que master no tiene nada que podamos añadir a styled

- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?

Si, ha causado conflictos, lo que nos ha ocurrido es que en los archivos de ambas ramas había líneas diferentes (Entiéndase que las líneas que eran diferentes estaban en el mismo número de línea, es decir, que si la línea 10 de un archivo y otro son diferentes ahí se nos genera un conflicto, eso es lo que ha ocurrido).

Lo que tenemos que pasar a borrar son las lineas que se marcan bajo los simbolos de igualdad ======== y así hasta que encontramos >>>>>>>htmlify que lo que nos indica es que es el fin del conflicto con la rama de htmlify.

- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

No causa ningún conflicto ya que solo tiene que hacer fast-forward para actualizarse.

- ¿Qué comando o comandos utilizaste en el paso 25?

git log --graph --decorate
No añado el pretty-oneline ya que prefiero moverme con vi y verlo un poco más grande.

- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

Si, ya que había un camino directo desde master hasta title y podríamos simplemente haber movido el puntero de máster hacia title.

- ¿Qué comando o comandos utilizaste en el paso 27?

git reset HEAD~1 
Para más seguridad podría haber cogido directamente el sha del reflog y usarlo en lugar del HEAD~1

- ¿Qué comando o comandos utilizaste en el paso 28?

git restore git-nuestro.md

- ¿Qué comando o comandos utilizaste en el paso 29?

git branch -D title

- ¿Qué comando o comandos utilizaste en el paso 30?

git reflog para encontrar el sha del merge que hemos deshecho.
Tras encontrarlo, escribimos:
git reset --hard 01e4e82

- ¿Qué comando o comandos usaste en el paso 32?

git log para ver cual es el primer commit y copiar el sha.
Una vez con el sha localizado escribimos:
git reset --hard 2957c5aa290306e10e02fcaaf2bf2a4786683787

- ¿Qué comando o comandos usaste en el punto 33?

Utilizamos git reflog para ver el sha del que venimos, una vez visto usamos el comando:
git reset --hard 01e4e82
