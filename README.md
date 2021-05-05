# excavator_hw_interface
* Changes from main
    * velocity and effort commands bug identified but not tested
    * joint state handle variables initialized to zero
* TODO identify and fix wrist joint_state issues
    * Measured wrist position is not propagated into /joint_states
    * Occasionally the wrist pose was reporting initial joint values on the order of 10e150, my theory is that the joint state variables were uninitialized and the previously mentioned bug is not overwriting that value with the encoder position.
