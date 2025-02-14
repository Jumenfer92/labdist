# Tarea 2  Control de versiones

## DAW Distancia - Despliegue de Aplicaciones Web

### Juan Méndez Fernández - 14 - 02 -2025



___



[TOC]



___



## 1. Objetivo de la tarea

Se trata de adquirir habilidades en el manejo de Git como sistema de control de versiones. Con estos ejercicios se practica tanto el trabajo en entornos locales como en entornos remotos, tanto por consola de comandos como gráficamente con SourceTree en este caso. También sirve para practicar el cambio de ramas y la resolución de conflictos.



___



## 2. Metodología práctica

Esta entrega se divide en dos secciones principales. En la primera se llevan a cabo operaciones con lo fundamental en un repositorio local de Git, desde la creación e inicialización del repositorio, pasando por la creación de las ramas, hasta la ejecución del commit, además de la resolución de conflictos y la carga de ficheros en el repositorio. El formato de entrega es un PDF redactado previamente en Markdown mediante Typora. Se incluye finalmente un videoclip que resume el desarrollo de la tarea.



____



## 3. Cuestiones Parte Local

Utilizando GitBash, mediante el siguiente comando establezco que el historial de ramas de Git se lleve a cabo en forma de árbol:

```bash
$ git config --global merge.ff false
```

![image-20250214194553476](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214194553476.png)



### Cuestión 1

Inicializo un nuevo repositorio Git en una carpeta llamada `labdist` y agrego los archivos proporcionados en el aula virtual. Renombro la rama master a `main` si es necesario. Realizo el primer commit y muestro el log del repositorio.



``````
git init
git branch -m master main
git status
git add .
git commit -m "Inicio. Renombrar master a main y agregados archivos del aula."
git log
``````



![image-20250214195802949](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214195802949.png)



### Cuestión 2

Incluyo un fichero `.gitignore` para que los ficheros `README.md`, `LICENCE.TXT` y `passwords.txt`  sean ignorados por el control de versiones. Realizo el commit y muestro los logs del repositorio en una línea.

``````
vim .gitignore (editor vim)
:wq! para salir de vim guardando los cambios
git add .
git commit -m "Creo el fichero .gitignore e incluyo en el la lista a ignorar"
git log --oneline
``````

![image-20250214200300015](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214200300015.png)

![image-20250214200332187](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214200332187.png)

![image-20250214200803524](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214200803524.png)



### Cuestión 3

En el repositorio, creo los archivos `README.md`, `LICENCE.txt` y `passwords.txt`  con algún contenido. Muestro el estado del repositorio. Muestro el listado de archivos ignorados.

![image-20250214202202664](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214202202664.png)

![image-20250214202239562](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214202239562.png)

Inciso: Renombro la errata de README.txt a README.md y muestro los listados y contenidos.

``````
git status
git status --ignored
``````



![image-20250214202515478](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214202515478.png)



### Cuestión 4

Creo una rama `feature-estilos` y me cambio a ella.

![image-20250214203240619](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214203240619.png)

Modifico el archivo `estilos.css`: (editor `vim`)

![image-20250214203307857](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214203307857.png)

- Propiedad color del `body` y de `h2` : `#2a2a2a`

![image-20250214203716280](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214203716280.png)

![image-20250214203745440](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214203745440.png)

- Propiedad `background-color` de `header` y `footer` : `#2a75ff`

![image-20250214203839185](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214203839185.png)

Compruebo el estado del repositorio. Añado los cambios, realizo un commit con el mensaje "actualizados estilos a azules".

![image-20250214204015325](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214204015325.png)

``````
git branch feature-estilos
git checkout feature-estilos
git status
git add .
git commit -m "actualizados estilos a azules"
``````





### Cuestión 5

Vuelvo a la rama `main`. En el archivo `index.html` añado un comentario donde se indica mi nombre como autor de la página. Compruebo el estado del repositorio. Añado los cambios, realizo un commit con el mensaje 'añadido autor en index'. Muestro los logs del repositorio en una línea, gráficamente y con 'decoración' con el comando:

``````bash
git checkout main
git status
git add .
git commit -m "añadido autor en index"
git log --graph --oneline --decorate
``````

