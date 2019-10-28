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