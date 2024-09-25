Visualization using Foxglove Studio
===============================================

Steps
-----

1. Download Foxglove Studio to your personal computer `Foxglove Studio Download <https://foxglove.dev/download>`_.
2. Pull the latest `pupper_v3_description`
3. Source ROS and the workspace and run the stack (e.g., ``ros2 launch neural_controller launch.py``).
4. Source ROS and the workspace and run ``ros2 run foxglove_bridge foxglove_bridge``.
5. Open Foxglove Studio on your personal computer and choose "Open connection".
6. Connect to ``ws://pupper.local:8765``.
7. Download my `Foxglove layout file <>`_ to your personal computer (it sets up the viewers and panels nicely).
8. Load my Foxglove layout file by going to LAYOUT in the top right corner, and choosing the file.   
9. Enjoy!

.. image:: ../_static/foxglove.png
    :alt: Visualization of Pupper URDF in Foxglove Studio