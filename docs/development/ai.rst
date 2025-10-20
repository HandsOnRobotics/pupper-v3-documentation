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

Setup
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

Functions
-------------

Conversation
^^^^^^^^^^^^^^
Backed by OpenAI's GPT-Realtime model, Pupper can chat with you about anything! Ask him about his homeworld Spoon, or what his favorite treat is! He's also fluent (with an embarassing accent) in English, Chinese, Dutch, French, German, Italian, Polish, Portugese, Hindi, Korean, Russian, Spanish, Swedish, and Turkish.

Vision
^^^^^^^^^^
With Google's Gemini model, Pupper can see through his camera and describe what he sees. Ask him to describe the room, what you're wearing, where the kitchen is, etc. 

Navigation
^^^^^^^^^^^^^^
Together with GPT-Realtime's prompt generation and the Gemini vision model, Pupper can navigate towards objects of interest. Ask Pupper to find the fire hydrant, or go to the door, etc.

Tricks
^^^^^^^^^^
Pupper knows a bunch of fun tricks including

* Sit
* Shake hand
* Lie down
* Twerk (his favorite)
* Swim
* Spider
* Sneeze
* Push ups
* Dance

Following mode
^^^^^^^^^^^^^^^^^^
Pupper can follow you around using vision. Say something like "activate walking mode and then follow me" and Pupper will start following the closest person in view. To exit following mode, say "deactivate following mode".

Known Issues
-----------------
* Sometimes the AI agent crashes or stops responding. There also seems to be an API limitation after ~20 minutes of use. Restart with ``sudo systemctl restart llm-agent`` or reboot the robot.
* Voice recognition will not work well in noisy environments.
* Person following mode will make Pupper follow the closest person in view, which may not be you.
* After doing a trick, Pupper will remain in trick mode and may not respond to other commands. To exit trick mode and return to walking mode, say "activate walking mode"
* Some tricks make Pupper fall over after completing them. In that case help Pupper back up please to avoid burning out motors due to high torque.
* The AI agent may take a while to respond depending on internet speed and server load.
* This is an early work in progress. Expect bugs and incomplete features!

How it works
----------------------
The AI system consists of several components working together:

* OpenAI GPT-Realtime model for audio understanding and tool usage. 
* Cartesia for speech output
* Google Gemini model for vision understanding and navigation.
* ROS2 robotics stack for locomotion and tricks.

Conversation
^^^^^^^^^^^^^^
The robot streams audio input to the GPT-Realtime cloud API where the LLM processes the audio and generates text responses. For normal conversation, the model just outputs text, which is read aloud by the Cartesia Sonic-2 text-to-speech cloud API.

Tool calling
^^^^^^^^^^^^^
If the GPT-Realtime AI thinks an action is appropriate (e.g. "move" or "look around"), then it will automatically output a special tool calling instruction rather than return normal conversational text. Tool calls are not read by Cartesia but instead executed by the robot software system to perform specific robot functions. For instance, the "move" tool will send velocity commands to the ROS2 navigation stack to move the robot. The "analyze_camera_image" tool will capture an image from the robot's camera and send it to the Google Gemini vision model for analysis. The response from the vision model is then fed back into the GPT-Realtime model as context for further conversation. Tricks are done by playing back pre-recorded motions stored on the robot.

Tool calling is an extremely flexible and powerful feature that allows us to extend the robot's capabilities by simply defining new tools that the AI can call. For example, letting the robot set its own speaker volume only took about 10 lines of code! Future tools could include searching the internet, doing special navigation, or even programming new behaviors on the fly!