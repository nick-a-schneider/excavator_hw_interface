# excavator_hw_interface
main branch (should) be identical to the package used to create the following list of errors
* We can confirm the encoder signs are correct, we have the arm in rviz mimicking the phyisical arm with remote control with a couple problems	
    * 1.1 the encoders are still showing drift but not as severely
    * 1.2 the measured wrist position is not propagated into /joint_states (probably a hardware interface bug, still needs fixed)
    * 1.3 Occasionally the wrist pose was reporting initial joint values on the order of 10e150, my theory is that the joint state variables were uninitialized and the previously mentioned bug is not overwriting that value with the encoder position. 
* We were able to plan motions but there was a bug (see effort_control branch for progress) in the hardware interface that blocked writing velocity commands so the arm did not move. Weirdly, the motion planning interface in rviz reported a successful execution.
* Using the effort controller threw a number of errors on the nano that I cannot recreate on my machine,  I suspect they relate to the 1.2 bug
