Technical Specifications
=========================

Design
----------
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
* Steadywin GIM4305 actuators
  
  * 4005 brushless motor
  * 10:1 planetary gearbox
  * ~ 3.5 Nm peak torque
  * ~ 1.0 Nm continuous torque with air cooling
  * ~ 30 rad/s max speed
  
* Custom 200W FOC motor drivers
  
  * Based on MIT Cheetah motor drivers
  * Features TI DRV8316 integrated gate driver and FETs. 8A, 40V rated.
   
* 9g servo motors to actuate the ears

Sensors
-----------
* 6DOF BNO086 IMU
* IMX296 222deg FOV fisheye camera in the nose
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
