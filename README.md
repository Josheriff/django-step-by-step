# Django pasito a pasito (suave suavesito)

- Creamos virtualenv
- `pip install django`
- `django-admin startproject {{mysite}}`

Ha creado una carpeta llamada mysite, contiene otra crpeta con archivos py y otra carpeta dentro también llamada mysite

Cada "sitio" puede tener tantas "apps" como sea necesario, 
Básicamente aquí se denomina app a lo que siempre he venido conociendo como componente
pero bien hecho, porque no se acobla a nada, lo quitas y pones de diferentes web-sites django

## Ejemplo para añadir una "app" de encuestas 

Desde la carpeta "mysite" creada por la orden útlima que dimos
- `python manage.py startapp polls`

Nos crea una carpeta llamada polls que ya contiene unos pocs archivos.

vamos a ver que pasa si corremos django:

- `python manage.py runserver`

Como no hemos hecho nada realmente, tenemos que darle forma a esos polls

Para eso hay que irse a la carpeta polls e ir a `models.py`

Creamos las clases heredando de `models.Model` para poder determinar que tipo de dato se va alojar en base de datos
una librería de base datos, básicamente

Una vez creadas las clases basandonos en lo que va a figurar en base de datos (aún no hemos metido lógica)

Ahora nos vamos a `{{PROJECT-ROOT}}/{{MYSITE}}/{{MYSITE}}`
y en el archivo `settings.py` en la constante `INSTALLED_APPS` añadimos `polls` 

Debemos escribir:

- `python manage.py makemigrations {{polls}}`

Que le dice a la app, que ya está, que coja ese código y haga su magia en el resto de Django

Ahora:

- `python manage.py migrate`

## Populando la base de datos


## Accediendo a la base de datos desde la shell

- `python manage.py shell`

y ahora en la shell:

```
import django
django.setup()
from polls.models import Question, Choice
Question.objects.all() # devuelve [] porque no tenemos nada aún en bbdd
```

Hay que modificar las classes y añadirles el built_in __str__ (probar con rpr)


## Creando un admin

- `python manage.py createsuperuser`

Rellenamos los datos y ya podemos ir a `http://127.0.0.1:8000/admin`

Para poder administrar las clases creadas desde el panel de administración, y hay que registrarlas

hay que ir a `polls/admin.py` e importarlos:

```
from django.contrib import admin

# Register your models here.
from .models import Question, Choice

admin.site.register(Question)
admin.site.register(Choice)

```
