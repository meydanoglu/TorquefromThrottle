In the world of this code, there are two sensors that simultaneously watch how much the torque pedal on an electric car is pressed. the `getTorqueFromThrottle` function gets the inputs `(int t, int input[])` , t being the maximum torque (N/m) of the nonexistent electric car and the input array consists of 4 values:

**input[0] = most significant byte of sensor 1  
input[1] = least significant byte of sensor 1  
input[2] = most significant byte of sensor 2  
input[3] = least significant byte of sensor 2**

With these known, we get a fraction of how much the pedal is pressed, and then calculate the corresponding torque value. 
