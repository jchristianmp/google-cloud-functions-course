# GOOGLE CLOUD FUNCTIONS COURSE
## Starting a project

To start a new project in Google Cloud we can go to [Firebase Console](https://console.firebase.google.com) or create it from [Google Cloud Platform](https://console.cloud.google.com).

## Creating a virtual Enviroment
First we have to install `python 3-venv` on windows with the following commands
```
pip install virtualenv
or
pip install --upgrade virtualenv
```
Then, we execute the following command:
```
python -m venv venv
```
To activate de virtual enviroment (in Windows)
```
venv\scripts\activate.bat
```

In order to add new packages to our VE, we create a file called `requeriments.txt` and execute the following command 
```
pip install -r requirements.txt
```

To install pip package on windows
```
python -m ensurepip
```
Si solicita actualizacion de paquete pip, usar el siguiente comando
```
python.exe -m pip install --upgrade pip
```

Acutalización