# Controlling-Joystick-With-Arduino

![Screenshot (1161)](https://github.com/Arush-om/Controlling-Joystick-With-Arduino/assets/134673721/b46b0569-1cd5-445f-a9b9-6c8ce9aa57cb)

If you have hard-time 3d printing stuff and other materials which i have provided in this project please refer the professionals for the help, [JLCPCB](https://jlcpcb.com?from=ayu ) is one of the best company from shenzhen china they provide, PCB manufacturing, PCBA and 3D printing services to people in need, they provide good quality products in all sectors

[JLCPCB](https://jlcpcb.com?from=ayu)

Please use the following link to register an account in [JLCPCB](https://jlcpcb.com?from=ayu )

https://jlcpcb.com?from=ayu 


Pcb Manufacturing

----------

2 layers

4 layers

6 layers

jlcpcb.com/RNA


PCBA Services

[JLCPCB](https://jlcpcb.com?from=ayu ) have 350k+ Components In-stock. You don’t have to worry about parts sourcing, this helps you to save time and hassle, also keeps your costs down.

Moreover, you can pre-order parts and hold the inventory at [JLCPCB](https://jlcpcb.com?from=ayu ), giving you peace-of-mind that you won't run into any last minute part shortages. jlcpcb.com?from=ayu 


3d printing

-------------------

SLA -- MJF --SLM -- FDM -- & SLS. easy order and fast shipping makes [JLCPCB](https://jlcpcb.com?from=ayu ) better companion among other manufactures try out [JLCPCB](https://jlcpcb.com?from=ayu ) 3D Printing servies

[JLCPCB](https://jlcpcb.com?from=ayu ) 3D Printing starts at $1 &Get $54 Coupons for new users

The Analog Joystick is similar to two potentiometers connected together, one for the vertical movement (Y-axis) and other for the horizontal movement (X-axis). The joystick also comes with a Select switch. It can be very handy for retro gaming, robot control or RC cars. So let's understand how it works!
 
 The home position for the stick is at ( x,y:511,511). If the stick is moved on X axis from one end to the other, the X values will change from 0 to 1023 and similar thing happens when moved along the Y axis. On the same lines you can read position of the stick anywhere in upper half hemisphere from combination of these values.
 
![Screenshot (1165)](https://github.com/Arush-om/Controlling-Joystick-With-Arduino/assets/134673721/a4e3d703-abaa-442a-b976-c9c1fa360e63)
![Screenshot (1163)](https://github.com/Arush-om/Controlling-Joystick-With-Arduino/assets/134673721/d892c980-8ad9-49ed-ad1f-e98d86fd785f)
![Screenshot (1164)](https://github.com/Arush-om/Controlling-Joystick-With-Arduino/assets/134673721/3caadbb4-da04-4927-979e-0143c8730fa4)

The potentiometers act as voltage dividers. This module produces an output of around 2.5V from X and Y when it is in the resting position. Moving the joystick will cause the output to vary from 0v to 5V depending on its direction. If you connect this module to a microcontroller, you can expect to read a value of around 512 in its resting position (expect small variations due to tiny imprecisions of the springs and mechanism). When you move the joystick you should see the values change from 0 to 1023 depending on its position. The given example values are for a 5V microcontroller or a development board with 10bit ADC resolution like Arduino UNO or nano

The Joystick itself only contains the two potentiometers for each axis and a switch to register the click. One side of the potentiometers is connected to the ground and the other to the VCC. The center pins are connected to the VRx and VRy pins respectively. Similarly, the switch is connected between the GND and the SW pins. And in some modules, there is also an unpopulated space for a pull-up resistor on board for the switch.

![Screenshot (1169)](https://github.com/Arush-om/Controlling-Joystick-With-Arduino/assets/134673721/98433291-36ae-46d8-8dbd-d4bff06e345a)


If your Joystick module is not working properly the first and important step is to make sure all the connections are correct. Once the connections are verified, we can move forward to the next diagnosing step. If the reading from the VRx and VRy is not proper or it jumps around too much, then there must be a problem with the potentiometers. You can gently pop the potentiometers out of their default position by lifting them slightly. Give them a good clean using IPA or a similar cleaning solution and then pop them back in, to see if this has fixed the issue. If not either replace the potentiometer or the module itself.

The sketch starts by defining the connections to the Joystick module. The SW pin is connected to Arduino’s Pin A2 while the VRx and VRy pins are connected to Analog pins A0 and A1.

#define Xaxis_pin A0 // Arduino pin connected to the VRx Pin
#define Yaxis_pin A1 // Arduino pin connected to the VRy Pin
#define SW_pin A2 // Arduino pin connected to the SW Pin
In the setup() function, we initialized the SW pin as an input and keep it HIGH. This is as same as declaring the pin as INPUT_PULLUP. When the switch is pressed, this pin will be pulled to the ground. Thus, we can detect the button press by monitoring the state of this pin. We have also initialized the serial communication so that we can print all the necessary information into the serial monitor.

void setup() {
  pinMode(SW_pin, INPUT);
  digitalWrite(SW_pin, HIGH);
  Serial.begin(9600);
}
In loop() function, we continously read the value of SW pin using digitalRead() function, VRx & VRy pin using analogRead() and display on serial monitor.

void loop() {
  Serial.print("X-axis: ");
  Serial.print(analogRead(Xaxis_pin));
  Serial.print(" : ");
  Serial.print("Y-axis: ");
  Serial.print(analogRead(Yaxis_pin));
  Serial.print(" : ");
  Serial.print("Switch:  ");
  Serial.println(digitalRead(SW_pin));
  delay(200);
}
Joystick module Interfacing with Arduino
The below GIF shows how we have interfaced the Joystick module with the Arduino. As you can see as soon as I move the joystick, the corresponding values are displayed on the serial monitor.

Applications like video games that require a change in cursor position in a 2-D plane make use of analog joysticks as input devices.

Analog joystick produces two voltages; one corresponding to position with respect to X-axis and another corresponding to the position with respect to Y-axis. The voltages produced depend on the position of the joystick.

For more information about Analog Joystick and how to use it, refer the topic Analog Joystick in the sensors and modules section.

To interface the Analog Joystick with Arduino Uno, we need to use ADC on the microcontroller of the Arduino UNO board.

![Screenshot (1171)](https://github.com/Arush-om/Controlling-Joystick-With-Arduino/assets/134673721/e246aad3-533c-4726-8c71-ecd4e61697da)
![Screenshot (1170)](https://github.com/Arush-om/Controlling-Joystick-With-Arduino/assets/134673721/6e0eef52-d46e-47c3-a7af-6bf33b9ef592)


Applications like video games that require a change in cursor position in a 2-D plane make use of analog joysticks as input devices.

Analog joystick produces two voltages; one corresponding to position with respect to X-axis and another corresponding to the position with respect to Y-axis. The voltages produced depend on the position of the joystick.

For more information about Analog Joystick and how to use it, refer the topic Analog Joystick in the sensors and modules section.

![Screenshot (1172)](https://github.com/Arush-om/Controlling-Joystick-With-Arduino/assets/134673721/6d9c6403-7809-4cf0-acdf-a211322aa984)

To interface the Analog Joystick with Arduino Uno, we need to use ADC on the microcontroller of the Arduino UNO board.

Connect your Leonardo board to your computer with a micro-USB cable. The pushbutton is connected to pin 6. If you're using a part like the Joystick shield pictured below, you may not need a pulldown resistor. The x-axis on the joystick is connected to analog in 0, the y-axis is on analog in 1.
