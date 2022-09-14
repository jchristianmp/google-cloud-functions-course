# GOOGLE CLOUD FUNCTIONS COURSE
## Starting a project

To start a new project in Google Cloud we can go to [Firebase Console](https://console.firebase.google.com) or create it from [Google Cloud Platform](https://console.cloud.google.com).

## Creating a virtual Enviroment en WINDOWS
Lo primero es instalar el paquete de entorno virtual `python 3-venv` `python 3-virualvenv`. Para windows se ejecuta con los siguientes comandos:
```
pip install virtualenv
or
pip install --upgrade virtualenv
```
NOTA: si en caso nos manda un error por versión de pip, entonces debemos actualizar el paquete pip primero:
```
python.exe -m pip install --upgrade pip
```
En caso la actualización no logró instalar la nueva versión de pip, debemos ejecutar:
```
python -m ensurepip
```

Luego, para crear un entorno virtual, ejecutamos:
```
python -m venv venv
```
Para activar el entorno virtual:
```
venv\scripts\activate.bat
```

## Añadiendo paquetes al EV
Para añadir e instalar paquetes al EV creado, debemos crear un archivo llamado `requeriments.txt` y ejecutar el siguiente comando
```
pip install -r requirements.txt
```

## Cambio de versión de python del EV
Si se desea cambiar la versión de python del entorno virual ya activo y creado, se tendrá qué ejecutar lo siguiente:
```
virtualenv -p python3.8.14 [nombre_entorno_virtual]
```

Para verificar la versión instalada y usada en nuestro entonrno: 
```
python -V
o
py -V
```

## Trabajando con GITHUB
Inicializamos git para que se cree un repositorio vacio en el directorio que estamos trabajando actualmente
```
git init
```

Para añadir el repositorio al directorio en el que estamos trabajando:
```
git remote add origin git@github.com:[usuario_github]/[nombre_repositorio].git
```
ejemplo: 
```
git remote add origin git@github.com:jchristianmp/google-cloud-functions-course.git
```
NOTA: Esto solo se ejecutará la primera vez

Si es la primera vez que subimos cambios, debemos configurar el email y usuario:
```
git config --global user.email "email@email.com"
git config --global user.name "Nombre"
```

Añadimos los cambios con:
```
git add .
```
Podemos verificar los archivos a subir con:
```
git status
```

Y lo que queremos que nos suba podemos especificarlo en el archivo `.gitignore`

Hacemos commit
```
git commit -m "Primer commit"
```
 
 Por ultimo hacemos Push
 ```
 git push -u origin [nombre_branch]
 ```

Para actualizar los archivos locales debemos hacer pull
```
git pull origin [nombre_branch]
```

Para cambiar de branch:
```
git checkout [nombre_branch]
```

Para crear nuevo branch:
```
git branch [nombre_branch]
```
Para ver la lista de branchs
```
git branch
```

Para eliminar un branch, debemos elegir otro branch inicialmente y luego ejecutar las siguientes lineas:
```
git branch -D [nombre_branch]
```

Para crear nuevo branch y al mismo tiempo elegirlo:
```
git chekout -b [nombre_branch]
```

## NOTA: ERROR POR FALTA DE LLAVE
Si al intentar subir un archivo al repositorio de GITHUB nos arroja un error por acceso denegado o falta de llave SSH, entonces debemos generar una y agregarla a nuestro perfil de 
github:
[Generar una llave SSH](https://docs.github.com/es/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

Seguido de eso, debemos agregarla a nuestro perfil [Añadiendo llave creada a perfil](https://docs.github.com/es/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

## Haciendo Deploy Google Cloud Functions
Para iniciar debemos correr:
```
gcloud init
```
Continuar seleccionando la configuración deseada.

Para ver la lista de proyectos:
```
gcloud projects list
```

Para seleccionar o cambiar a otro proyecto:
```
gcloud config set project [id_proyecto]
```

Para hacer deploy de la funcion, para ello debemos estar en la carpeta de nuestro proyecto
```
gcloud functions deploy [nombre_funcion] --runtime python[version] --trigger-http
```
Una vez cargado, podemos acceder a la función seleccionando el URL que nos genera, ejemplo https://us-central1-cloud-function-curso.cloudfunctions.net/hello_world

Para subir todo al repositorio, debemos regresar a la raiz del cporyecto con cd..
