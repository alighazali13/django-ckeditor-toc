Deprecation notice
==================

I do not recommend using this package anymore since the open source version of CKEditor 4 has unfixed security issues. More on this in `my blog post <https://406.ch/writing/django-ckeditor/>`__. Alternatives are listed `here on Django Packages <https://djangopackages.org/grids/g/wysiwyg/>`__. I personally am using `django-prose-editor <https://406.ch/writing/django-prose-editor-prose-editing-component-for-the-django-admin/>`__. Thanks!


Django CKEditor powerd by django-ckeditor
=========================================

.. image:: https://img.shields.io/pypi/v/django-ckeditor-with-toc.svg
   :target: https://pypi.python.org/pypi/django-ckeditor-with-toc


**Django CKEditor Configurations.**

Here, I will only explain how to configure the Table of Contents (TOC) in django-ckeditor, but to view the full django-ckeditor documentation, `click here <https://pypi.org/project/django-ckeditor/>`_.


Example ckeditor configuration
------------------------------

::

    CKEDITOR_CONFIGS = {
        'default': {
            'skin': 'moono',
            # 'skin': 'office2013',
            'toolbar_Basic': [
                ['Source', '-', 'Bold', 'Italic']
            ],
            'toolbar_YourCustomToolbarConfig': [
                {'name': 'document', 'items': ['Source', '-', 'Save', 'NewPage', 'Preview', 'Print', '-', 'Templates']},
                {'name': 'clipboard', 'items': ['Cut', 'Copy', 'Paste', 'PasteText', 'PasteFromWord', '-', 'Undo', 'Redo']},
                {'name': 'editing', 'items': ['Find', 'Replace', '-', 'SelectAll']},
                {'name': 'forms',
                 'items': ['Form', 'Checkbox', 'Radio', 'TextField', 'Textarea', 'Select', 'Button', 'ImageButton',
                           'HiddenField']},
                '/',
                {'name': 'basicstyles',
                 'items': ['Bold', 'Italic', 'Underline', 'Strike', 'Subscript', 'Superscript', '-', 'RemoveFormat']},
                {'name': 'paragraph',
                 'items': ['NumberedList', 'BulletedList', '-', 'Outdent', 'Indent', '-', 'Blockquote', 'CreateDiv', '-',
                           'JustifyLeft', 'JustifyCenter', 'JustifyRight', 'JustifyBlock', '-', 'BidiLtr', 'BidiRtl',
                           'Language']},
                {'name': 'links', 'items': ['Link', 'Unlink', 'Anchor']},
                {'name': 'insert',
                 'items': ['Image', 'Flash', 'Table', 'HorizontalRule', 'Smiley', 'SpecialChar', 'PageBreak', 'Iframe']},
                '/',
                {'name': 'styles', 'items': ['Styles', 'Format', 'Font', 'FontSize']},
                {'name': 'colors', 'items': ['TextColor', 'BGColor']},
                {'name': 'tools', 'items': ['Maximize', 'ShowBlocks']},
                {'name': 'about', 'items': ['About']},
                '/',  # put this to force next toolbar on new line
                {'name': 'yourcustomtools', 'items': [
                    # put the name of your editor.ui.addButton here
                    'Preview',
                    'Maximize',

                ]},
            ],
            'toolbar': 'YourCustomToolbarConfig',  # put selected toolbar config here
            # 'toolbarGroups': [{ 'name': 'document', 'groups': [ 'mode', 'document', 'doctools' ] }],
            # 'height': 291,
            # 'width': '100%',
            # 'filebrowserWindowHeight': 725,
            # 'filebrowserWindowWidth': 940,
            # 'toolbarCanCollapse': True,
            # 'mathJaxLib': '//cdn.mathjax.org/mathjax/2.2-latest/MathJax.js?config=TeX-AMS_HTML',
            'tabSpaces': 4,
            'extraPlugins': ','.join([
                'uploadimage', # the upload image feature
                # your extra plugins here
                'div',
                'autolink',
                'autoembed',
                'embedsemantic',
                'autogrow',
                'toc',
                # 'devtools',
                'widget',
                'lineutils',
                'clipboard',
                'dialog',
                'dialogui',
                'elementspath'
            ]),
        }
    }
