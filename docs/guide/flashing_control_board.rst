Flashing control board
------------------------

#. Download the control board firmware from `here <https://drive.google.com/file/d/1D_24V-na4hx1gnoLJxgpeXmecSkJCtj6/view?usp=drive_link>`_
#. Download the `STM32CubeProgrammer <https://www.st.com/en/development-tools/stm32cubeprog.html>`_
#. Connect your computer to the control board using a ST-link V2 programmer
#. Open STM32CubeProgrammer 

    .. image:: ../_static/flashing_control_board/stm32cubeprog.png
        :align: center
        :scale: 50%

#. Click "Open file" and select the ``SPIneV1.elf`` file you downloaded on step 1. You should see a screen like below:

    .. image:: ../_static/flashing_control_board/open_file.png
        :align: center
        :scale: 50%

#. Click "Download" to flash the board
#. Unplug the control board from the ST-link V2 programmer and you're done!