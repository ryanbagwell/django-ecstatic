Settings
========

.. currentmodule:: django.conf.settings


Storage Settings
----------------

.. attribute:: ECSTATIC_STRICT

    :default: ``False``

    Specifies whether Ecstatic should raise an exception when it can't convert
    a URL. If ``False``, the unconverted URL will be used. This situation
    typically arises when a CSS file points to a non-existent image.


Manifest Settings
-----------------

.. attribute:: ECSTATIC_MANIFEST

    :default: ``'ecstatic.manifests.JsonManifest'``

    The dotted path to the manifest class to be used by the
    ``createstaticmanifest`` management command and
    ``ecstatic.storage.StaticManifestMixin``.


.. attribute:: ECSTATIC_MANIFEST_FILE

    :default: ``None``

    The path where the manifest file should be saved. This setting must be set
    if using staticfiles manifests.


.. attribute:: ECSTATIC_USE_MANIFEST

    :default: the opposite of ``DEBUG``

    Specifies whether the manifest should be used by the
    (``ecstatic.storage.StaticManifestMixin`` extending) storage class.


.. attribute:: ECSTATIC_MANIFEST_CACHE

    :default: ``'ecstatic_manifest'``, if the ``CACHES`` dictionary contains it,
    otherwise 'default'

    The name of the cache that should be used by the manifest class.

.. attribute:: ECSTATIC_MANIFEST_EXTRAS

    :default: ``['admin/']``

    A list of paths that will not be found by Django's ``STATICFILES_FINDERS``
    but that should nonetheless be included in the manifest. This setting exists
    chiefly to support the Django admin, which uses the static template tag with
    the path ``'admin/'`` in order to get a static prefix for the admin. (Note
    that Django's behavior here may be incompatible with storages that alter the
    filepath in a way other than adding a prefix.)
