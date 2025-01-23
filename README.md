# GIT
### Inicializar por primera vez

Poner el nombre de usuario, luego el correo electrónico.
```
$ git config --global user.name "Enrique Herrera"
$ git config --global user.email enriqueherreranz@gmail.com
```

Usar VS Code como editor principal y ver el archivo global.
```
$ git config --global core.editor "code --wait"
$ git config --global -e
```

Poner el salto de línea en Windows para antes de subir al repositorio.
```
$ git config --global core.autocrlf true
```

### Comandos comúnes

Listar archivos y carpetas de un directorio.
```
$ ls
```
Observar en que carpeta nos encontramos nosotros ahora.
```
$ pwd
```

Inicializar git en un repositorio y verlo oculto.
```
$ git init
$ ls -a
```

### Poner archivos en stage
Ingresamos a la carpeta y agregamos el .git para inicializar, luego en la carpeta ponemos code . y se abre VS Code y creamos el archivo, seleccionamos ese archivo en gitbash y ya despues ponemos git status para ver el estado si se subió correctamente.
```
$ git init
$ code .
$ git add archivo1.txt
$ git status
```

### Poner archivos en commit
Ingresamos el comando con un comentario en comillas dobles y después verificamos si todo salió bien.
```
$ git commit -m "Commit inicial"
$ git status
```

### Eliminar archivos de repositorio en stage
Ingresamos el comando y después verificamos si se borró correctamente, luego para eliminar en stage se pone el comando y se actualiza
```
$ rm archivo2.txt
$ git status
$ git add archivo2.txt
```

### Eliminar archivos de repositorio en commit
Ingresamos el comando y después verificamos si se borró usando el comando ls.
```
$ git commit -m "Eliminando archivo 2"
$ git status
```

### Cambiar nombre de archivo
Hay 2 formas las cuales son:
La primera es renombrando el archivo primero, después pasándolo a stage y finalmente a commit.
```
$ mv archivo3.txt archivo.txt
$ git status
$ git add archivo3.txt archivo.txt
$ git status
$ git commit -m "Renombrando archivo"
$ git status
$ ls
```
La segunda es mofiidcando el archivo directamente en stage para después llevarlo a commit.
```
$ git mv archivo.txt archivofinal.txt
$ git status
$ git commit -m "Renombrando archivo"
$ git status
$ ls
```

### Variables de entorno
Debemos crear un archivo .env que este no va a ser visible y va a tener los usuarios y contraseñas delicadas, pero para que no se vea este archivo debemos ignorarlo usando otro archivo llamado .gitignore y ahí debemos ingresar el .env y subir todo al stage y después a commit.
```
$ git add .env .gitignore
$ git commit -m "Subiendo archivos que no serán visibles"
```

### Forma para no usar el git status y de tanta información sino la relevante
Usar git status es un buen método pero ofrece demasiada información, nosotros solo lo usamos para saber si un archivo está sin subir, editado o subido, por eso solo esa información necesitamos así que usaremos el siguiente comando que nos ofrece esa infomración solamente.
```
$ git status -s
```

### Observar lo que se ha editado de un archivo antes de subir
Si necesitamos ver que se modificó en un archivo usamos el comando y para salir de ahí presionamos la tecla u, y si quiero leer el archivo normalmente se pone el comando final.
```
$ git diff
q
cat archivo2.txt
```

### Consultar el historial de cambios
Se debe digitar el comando y ofrece toda la información de los cambios incluyendo el mensaje.
```
$ git log --oneline
```

### Crear ramas que sea independiente de la rama principal
Cuando se trabaja con otros desarrolladores, queremos estar en un espacio individual codeando, para esto es necesario que nos desligemos de la rama principal para poder continuar con el desarrollo de nuestro código y cuando esté listo mover todo a la rama principal.
Primero se debe ver si estamos en la rama principal, luegos agregamos la otra rama que será ramab, como ejemplo modificamos el archivo2.txt, lo subimos en rama b tanto al stage como al commit y vemos los cambios con el comando final y vemos que este cambio último aparece como realizado en ramab.
```
$ git branch
$ git checkout -b ramab
$ git log --oneline
```

### Regresar a la rama principal
Solo ponemos el comando y el nombre que es master o en otros casos main.
```
$ git checkout master
```

### Llevar cambios de ramab a master
Debemos estar en la rama master y decir cual rama queremos traer con el siguiente comando.
```
$ git merge ramab
```

### Subir todo el código trabajado y subirlo a GitHub
En caso existan problemas, sería recomendable empezar eliminando la carpeta llamada "config.lock", eso se hace con estos comandos.
```
$ ls -a .git
$ rm -f .git/config.lock 
```

Ahora si ya podemos subirlo, para eso debemos poner el comando, este nos va a mandar a digitar el token, el cual tenemos que sacarlo de Github.
```
$ git remote add origin https://github.com/enriqueherreranz/miweb.git
$ git push -u origin master
```

### Agregar más cosas directo al repositorio
Se debe insertar solamente el comando, previamente ya subido a storage y a commit, de esta manera se actualiza.
```
$ git push
```
