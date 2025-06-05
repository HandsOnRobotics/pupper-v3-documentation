Technical Specifications
=========================

Design
----------
* `Onshape CAD model <https://cad.onshape.com/documents/97a1bc3e752ec66822dbb5bb/w/c7f9232ccbc53a2e3f6ee909/e/74c0b3caf828b9fd1994bcd6?renderMode=0&uiState=683be4f0c59fb554ee1111a4>`_
* `Fusion 360 model <https://a360.co/4kD64eX>`_

* 12 degrees of freedom, 3 in each leg
* 3kg weight
* Dimensions in crouched position

  * 25cm length
  * 20cm height
  * 22cm width

Compute
---------
* Raspberry Pi 5 8gb
* M.2 slot available for AI accelerator

Actuators
-------------------------
* `Steadywin GIM4305 actuators <https://aifitlab.com/products/pupper-v3-stanford-open-source-robotics-dog>`_

  * 4005 brushless motor
  * 10:1 planetary gearbox
  * ~ 3.5 Nm peak torque
  * ~ 1.0 Nm continuous torque with air cooling
  * ~ 30 rad/s max speed
  
* 9g servo motors to actuate the ears

Sensors
-----------
* `6DOF BNO086 IMU <https://www.digikey.com/en/products/detail/ceva-technologies-inc/BNO086/14114190>`_ 
* `IMX296 222deg FOV fisheye camera <https://www.arducam.com/1-58mp-imx296-color-global-shutter-camera-module-with-m12-lens-for-raspberry-pi.html>`_ in the nose 
* Microphone for voice interaction
* Motor drivers report actuator angles, velocities, and efforts
* Battery voltage ADC

Extras
---------
* 4"x4" LCD for showing expressive facial animations and for debugging
* 3W speaker located behind the nose for voice interaction

.. Fusion 360 CAD model: https://a360.co/2TEh4gQ

.. .. raw:: html
    
..     <iframe src="https://stanford195.autodesk360.com/shares/public/SH919a0QTf3c32634dcfedf61e031f673710?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>


.. Power distribution pcb files: https://github.com/stanfordroboticsclub/Pupper-Raspi-PDB/
