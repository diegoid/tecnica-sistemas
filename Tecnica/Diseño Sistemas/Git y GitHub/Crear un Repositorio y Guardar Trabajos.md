
### Pasos Para Crear un Repositorio en Git 

**Paso 1: Elegir la carpeta con la cual vamos a trabajar.**

Para usar Git con una carpeta, seguir estos pasos

1. Ir a la carpeta donde quieres trabajar.
    
2. Click derecho.
    
3. Elegir:
    
==Git Bash Here==

Eso abre la carpeta elegida en la consola.

**Paso 2: Iniciar el Repositorio.**

Luego ejecuta:

	git init

Con esto Git está listo para empezar a trabajar con esta carpeta.

Dato: Cuando hago "git init" en una carpeta Git crea una carpeta oculta llamada:

**.git**

Ese directorio contiene **todo el historial de cambios**. ==No lo borres, sino chau historial.==

Tu carpeta queda así:

*MiApp*  
   *archivo1.txt*  
   *archivo2.txt*  
   *.git*

**Paso 3: Agregar Archivos al Control de las Versiones.**

Para eso tipeo...


	git add .


El . significa que va a agregar TODOS los archivos que haya en la carpeta
(archivos, carpetas y subcarpetas).

Git le "Saca una foto a todo" (como está mi carpeta ahora, los archivos que tiene,
sus contenidos, todo).

Una vez que le saqué esa foto, **falta que le de la orden final**, que es "guardá esa foto".

**Paso 4: Guardar "la Foto" en mi proyecto.**

Con "git add . " ya saqué una foto. 

Pero como que no la guardé todavía en mi proyecto.

Al guardarla, si algo pasa el día de mañana y hago cambios que no me gustan, puedo recuperar 
esa "Foto" que saqué porque **"ya está almacenada en mi repositorio"**.

Ese "guardado" de "la foto", se llama "hacer un commit". 

Guardarlo en mi repositorio como un "commit".

Imaginemos que mi repositorio tiene estos commits:

- Primer commit
- Primera versión del sitio
- Segunda versión del sitio
- Tercera versión del sitio.

Cada commit nació primero de hacer "git add ." (avisarle a Git que "sacara la foto" y yo después
fuí guardando cada foto con un nombre (ejemplo "Segunda versión del sitio").

Después si el día de mañana no me gustó un commit puedo volver a un previo
(por ejemplo, si no me gustó la tercera versión del sitio, puede recuperar la segunda
versión u otra).


Cómo hago un commit? Con este comando:

	git commit -m "primer commit"

Después del -m, pongo entre comillas un comentario que me sea util acerca 
del commit.

**Después del Primer Commit (Lo que mas usamos) **

La vida commiteando tiene siempre esta secuencia....

A) Hago cambios en uno o mas archivos.
B) Hago 
	git add .

C) Hago commit ...

	git commit -m "descripcion del commit"


### **Importante: Si cambiás archivos...  después de agregarlos con "Git add . " 

Si haces

	git add . 

Git saca "una foto" de todos esos archivo. Esa foto quedará guardada cuando
hagas el "commit".

Ahora, ==si después de "git add . " hiciste cambios en los archivos== .... ==esos cambios==
==NO SE GUARDAN en el commit==.

Para que se guarden, cada vez que hacés cambios... tenés que hacer 

	git add .

Otra vez. Ahí si, si hacés un commit, el commit va estar actualizado.

Datos  utiles:

- Cuando hacés "git add ." git saca una "captura" de esos cambios y los pone en un area de "staging" (así la llama) hasta que los guardes definitivamente **haciendo un commit**.
  
- Antes de hacer un "commit", podés ver si te quedaron archivos "fuera del area de staging" haciendo....

		git status

  Si te marca que hay cosas "no trackeadas", podés hacer "git add . " y de ahí el commit.

### Sobre esto último... 

Working Directory (tu carpeta)
↓
Staging Area (git add)
↓
Repository (git commit)

Para hacerlo fácil... 

git add = toma una foto del archivo en ese momento

Si lo cambias después:

👉 la foto no se actualiza.


### **Algunas Dudas... 

**¿Qué pasa si muevo la carpeta?**

Nada.  Git funciona porque la carpeta contiene:

.git

Entonces si movés a otro lado, sigue funcionando.

 **¿Qué pasa si copio a un USB?**

También funciona. Si copias la carpeta **completa** incluyendo `.git`, el repositorio sigue funcionando.

 **¿Qué pasa si borro la carpeta .git ?**

Perdes el historial y el proyecto vuelve a ser una carpeta "normal".
