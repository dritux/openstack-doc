# Django Translate


### Compile messages in horizon

./run_tests.sh --compilemessages

---

pfsense_dashboard/locale/
├── djangojs.pot
├── django.pot
└── pt_BR
    └── LC_MESSAGES
        └── django.po


msgid "Mail Server"
msgstr "Servidor de Email"

---

manage.py

import os
import sys

if __name__ == "__main__":
    os.environ.setdefault(
        "DJANGO_SETTINGS_MODULE", "pfsense_dashboard.settings")
    from django.core.management import execute_from_command_line  # noqa
    execute_from_command_line(sys.argv)

------------------------------------------------------------------------
python manage.py makemessages -l pt-br
python manage.py compilemessages -l pt-br

python manage.py makemessages -l pt_BR
python manage.py compilemessages -l pt_BR


------------------------------------------------------------------------
setthings.py

from django.utils.translation import ugettext_lazy as _

BASE_DIR = os.path.dirname(os.path.dirname(__file__))

LOCALE_PATHS = (
    os.path.join(BASE_DIR, 'pfsense_dashboard/locale'),
)

MIDDLEWARE_CLASSES = (
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'horizon.middleware.OperationLogMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.contrib.auth.middleware.SessionAuthenticationMiddleware',
    'horizon.middleware.HorizonMiddleware',
    'horizon.themes.ThemeMiddleware',
    'django.middleware.locale.LocaleMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
)

TEMPLATE_CONTEXT_PROCESSORS = (
    'django.core.context_processors.debug',
    'django.core.context_processors.i18n',
    'django.core.context_processors.request',
    'django.core.context_processors.media',
    'django.core.context_processors.static',
    'django.contrib.messages.context_processors.messages',
    'horizon.context_processors.horizon',
    'openstack_dashboard.context_processors.openstack',
)

LANGUAGES = (
    ('en', _('English')),
    ('pt-br', 'Portuguese (Brazil)'),
)
LANGUAGE_CODE = 'pt-br'
USE_I18N = True
USE_L10N = True
USE_TZ = True





python manage.py makemessages --all
python manage.py compilemessages --all
