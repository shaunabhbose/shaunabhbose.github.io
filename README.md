# TableTop Robot
An autonomous wanderer robot that doesn't fall off a table using infrared light detection as a method to detect a ledge. 

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Shaunabh B | San Mateo High School | Electrical Engineering | Incoming Sophomore



![My picture](https://res.cloudinary.com/dbuxx0uql/image/upload/v1658507278/imageedit_1_6629666651_mixafw.jpg)


  
# Final Milestone
My final milestone was to build my [Circuit Board](https://github.com/BlueStamp-Engineering-2022/Shaunabh_BSE_Project/blob/5280e6982704084b1eadb624ecee7482036e9ace/Screenshot%202022-07-23%20180512.png) and build the actual robot so that I can see if it works normally. To build the circuit board I just had to put the same connections using soldering from my breadboard to a perfboard, which is a copper board with pre-drilled holes on a grid to help make a prototype circuit board. My first prototype circuit board did not work since I had multiple shorts so I had to make another prototype which worked later. I used [online instructions](https://www.instructables.com/Tiny-Wanderer-A-Table-Top-Robot/) to make the structure of the robot. Something I enjoyed about reaching this milestone was to create my first successful circuit board and making the structure of the robot. Something I stuggled with was the dimensions since they were smaller than the appropriate size so I had to sand some parts to make my screws fit and also my first prototype for the first infrared sensors didn't work so I had to use premade infrared sensors.

[![Milestone 2](https://res.cloudinary.com/dbuxx0uql/image/upload/v1658357735/20220718_140007_qjumzk.jpg)](https://drive.google.com/file/d/1E8m4sUgNkT43bxaO3-BHYKa17fetpoio/view?ts=62e16545)
*click on image for linked video*
# First Milestone
My first milestone was to create a working prototype using a breadboard. The breadboard contains the ATtiny microcontroller, servo motors, the infrared LEDs and phototransistors which act as the infrared sensor. I used this [schematic](https://github.com/BlueStamp-Engineering-2022/Shaunabh_BSE_Project/blob/f8d4d848aaaa821004db3e821adecc59988f2757/Schematic.pdf) to make the appropriate connections between components. I also used an arduino board to [code the function of the infrared sensors and the movement of the servos.](https://github.com/BlueStamp-Engineering-2022/Shaunabh_BSE_Project/blob/a1d07006e6e79339a3740421a67f5c24dbfb9e40/Tabletop_robot.ino) The infrared LEDs would normally shine onto a tabletop which would be picked up by the phototransistors which does the sensing part of the robot. If at any point, one of these transistors stops detecting infrared light it would tell the alternating servo to reverse so that it goes back to detecting infrared light. Something I enjoyed about making this is learning breadboarding and coding on arduino. Something I struggled with was breadboarding since I had no insight on this and it was my first time doing it and learning it was really fun my next steps would be to build my PCB and build the actual robot so that I can see if it works normally.
[![Milestone 1 Wiring](https://res.cloudinary.com/dbuxx0uql/image/upload/v1657554964/20220708_112955_uhk9om.jpg)](https://www.youtube.com/watch?v=vzuAO6n93tA "Shaunabh Milestone 1")
*click on image for linked video*
# Starter Project
My starter project is the TV-B-Gone. It switches off Televisions when you point it at the infrared receiver on the TV. The TV-B-Gone emits a pulse of infrared light that is invisible to the human eye, which is picked up by a television's receiver, and turns it off. The microcontroller, or the computer that helps the TV-B-Gone work, was pre-programmed. I soldered all of the components in the right places to assemble it. The switch at the bottom of the circuit board restarts the TV-B-Gone. The green LED next to it, flashes to show if the device is switched on. The resistor right above it reduces the current flowing to the VCC(Common collector voltage) and GND(ground) of the microcontroller. The ceramic oscillator on the circuit board vibrates to generate an oscillating signal of a specific freqency for timing the on/off pattern of the infrared light. The microcontroller then sends the current through the four transistors to amplify the current to send it to the LED placed in front of it. The LEDs then emit the infrared signal. During this project, something I struggled with is soldering good joints since this was my first soldering experience. Additionally, the original ceramic oscillator that the TV-B-Gone kit was sent with was defective which prevented it from working. The wires on the battery pack kept snapping, so I had to solder a new wire entirely. Something I enjoyed about this project is discovering fixes to the project even when it seemed like it wouldn't work again and soldering.

[![Shaunabh Starter Project](https://res.cloudinary.com/dbuxx0uql/image/upload/v1657728809/20220708_115729_lcatec.jpg)](https://www.youtube.com/watch?v=WTV-NTjOOtQ "Shaunabh Starter Project")
*click on image for linked video*
