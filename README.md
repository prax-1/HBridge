# HBridge

## Project Overview
An H-bridge is an electronic circuit that switches the polarity of a voltage applied to a load. These circuits are often used in robotics and other applications to allow DC motors to run forwards or backwards

The term H-bridge is derived from the typical graphical representation of such a circuit. An H-bridge is built with four switches (solid-state or mechanical). When the switches S1 and S4 (according to the first figure) are closed (and S2 and S3 are open) a positive voltage is applied across the motor. By opening S1 and S4 switches and closing S2 and S3 switches, this voltage is reversed, allowing reverse operation of the motor.

Using the nomenclature above, the switches S1 and S2 should never be closed at the same time, as this would cause a short circuit on the input voltage source. The same applies to the switches S3 and S4. This condition is known as shoot-through.

![](/images/images.png)

This is the schematic which I have till now with several iterations, it is able to control motor direction with the help of just one SPDT switch on the right side, but the speed of the motor is low even after maximising it from the PWM generation side.

![Schematic](/images/schematic1.png)


In this project, I incorporated optocouplers to address a specific issue related to voltage behavior in the circuit. Initially, I encountered a problem where a floating resistor could unintentionally assume the voltage of the line it was connected to, due to Kirchhoff's Voltage Law (KVL). To mitigate this, I had a pull-down resistor placed between the SPDT switch and the signal wire to ensure the signal would pull down to ground when needed. However, I noticed that when the SPDT switch was in the off position, its inherent finite resistance acted as another resistor between VCC and the signal wire. This caused the signal to remain high instead of pulling down to ground as intended. By using optocouplers, I was able to isolate the control signal effectively, preventing the unwanted voltage elevation and ensuring reliable switching behavior. But still i am facing the problem of low voltage on the Gate side of the mosfets, I hope to solve it soon.

![](/images/s1.png)
![](/images/s2.png)



## License
This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Contribution
Feel free to fork this repository and contribute by submitting issues or pull requests.
