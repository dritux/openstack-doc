# Django Translation, Internationalization and Localization in OpenStack



### Estructure
```
app_name/locale/
├── djangojs.pot
├── django.pot
├── pt_BR
│   └── LC_MESSAGES
│       ├── djangojs.mo
│       ├── djangojs.po
│       ├── django.mo
│       └── django.po
├── es
│   └── LC_MESSAGES
│       ├── djangojs.mo
│       ├── djangojs.po
│       ├── django.mo
│       └── django.po

```

### Compile messages

* Example compile messages in horizon - default --all

```
Generating files .po
$ ./run_tests.sh --compilemessages

Compile .mo
$ ./run_tests.sh --makemessages
```

* Example compile messages in django

```
Generating files .po
$ python manage.py makemessages

* Compile .mo
$ python manage.py compilemessages
```

* Example compile message locale name

```
Generating message file .po
$ python manage.py makemessages -l es

* Compile .mo
$ python manage.py compilemessages -l es
```

* Example generating message file .pot
```
$ python setup.py extract_messages
```

---

### Example message files .po|.pot
```
msgid "Mail Server"
msgstr "Servidor de Email"
```

---

### Exec commandas manage.py

```
import os
import sys

if __name__ == "__main__":
    os.environ.setdefault(
        "DJANGO_SETTINGS_MODULE", "pfsense_dashboard.settings")
    from django.core.management import execute_from_command_line  # noqa
    execute_from_command_line(sys.argv)
```


---

### Merge and install translate

```
* Merge .pot in .po
$ msgmerge -U openstack_dashboard/locale/es/LC_MESSAGES/django.po openstack_dashboard/locale/${YOURDJANGO}.pot

* Check install translations
bash -c "find ${MODULENAME} -type f -regex '.*\.pot?' -print0| xargs -0 -n 1 --no-run-if-empty msgfmt --check-format -o /dev/null"

```

---

### Config setthings.py

```

BASE_DIR = os.path.dirname(os.path.dirname(__file__))

LOCALE_PATHS = (os.path.join(BASE_DIR, 'pfsense_dashboard/locale'),)

MIDDLEWARE_CLASSES = (
    'django.middleware.locale.LocaleMiddleware',
    ...
)

TEMPLATE_CONTEXT_PROCESSORS = (
    'django.core.context_processors.i18n',
    ...
)

LANGUAGES = (
    ('en', _('English')),
    ('pt-br', 'Portuguese (Brazil)'),
)
LANGUAGE_CODE = 'en'

USE_I18N = True

USE_L10N = True

USE_TZ = True
```

---


### Refereces

[git](https://gist.github.com/gabrielhurley/2969337)
[Plugin Horizon](http://docs.openstack.org/developer/horizon/tutorials/plugin.html)
