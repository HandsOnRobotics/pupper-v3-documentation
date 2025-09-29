Using Pupper AI (work in progress)
======================================

Requirements
--------------

* USB wireless microphone
* Speaker works (test in terminal with ``speaker-test``)
* Camera works

    * Test in terminal with

        .. code-block:: console

            sudo systemctl stop robot
            DISPLAY=:0 rpicam-hello
            [after verifying]
            sudo systemctl start robot

* Internet connection (test in terminal with ``ping google.com``)
* Google, Cartesia, and OpenAI API keys

Steps
-------

#. Download the AI-enabled image (named ``pupOS_pios_ai_[version]``) from this `Google Drive folder <https://drive.google.com/drive/u/0/folders/1DHN-1TVXteCB5OA0ngWWJe6-_iPYVCHJ>`_
#. Flash using RaspberryPi OS Imager (see :doc:`../guide/software_installation`)
#. Boot Pupper 
#. SSH to Pupper and configure API keys

    * ``cd /home/pi/pupperv3-monorepo/ai/llm-ui/agent-starter-python``
    * ``cp .env.example .env.local``
    * Add your keys to the .env.local file: ``nano .env.local``

#. Restart llm-agent: ``sudo systemctl restart llm-agent``
#. Pupper should say a greeting like "Hi I'm Pupster!"
#. Tell Pupster to do a trick like "shake my hand"
#. Ask Pupster what it sees