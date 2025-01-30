=====================
Software Installation
=====================

.. contents:: :depth: 4

Setting up your Raspberry Pi 5
------------------------------

Materials
^^^^^^^^^

* Raspberry Pi 5
* USB drive (see BOM)

Prepare USB drive
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

From your desktop / laptop:

#. Download Pi Imager from https://www.raspberrypi.org/software/
#. Download our custom PiOS image from Google Drive `here <https://drive.google.com/file/d/1a-OG4-mOTl1FWGqtd781xPmMf8ptjysl/view?usp=drive_link>`_
#. Plug in USB drive to your computer
#. Open Pi Imager and you should see menu like below:

    .. image:: ../_static/pi_imager.png
        :align: center

#. Click "Choose Device" and select Raspberry Pi 5 as shown below:

    .. image:: ../_static/pi_imager_device.png
        :align: center

#. Click "Choose OS", scroll down and select "Use custom" as shown below:

    .. image:: ../_static/pi_imager_use_custom_image_screen.png
        :align: center

#. Click "Choose Storage" and select the USB drive you plugged in as shown below:

    .. image:: ../_static/pi_imager_choose_usb.png
        :align: center

#. Click "Next" and then click "Edit Settings"

    .. image:: ../_static/pi_imager_os_customization_screen.png
        :align: center

#. Set OS customizations
    #. Set the hostname & username as shown. 
    #. Set your password (our default is ``rhea123``). 
    #. Replace "Pebble" with your own WiFi name and enter its password. If you want to use a WiFi network with a login screen (like Stanford networks), deselect "Configure Wireless LAN" and configure the WiFi after completing the rest of this setup guide and booting up the Raspberry Pi 5 with the USB drive.
    #. Change the locale settings as desired. 
    #. Go to the "Services" tab and check the "Enable SSH" box.
    #. Click "Save".

    .. image:: ../_static/pi_imager_os_customizations.png
        :align: center

#. Click "Yes" on OS customizations screen

    .. image:: ../_static/pi_imager_os_customization_screen.png
        :align: center

#. Click "Yes" again when it asks to confirm to flash

    .. image:: ../_static/pi_imager_conf.png
        :align: center

#. Once done flashing, insert the USB drive into one of the blue USB 3 ports on the Raspberry Pi 5 and you're done!


First-time setup
^^^^^^^^^^^^^^^^^

#. Turn on Pupper
#. Connect keyboard and mouse
#. Open a terminal on Pupper (control-alt-t) and run

    ``sudo chown -R pi /home/pi``

We are working to make this step unnecessary in the future.

###################################################

TODO