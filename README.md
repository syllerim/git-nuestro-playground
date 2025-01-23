# Práctica Git & GitHub

Información de contacto del profesor:

Alberto Casero
kas.appeal@gmail.com

Author: Mirellys Arteta Davila

## Ejercicio 1
Se deberá crear un repositorio y realizar una serie de operaciones **desde la consola de
comandos** sobre el mismo para posteriormente subir el repositorio a Github.

Se deberá entregar a través del formulario de prácticas indicando la URL del repositorio. En el
repositorio, deberá existir un archivo readme.md con las respuestas a las siguientes preguntas:

**- ¿Qué comando utilizaste en el paso 11? ¿Por qué?**

```
git reset --hard HEAD~1
```
Porque necesitaba destruir el último commit, de tal modo que el history se quede en el primer commit de la branch styled.


**- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?**

```
git reflog
git reset --hard HEAD@{1}
git log --oneline
```
`git log` no es suficiente para mirar el historial de cambios ejecutados en HEAD, así que es necesario mirarlo con `reflog`, y una vez identificada la referencia de HEAD que apunta al commit deshecho, es cuestión de ejecutar `git reset --hard` junto con dicha referencia. Por último es necesario verificar el historial restaurado.

**- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?**

```
git merge main
```
No hubo conflictos, porque no han habido cambios en `main` después de haber creado la rama `styled`, que fue creada a partir de `main`.

**- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?**

```
git merge htmlify

```

Sí hubo conflictos, porque al crear la rama `htmlfy` a partir de `main` y hacerle cambios, cuando se intenta merger en `styled` git detecta que las ramas divergen desde cierto punto (el primer commit en el fichero `git-nuestro` en `main`), y no puede decidir automaticamente como resolver con qué cambios quedarse.


**- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?**

```
git merge styled
```
No hubo conflictos, porque no han habido cambios en `main` después de haber resuelto los conflictos entre `styled` y `htmlfy` en `styled.

**- ¿Qué comando o comandos utilizaste en el paso 25?**

```
git log --graph --decorate --pretty=oneline --abbrev-commit
```

**- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?**

```
git merge title --no-ff
```
Sî podría haberse ejecutado porque `main` es nodo `ancestro` de title. La única diferencia es que no hubiese habido un commit específico para dicho merge y el puntero a la branch `title` hubiese sido el mismo que `main`.

**- ¿Qué comando o comandos utilizaste en el paso 27?**

```
git reset HEAD~1
```

**- ¿Qué comando o comandos utilizaste en el paso 28?**

```
git checkout -- git-nuestro.md
```

También pude haber ejecutado:

```
git checkout .
```

**- ¿Qué comando o comandos utilizaste en el paso 29?**

```
git branch -D title
```

**- ¿Qué comando o comandos utilizaste en el paso 30?**

```
git reflog
git reset --hard HEAD@{1}
```

También pude haber ejecutado:

```
git reflog
git reset --hard b5bd66d
```
Siendo `b5bd66d` el SHA del commit con el merge.

**- ¿Qué comando o comandos usaste en el paso 32?**

```
git reflog
git reset --hard HEAD@{25}
```

También pude haber ejecutado:

```
git reflog
git reset --hard 5ab7d06
```

**- ¿Qué comando o comandos usaste en el punto 33?**


```
git reflog
git reset --hard b5bd66d
```

También pude haber ejecutado:

```
git reflog
git reset --hard
```
