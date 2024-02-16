#include <bits/stdc++.h> 
#include <math.h>        

using namespace std;     


float getTorqueFromThrottle(int t, int input[]) {
    float output = 0; 
    int resolution = 65535;

    // Calculate 16 bit values from the two sensor inputs. 16 bit = MSB * 256 + LSB
    int sensor_value_1 = input[0] * 256 + input[1];
    int sensor_value_2 = input[2] * 256 + input[3];

    // Return torque output = 0 if values differ by more than 10% of the resolution
    if (fabs(sensor_value_1 - sensor_value_2) > resolution / 10) { 
        return output; 
    }

    float sensor_avg = (sensor_value_1 + sensor_value_2) / 2;

    // Scale the average sensor value to a fraction
    float sensor_fraction = sensor_avg / resolution;

    // if the pedal is pressed 10 percent or less, therefore sensor fraction <= 0.1, return torque output = 0
    if (sensor_fraction <= 0.1) { 
        return output; 
    }
    
     // If more than 10 percent of the pedal is pressed, return corresponding torque
    float torque_fraction = ((sensor_fraction) - 0.1) / 0.9; // offset then scale, therefore there won't be an instant torque of 10 percent once the pressed pedal percentage exceeds 10.
        output = torque_fraction * t; 
        return round(output * 1000) / 1000; //round the number with 3 decimals
}

int main() {
    int t; 
    int inputArr[4]; 

    cin >> t; 

    for (int i = 0; i < 4; i++) {
        cin >> inputArr[i]; 
    }

    cout << getTorqueFromThrottle(t, inputArr); 

    return 0;
}
