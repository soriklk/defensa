cd (para ir a directorios/carpetas)
ls -la (mostrar ficheros ocultos)
mkdir (crea directorios/carpetas)
pwd (saber en qué directorio/carpeta estas)
rm -r (borrar carpeta, ficheros)
mv archivo1 archivo2 (renombrar y mover)
cat (mostrar contenido de un fichero)
echo (texto de salida)

—------------------------------------------------------------------

Creamos un directorio con mkdir y después nos situamos en el con cd.
	mkdir carpetaEjemplo
	cd carpetaEjemplo
Ordenamos la creación de los metadatos de Git
	git init
Para ver el estado del repositorio 
git status

ÁREA DEL WORKING → ROJO  No validados, crear o cambiar algún fichero, 

Si lo queremos validar el comando es:
		git add nombreFichero
Después de esto pasan a estar en el área del staging.

ÁREA DEL STAGING → VERDE

     6.  Para aprobar los cambios y hacer el commit es necesario el comando:

		git commit -m “Texto que se quiera imprimir”
     7. De esta manera los archivos desaparecen del área del staging

     8. Para ver las revisiones hechas usamos el siguiente comando:
	
		git log –oneline

     9. Si hacemos un cambio en un fichero que ya está commiteado podemos comparar ese cambio con el comando: 

		git diff
	
	y nos saldrá con un + y - los cambios que ha localizado y ambos ficheros nombrados con un a/ y el otro b/
    
      10. Si queremos deshacer algo que está en el área del working hacemos el comando: 

		git checkout nombreFichero
		
	y nos traerá la última versión validada que esta en el área del staging. Esto no toca el area de staging.

      11. Para el area del staging tenemos el comando

		git reset HEAD nombreFichero

git reset hard ELIMINA LO DEL STAGING Y EL WORKING
	git reset –hard <apuntador del commit(amarillo izq)>
    12. Se puede deshacer los cambios del ultimo commit hecho 

git reveret -n HEAD, y luego conforama con el commit -m mensaje de validación	
    12. Para trabajar en remoto
	
	1.Creamos carpeta con el nombre del proyecto
	2. git init (para la copia del repositorio
	3.Vinculamos el repositorio local con el remoto 
		gir remote add origin urlRepositorio
	4.Nos traemos el repositorio remoto al area del commit del repositorio local
		git fetch origin master
		git fetch origin main

	5.Pasamos del area del commit local a la carpeta de trabajo

		git checkout origin/master
		git checkout origin/main

       13. Para ver en la rama local en la que estamos y la rama remota a la que estamos conectados : 

		git branch -v-a
  14. Podemos tambiar clonar un repositorio que ya esta y nos ahorramos todos los pasos anteriores del git init el fetch y demas simplemente comn:

		git clone urlRepositorio .

15. Para crear ramas esta el comando 

		git branch nombreRama

16.Para cambiar de rama

		git checkout nombreRama

17.Para renombrar la rama
	
		git branch -m

  Tanmbien hemos trabajado con etiquetas

      git tag nombre_etiqueta


  Un resumen de la vinculacion, traspaso de ramas y traspaso de etiquetas(todo lo nombrado con todo su contenido):

  Lo primero es crear un repositorio en remoto con el mismo nombre y vacio.
  Luego copiar la url que hay en code 
  Esa url la pegamos en bash junto al comando
  git remote add origin URL_DEL_REMOTO
      --> si nos da algun tipo de error porque dice que ya existe una conexion simplemente con el comando
              git remote -v, veremos que conexiones tenemos
              si resulta que algun fallo al copiar la url edl remoto con el siguiente comando podemos solucionarlo y renombrar la url
                 git remote set-url origin NUEVA_URL_DEL_REMOTO
  despues una vez que ya esta todo vinculado para mandar todo su contenido al remoto hacemos lo siguiente
      --> para enviar las ramas y todo su contenido
              git push -u all origin
      --> y para enviar las etiquetas 
              git push -u tags origin

              
 