![image-20250214204949707](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214204949707.png)

![image-20250214205340049](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214205340049.png)

![image-20250214205401937](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214205401937.png)

![image-20250214205418514](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214205418514.png)



### Cuestión 6

Fusiono la rama `feature-estilos` en la rama `main`. Muestro los logs del repositorio en una línea, gráficamente y con decoración.

![image-20250214210139636](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214210139636.png)

![image-20250214210052532](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214210052532.png)

``````
git status
git merge feature-estilos
git log --graph --oneline --decorate
``````



## 4. Cuestiones Parte Remota

Una vez instalado y configurado `SourceTree`:

### Cuestión 1

Continúo con el repositorio `labdist`. Añado el repositorio al ***Sourcetree***.



![image-20250214230250864](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214230250864.png)

Una vez añadido el repositorio:

![image-20250214211013156](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214211013156.png)



### Cuestión 2

En mi cuenta de GitHub, creo un repositorio remoto y subo los ficheros de mi repositorio local. Subo todas las ramas. Muestro además la captura de pantalla donde se ven en GitHub.

![image-20250214211708201](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214211708201.png)

![image-20250214211915440](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214211915440.png)

![image-20250214212055074](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214212055074.png)

![image-20250214212129067](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214212129067.png)

![image-20250214212147020](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214212147020.png)

Se ven los cambios de color de la primera parte de la práctica...

![image-20250214212251606](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214212251606.png)

Se ven en la web de GitHub los contenidos:

![image-20250214212507954](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214212507954.png)

Las ramas en `Branches`:

![image-20250214212544427](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214212544427.png)



### Cuestión 3 ~ 4

En el repositorio **local**, creo una rama `feature-index`. Añado el código del enunciado, en la sección:
 `<section class="about" `

``````html
<h2>Conoce a Nuestro Equipo</h2>
<p>
    labdist está formado por un equipo de diseñadores y
    desarrolladores apasionados que trabajan juntos para ofrecer soluciones
    tecnológicas de alta calidad. Cada miembro de nuestro equipo aporta
    experiencia en diseño, programación, y soporte técnico, asegurando que
    nuestros clientes reciban un servicio completo y personalizado.
<p>
<p>
    Nuestro objetivo es que cada cliente se sienta acompañado en su
    aventura digital, con un equipo profesional que entiende sus necesidades y
    trabaja para hacer crecer su presencia en línea.
</p>

``````



Agrego la nueva rama y después puedo verla en mi lista.

![image-20250214212801008](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214212801008.png)

![image-20250214212832599](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214212832599.png)

Añado el código del enunciado al index:

![image-20250214213213653](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214213213653.png)

En `File Status` veo los cambios y pulso en `Stage All`.

 ![image-20250214213714492](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214213714492.png)

Efectúo el commit habiendo añadido todo al stage e indicado el comentario.

![image-20250214214020922](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214214020922.png)

Con `push` llevo los cambios al remoto:

![image-20250214214114737](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214214114737.png)

Confirmo comprobando GitHub web:

![image-20250214214212410](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214214212410.png)

![image-20250214214641084](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214214641084.png)

En el repositorio local hago la fusión con el  `merge` de la rama `main` con la rama  `feature-index`

![image-20250214215747955](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214215747955.png)



### Cuestión 5

Edito el fichero `contacto.html` borrando unas líneas. Muestro los ficheros con cambios pendientes y las diferencias. Añado los cambios y hago commit.

Añado esta nueva sección:

![image-20250214220221085](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214220221085.png)

Se ven los cambios en la esquina inferior derecha:

![image-20250214220326233](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214220326233.png)

Hago el Stage y Commit de los cambios:

![image-20250214220537192](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214220537192.png)

### Cuestión 6

Me doy cuenta del error. Deshago totalmente el commit anterior. Capturo el estado actual del repositorio. (Me aseguro de que el fichero contacto.html ha recuperado las líneas borradas y no hay cambios pendientes en  el repositorio.) 

![image-20250214220852456](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214220852456.png)

Especifico que es un hard reset para remediar el estropicio por lo sano.

![image-20250214220954309](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214220954309.png)

Volví al punto anterior. 

![image-20250214221017600](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214221017600.png)

