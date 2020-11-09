heroku:
pip install django-heroku whitenoise gunicorn

## file: 
Procfile 
``` release: python manage.py migrate 
    web: gunicorn test_.wsgi --log-file -
```
runtime.txt >> python version
requirements.txt >> pip freeze


## settings.py

MIDDLEWARE = [
    'whitenoise.middleware.WhiteNoiseMiddleware',
]


STATICFILES_STORAGE = 'whitenoise.storage.CompressedManifestStaticFilesStorage'
STATIC_ROOT = os.path.join(os.path.dirname(BASE_DIR), 'static')
STATIC_URL = '/static/'
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, "static"),
]
