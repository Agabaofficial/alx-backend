Learn how to parametrize Flask templates to display different languages
Learn how to infer the correct locale based on URL parameters, user settings or request headers
Learn how to localize timestamps

Flask-Babel is an extension to Flask that adds i18n and l10n support to any Flask application with the help of babel, pytz and speaklater. It has builtin support for date formatting with timezone support as well as a very simple and friendly interface to gettext translations.

Installation
Install the extension from PyPi:

$ pip install Flask-Babel
Please note that Flask-Babel requires Jinja >=2.5. If you are using an older version you will have to upgrade or disable the Jinja support (see configuration).

Configuration
To get started all you need to do is to instantiate a Babel object after configuring the application:

from flask import Flask
from flask_babel import Babel

app = Flask(__name__)
app.config.from_pyfile('mysettings.cfg')
babel = Babel(app)
To disable jinja support, include configure_jinja=False in the Babel constructor call. The babel object itself can be used to configure the babel support further. Babel has the following configuration values that can be used to change some internal defaults:

BABEL_DEFAULT_LOCALE

The default locale to use if no locale selector is registered. This defaults to 'en'.

BABEL_DEFAULT_TIMEZONE

The timezone to use for user facing dates. This defaults to 'UTC' which also is the timezone your application must use internally.

BABEL_TRANSLATION_DIRECTORIES

A semi-colon (;) separated string of absolute and relative (to the app root) paths to translation folders. Defaults to translations.

BABEL_DOMAIN

The message domain used by the application. Defaults to messages.