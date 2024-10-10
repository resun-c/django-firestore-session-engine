# Django Firestore Session Engine

This is a simple [`Django Session Engine`](https://docs.djangoproject.com/en/dev/topics/http/sessions) that uses `Firestore` as the database to store session data.

## Instalation

```
pip install --index-url https://test.pypi.org/simple/ --no-deps django-firestore-session-engine

```

## Setup & Usage

#### 1. Add `django_firestore_session_engine` to the `INSTALLED_APPS` list in settings.

```
INSTALLED_APPS = [
    ...,
    'django_firestore_session_engine'
]
```

#### 2. In settings, set `SESSION_ENGINE` to `django_firestore_session_engine.engine`
 
```
SESSION_ENGINE = 'django_firestore_session_engine.engine'

```

#### 3. initialize a firestore collection and set it to `FIRESTORE_SESSION_COL` in settings.

```
FIRESTORE_SESSION_COL = FIRESTORE.collection("session")
```

## Tips

Do not 'initialize' Firestore or 'import' initialized Firestore in more than one file while using it with Djnago. A good practice is to initialize firestore in the `settings` file and import it from there.


## Acknowledgements

This Engine was made based on what is described in the Djnago documentation on [`How to use sessions`](https://docs.djangoproject.com/en/dev/topics/http/sessions/) and after some reverse-engineering of the existing session engines, especially the `'django.contrib.sessions.backends.db'` and `'django.contrib.sessions.backends.file'` engines.


Please send any  comments  and  criticisms  to the author here <a href="mailto:saif.resun@outlook.com">saif.resun<span style="color: #fc4445; margin: 0 3px; font: 1rem 'JetBrains Mono'; font-style: italic;">@</span>outlook.com</a>

Cheers!