djangocms-text-ckeditor
=======================

Text Plugin for django-cms with CK-Editor

Installation
------------

This plugin requires `django CMS` 2.3 or higher to be properly installed.

* In your projects `virtualenv`_, run ``pip install djangocms-text-ckeditor``.
* Add ``'djangocms_text_ckeditor'`` to your ``INSTALLED_APPS`` setting.
* Run ``manage.py migrate djangocms_text_ckeditor``.


Usage
-----


You can add a new setting to your settings.py called `CKEDITOR_SETTINGS`

the default is::

	CKEDITOR_SETTINGS = {
	    'language': '{{ language }}',
	    'toolbar': 'Basic',
	    'skin': 'kama',
	    'toolbarCanCollapse': False,
	}

It is a dict that hold all CKEditor settings. For an  overview of all the available settings have a look here:

http://docs.cksource.com/ckeditor_api/symbols/CKEDITOR.config.html for all settings

Drag & Drop Images
------------------

In IE and Firefox based browsers it is possible to drag and drop a picture into the text editor.
This image is base64 encoded and lives in the 'src' attribute as a 'data' tag.

We detect this images, encode them and convert them to picture plugins.
If you want to overwirite this behavior for your own picture plugin:

There is a setting called:

`TEXT_SAVE_IMAGE_FUNCTION = 'djangocms_text_ckeditor.picture_save.create_picture_plugin'` 

you can overwrite this setting in your settings.py and point it to a function that handles image saves.
Have a look at the function `create_picture_plugin` for details.


Translations
------------

If you want to help translate the plugin please do it on transifex:

https://www.transifex.com/projects/p/django-cms/resource/djangocms-text-ckeditor/