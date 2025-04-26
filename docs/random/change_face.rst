.. _change_background:

Screen & Face
=========================

Changing screen orientation
----------------------------

Go to the top left corner of the screen and click on the Raspberry Pi icon. Then go to Preferences > Screen Configuration.

See `this video <https://www.youtube.com/shorts/PqGTuNIe90E>`_ for a demonstration.

If anyone knows how to pre-configure the screen orientation in our `Packer image creation workflow <https://github.com/Nate711/pupperv3-monorepo/tree/main/infra/pupper_image_builder>`_, please let us know!

Changing Pupper's Face
----------------------------

You can change Pupper's face using the ``pcmanfm`` command to set the wallpaper.

.. code-block:: shell

    pcmanfm --set-wallpaper [FULL_IMAGE_PATH]

For example, to set the wallpaper to ``pupperface2.jpg``, you would run:

.. code-block:: shell

    pcmanfm --set-wallpaper /usr/share/rpd-wallpaper/pupperface2.jpg

There are a few face images already loaded onto the pi. You can find them in the following directory:

.. code-block:: shell

    /usr/share/rpd-wallpaper

They include the following:

- ``pupperface2.jpg``
- ``pupperface3.png`` (default)
- ``bmo9.jpg``

You can also add your own images to the ``/usr/share/rpd-wallpaper`` and use them as wallpapers.