El fichero contacto ya no tiene esa sección que me inventé debajo del formulario.

![image-20250214221121222](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214221121222.png)

### Cuestión 7

Creo una rama `feature-mapa` y me cambio a ella. Incluyo el código del enunciado en el archivo `contacto.html`:

``````html
<section class="map">
   <h2>Nuestra Ubicación</h2>
     <p>C/Luis Moya 335, Gijón, Asturias</p>
     <iframe src="https://www.google.com/maps?
                q=C%2FLuis%20Moya%20335%2C%20Gij%C3%B3n%2C%20Asturias&output=embed"
                width="600" height="450" style="border:0;" allowfullscreen=""
                 loading="lazy">
    </iframe>
</section>

``````

Creo la rama:

![image-20250214221428927](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214221428927.png)

Añado dicho código:

![image-20250214221538505](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214221538505.png)

Hago Stage y Commit de los cambios y veo el estado actual:

![image-20250214221647961](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214221647961.png)

### Cuestión 8

Subo los cambios de todas las ramas al remoto. Muestro en el remoto los cambios del archivo `contacto.html` en la rama `feature-mapa`

Push de todo:

![image-20250214221826946](C:\Users\jumen\Documents\GitHub\juan-hub\__year2\2_MARTES_DESPLIEGUE\TAREA 2\image-20250214221826946.png)

Veo en remoto subido el párrafo en la rama `feature-mapa`

![image-20250214221915485](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214221915485.png)

![image-20250214222014893](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214222014893.png)

### Cuestión 9

En GitHub, en la rama `main`, fusiono la rama `feature-mapa`. Bajo los cambios del remoto a local. Dejo los dos repositorios sincronizados. Muestro una captura de pantalla donde se ve la página principal de mi repositorio remoto.

En GitHub web, utilizo un ***pull request*** para solicitar el merge de los cambios.

![image-20250214222400794](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214222400794.png)

![image-20250214222515038](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214222515038.png)

Confirmo el merge:

![image-20250214222548438](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214222548438.png)

![image-20250214222714079](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214222714079.png)

![image-20250214222957724](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214222957724.png)

![image-20250214223431566](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214223431566.png)



## 5. Cuestiones Parte Conflictos

### Cuestión 1

Creo la rama `hotfix-js`. Me cambio a ella. Añado el código en el fichero `script.js`. Confirmo el cambio y hago un commit con el mensaje "corregido problema en script.js".

Nueva rama:

![image-20250214223629485](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214223629485.png)

Cambios en el fichero:

![image-20250214223652871](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214223652871.png)

Commit:

![image-20250214223747089](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214223747089.png)

![image-20250214223825003](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214223825003.png)

### Cuestión 2

Vuelvo a la rama `main.` En el fichero `script.js` en las mismas líneas añado el siguiente código. Confirmo cambios. Hago un commit con el mensaje "corregido problema en script.js rama main".

![image-20250214223912865](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214223912865.png)

Nuevos cambios:

![image-20250214223925538](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214223925538.png)

Commit:

![image-20250214224031182](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214224031182.png)

![image-20250214224110127](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214224110127.png)

### Cuestión 3

Fusiono la rama `hotfix-js` con `main`. Debe producirse un conflicto. Lo resuelvo. Subo los cambios al remoto.

Hago el **merge** a `main` de `hotfix` con botón derecho:

![image-20250214224327219](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214224327219.png)

Por tanto aparece el siguiente **conflicto**:

![image-20250214224423650](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214224423650.png)

Veo el ***diff*** de ambos ficheros y lo soluciono a mano:

![image-20250214224514915](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214224514915.png)

Resuelto:

![image-20250214224615532](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214224615532.png)

En Sourcetree confirmo que ha sido resuelto el conflicto entre ambas versiones

![image-20250214224712190](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214224712190.png)

![image-20250214224855211](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214224855211.png)



Estado final del Sourcetree tras toda la operación:

![image-20250214224943588](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214224943588.png)

![image-20250214225039740](C:\Users\jumen\AppData\Roaming\Typora\typora-user-images\image-20250214225039740.png)

## 6. Repositorio en GitHub:

https://github.com/Jumenfer92/labdist

## 7. Videoclip de la Tarea 2:

