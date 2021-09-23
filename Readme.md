# Heroku en Linux-Ubuntu

_Pasos par subir una Api basado en Flask a Heroku._
_________________________

Instalacion de un entorno virtual

```bash 
pip install virtualenv
```

```bash
python -m venv venv
```

----

Ingresar al entorno virtual
```bash
abraham@jash-linux:~/Escritorio/Codemirror$ ls
app.py  Readme.md  static  templates  venv
```

```bash
abraham@jash-linux:~/Escritorio/Codemirror$ source venv/bin/activate
```
Si se ejecuto correctamente de debe de aparecer esta forma

```bash
(venv) abraham@jash-linux:~/Escritorio/Codemirror$ 
```

------------

Instalar todas las librerías a utilizar

```bash
    pip install flask
    pip install gunicorn
    pip install flask-codemirror
    pip install Flask-WTF
```
Se crear un archivo con las librería.

```bash
venv) abraham@jash-linux:~/Escritorio/Codemirror$ pip freeze > requirements.txt 
```
Crear un archivo con el siguiente Nombre:
```bash
Procfile
```
Debe de contener
```bash
web: gunicorn nombre_app:app
```
En el nombre_app debe de ir el nombre de la aplicacion en este caso, se llama app.
El Procfile debe de ir de la siguiente manera:
```bash
web: gunicorn app:app
```
______
```bash
(venv) abraham@jash-linux:~/Escritorio/Codemirror$ heroku login
```
___

```bash
(venv) abraham@jash-linux:~/Escritorio/Codemirror$ heroku create
Creating app... done, ⬢ nameless-dusk-97106
https://nameless-dusk-97106.herokuapp.com/ | https://git.heroku.com/nameless-dusk-97106.git
```
___
```bash
(venv) abraham@jash-linux:~/Escritorio/Codemirror$ heroku git:remote -a nameless-dusk-97106
set git remote heroku to https://git.heroku.com/nameless-dusk-97106.git
```
____
```bash
(venv) abraham@jash-linux:~/Escritorio/Codemirror$ git add -A
(venv) abraham@jash-linux:~/Escritorio/Codemirror$ git commit -m "[ADD] Heroku"
(venv) abraham@jash-linux:~/Escritorio/Codemirror$ git push
(venv) abraham@jash-linux:~/Escritorio/Codemirror$ git push heroku master
```