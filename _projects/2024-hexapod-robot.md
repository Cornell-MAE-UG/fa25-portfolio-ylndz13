---
layout: project
title: Hexapod Robot
description: Making a hexapod from scratch and learning about the electrical system and code...
technologies: [Inverse Kinematics, Power regulator circuit, CAD, C++, PCB, Arduino]
image: /assets/images/hexapod_v1_real.jpg
---

<script>
  MathJax = {
    tex: {
      inlineMath: [['$', '$'], ['\\(', '\\)']],
      displayMath: [['$$', '$$'], ['\\[', '\\]']]
    }
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js" defer></script>

I began building a personal hexapod robot project in the summer of 2024.

This project started out as an endeavor to learn about working with Arduino microcontrollers and setting up electrical components. I started out with a very simple idea for the hexapod in CAD, then followed YouTube videos of other makers' hexapod projects and took inspiration from commercially-available hexapod designs to flesh out the design.


<h5> Structure: </h5>

Having done CAD on my high school FIRST robotics team, I designed the robot's mechanical structure in OnShape in June of 2024. I set out to 3D print the components at a local maker club in Boston. The makerspace was a 2-hr roundtrip commute away, but the printers were the best I could get access to at the time, so the effort was worth it.

My initial thought with the assembly of the hexapod was to bolt the components together to form the necessary joints. This idea turned out to allow too much space for imprecision, like heated inserts and printing issues. In addition, I also ran into the issue that the cylinders for holding the bearings in place are very easy to break off after they are printed. Therefore, I ended up redesigning a new rev of the hexapod's structure.

<div class="vertical-evolution">
  <img src="{{ '/assets/images/hexapodv0.png' | relative_url }}"
     style="display: block; width: 60%; margin: 0rem auto;" alt="Initial design">
  <figcaption>Hexapod design concept</figcaption>

  <div class="arrow-down">↓</div>
  <img src="{{ '/assets/images/hexapodv1.png' | relative_url }}"
     style="display: block; width: 60%; margin: 0rem auto;">
  <figcaption>Hexapod design rev 1</figcaption>

  <div class="arrow-down">↓</div>
  <img src="{{ '/assets/images/hexapodv2.png' | relative_url }}"
     style="display: block; width: 60%; margin: 0rem auto;">
  <figcaption>Hexapod design rev 2</figcaption>
</div>

The new design thickens the joints, avoiding the need of using as many heated inserts and improving the printing accuracy. I also redesigned the bearing holder and changed its printing method to horizontal. As a short test of validation for the design, I ran some FEA simulations in ANSYS to make sure that the newly designed parts are able to withstand normal stress and potential torsion when the robot moves. 

<div class="two-images">
  <img src="{{ '/assets/images/bearing_holder_cad.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">

  <img src="{{ '/assets/images/bearing_holder_slicer.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">
</div>
<figcaption>Improved bearing holder in CAD and in 3D printing slicer</figcaption>

Intuitively, the new printing orientation should not be as breakable as the previous, upright print orientation. I am working on modeling anisotropic (direction-dependent) 3D printed material properties in ANSYS FEA simulations.

Fasteners were not added into the assembly as they make the browser incredibly slow.

<h5> Electrical: </h5>

I initially set up the electrical circuitry according to other maker's suggestions online: using a 3S Lipo battery, a buck stepdown converter board with jumper wires to two Adafruit PCA9685 servo controllers, and 18 heavy duty MG996R servo motors. It turns out that the servo motors experience occasional voltage spikes or cutouts that could be a result of unstable connection or insufficient current supplied to the servos. Therefore, I designed a custom power distribution board consisted of two 8A MP2238GD-Z buck converter ICs and their relevant circuitry, distributing power from the lipo battery to the servo motors on the hexapod and powering the two Adafruit PCA 9685 servo drivers. To decide on the MP2238GD-Z, I took into consideration maximum current rating, power dissipation rating, manufacturer location, cost, and solderability. 

**Schematics**

  <img src="{{ '/assets/images/hex_sch.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">
  <figcaption>Logic level schematic</figcaption>

  <img src="{{ '/assets/images/hex_buck_sch.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">
  <figcaption>Buck regulator schematic</figcaption>

The majority of the connections in the schematic are suggestions by the datasheet, or circuitry of the servo controllers. Aside from the buck converter, voltage is stepped from 5.5V to 5V through a resistor voltage divider. 

<h5> Component Selection: </h5>

**Decoupling Capacitors:**

I used the same decoupling capacitors as the ones suggested in the MP2238GD-Z datasheet. This IC alraedy contains a Schottky diode, so no extra diode is included in the schematic. I calculated the inductor value with the following formula:

**Inductor:**
\\[L_1 = \frac{V_{OUT} \times (V_{IN} - V_{OUT})}{V_{IN} \times \Delta I_L \times f_{OSC}}\\]

where the inductor ripple current is given as $30\\%$ of the maximum load current. So $\Delta I_L = 30\\% \times 8A = 2.4 A$. $V_{IN} = 11.4V$, $V_{OUT} = 5.5V$, $f_{OSC} = 600kHz$

\\[L_1 = \frac{5.5 V \times (11.4 V - 5.5 V)}{11.4 V \times 2.4 A \times 600,000 Hz} = 1.98 \mu H\\]

A $2 \mu H$ inductor should suffice. Then we need to determine the maximum current rating:

The maximum current through the switching regulator is 8A. The inductor's maximum current should not exceed $8A + \frac{2.4A}{2}=9.2A$. To be safe, I wanted a $50\\%$ margin over the maximum current, which is $13.8A$.

**Buck Converter Voltage Divider Resistors:**

The values for $R39$ is given by the equation $\frac{R38}{\frac{V_{OUT}}{0.6 V}-1}$. The datasheet suggested a $100 \; k\Omega$ resistor for the an output of 5V. Assuming that $R38 = 100 \; k\Omega$, Plugging in the conditions for this circuit yields $R39 = \frac{100 \; k\Omega}{\frac{V_{OUT}}{0.6 V}-1}=12.244 \; k\Omega$. Therefore, I picked $12.3 \; k\Omega$ resistors for $R39$ and $R45$.

**Layout:**

<div class="two-images">
  <img src="{{ '/assets/images/pcb_top.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">

  <img src="{{ '/assets/images/pcb_bot.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">
</div>
<figcaption>Power distribution PCB layout</figcaption>

The main challenge was laying out the board in a way to minimize noise from the switching regulator and inductor, and handling the high current the servo motors draw. My first step was to determine the trace size for the PCB using the [formula](https://resources.altium.com/p/how-calculate-pcb-power-plane-current-capacity):

\\[A=6.452 \cdot 10^{-4} \left( \frac{I}{k(\Delta T)^{0.44}} \right)^{1.3793} \frac{Amp}{mm^2 \cdot \; ^\circ C}\\]

Where $k = 0.048$ for the external layer and $k = 0.024$ for the internal layer. Therefore, if I want to use an two-layer, 1oz copper layer thickness board, and I want a trace that has a maximum temperature increase of $20^\circ C$, then

\\[A=6.452 \cdot 10^{-4} \left( \frac{6}{0.048(20)^{0.44}} \right)^{1.3793} \frac{Amp}{mm^2 \cdot \; ^\circ C}\\]
\\[A_{6A}=0.08827mm^2\\]

So the trace width is $\frac{0.08827mm^2}{0.035mm}=2.522mm$

If the temperature rise is $30 ^\circ C$,

\\[A=6.452 \cdot 10^{-4} \left( \frac{6}{0.048(30)^{0.44}} \right)^{1.3793} \frac{Amp}{mm^2 \cdot \; ^\circ C}\\]
\\[A_{6A}=0.06879mm^2\\]

So the trace width is $\frac{0.06879mm^2}{0.035mm}=1.9654mm$

The slot in the copper pour is used to prevent the the noisy current from directly going to the connectors and forces the current to go through the decoupling capacitors, which reduces the noise in the power circuit. The performance of the board still needs to be tested and validated, as this is the first rev of the board. If there are still persistent overheating issues with the board's components, I plan to adjust the layot of the components on the 11.4V trace use a separate copper pour instead of a trace (last resort is changing the board's thickness to 2oz copper).

The inductor is a noisy element in the circuit as its magnetic field can induce current in nearby traces. Therefore, it should be placed away from sensitive circuits like the feedback pin on the switching regulator IC. In the layout, we can see that the inductor is placed near the LED's circuitry, which is not a sensitive element to noise. 

<h5> Code: </h5>

More specific code can be found at my GitHub [repository](https://github.com/ylndz13/HexapodCode): 

I first wrote the C++ code in the Arduino editor using the Servo.h library with hard-coded pwm values. The robot walked well, but I was limited to a narrow range of movement possibilities and could not interact with the robot. For the current version of the code (v2), I implemented interpolated inverse kinematics to control the robot's leg movements based on the position of the tip of the foot of each leg. In addition, I moved to the PlatformIO extension on VSCode for more comprehensive debugging and development functionalities. 

**Device Setup:**

<img src="{{ '/assets/images/device_setup.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">

Each servo is of type `servoConfig`. The struct includes servo information like the max and min position the servos can turn to (displayed in terms of pwm) and the Adafruit servo driver number. The midValue variable represents the angle when the servo is moved by $90 ^\circ$. Since each servo has a slightly different max and min rotation position, I declared a constructor to initialize the servo parameters to each specific servo and move the servo by converting the specified angle into pwm. 

The hexapod is abstracted as an instance of the `Robot` class. A `Robot` has 6 `Leg` objects, where 3 `servoConfig` is declared for the Coxa, Femur, and Tibia. The `Robot` class contains member functions that record and update the robot's position relative to where it was initialized. The `Leg` class's member functions calculate the destination coordinate based on Inverse Kinematics, interpolate the points on the path, and move the servos correspondingly.

**Inverse Kinematics:**

<img src="{{ '/assets/images/IK.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">

The member function `calculateIK()` takes in two parameters: the robot's destination's coordinate `target` and the current coordinate `current`. The angles `theta`, `alpha`, `beta` respectively represent the Coxa, Femur, and Tibia servo's deviation from their `midVal` parameter. 

<img src="{{ '/assets/images/theta.jpeg' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">

The calculation for `theta` is quite simple. An `atan2(target.y, x-y plane projected length of the leg)` call returns the value for `theta`, the angle between the current position of the hexapod's foot and the Coxa servo's `midVal`. For convenience of calculation, the variable `projectedLength` is declared to represent the x-y plane projected length of the leg.

<img src="{{ '/assets/images/alpha_beta.jpg' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">

`alpha` is the angle between the midVal of the Femur motor and Femur of the leg. 
Law of Cosines gives:
\\[b^2 = a^2 + c^2 - 2ac \cdot cos(\alpha + \alpha ^{\prime})\\]

\\[ \alpha^{\prime} = tan^{-1} \left(\frac{z}{pL}\right) = atan2(z,pL) \\]

\\[\alpha + \alpha ^{\prime} = cos^{-1} \left(\frac{a^2 + c^2 - b^2}{2ac}\right)\\]
\\[\alpha = cos^{-1} \left(\frac{a^2 + c^2 - b^2}{2ac}\right) - atan2(z,pL)\\]

To calculate the projectedLength (`pL`) of the leg at the target location: `pL = target - current + footLoc`. $z$ is just the z-coordinate of the robot's foot at the target location.

`beta` is the angle between the Femur and the line connecting the point on the axis of rotation of the tibia motor to the foot of the hexapod. Based on Law of Cosines and the diagram above,

\\[\beta = cos^{-1} \left( \frac{a^2 + b^2 - c^2}{2ab} \right)\\]

**IK Bezier Curve &  Interpolation:**

<img src="{{ '/assets/images/interpolate.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">

Each foot tip's movement follows an interpolated Bezier curve. I plotted a symmetric Bezier curve with the one control point with a height of $0.3$ of the total distance between the tip of the foot and the coordinate of the leg. The code moves along the line joining the current and target `x` and `y` coordinates. For the `z` coordinate, the following equation was used:

$$\begin{aligned}
&(1-t)((1-t)(0.3tl) + 0.3tl((1-t) + 0.3tl)) \\
     &\quad + 0.3tl((1-t)((1-t) + 0.3tl) + 0.3tl((1-t) + t \cdot targetZ))
\end{aligned}
$$

Where $l$ is the length from the leg's origin at the coxa to the tip of the foot. And targetZ is the z-coordinate of the target point the robot's foot will move to.

Interpolating the results of the Inverse Kinematics calculations is fairly simple. I declared an array of type `Vector3` named `interpolation`. The interpolated points are added to an array `interpolation`. The result of the interpolation is a series of points that the robot's foot can follow to proceed to the target position. To actually advance moving the robot, the code simply interpolates the straight line connecting the target coordinate with the zero coordinate and carry out the necessary movements.

**Code Testing:**

I first tested the board without driving the servo motors to eliminate causing problems with the hardware. I traced the code through a series of print statements inside each function call and deployed the code on the Arduino Mega board. This method of testing turned out to be very helpful as I was able to debug a significant portion of my code without needing access to the physical hexapod. A large amount of print statements did cause the program to run slower than my expectation, so I had to adjust the amount of delay in the code after integrating the code with the robot. 

I made a coordinate tracker based on the output of the program and compared the actual behavior to the expected behavior of the foot coordinates.

To protect the servos from stalling due to bugs in the code, I limited the maximum turning angle of the servo to between $0^\circ$ and $180^\circ$

**Current Results:**

The robot was able to move, but the servo positions displayed slight drifts in the values after each cycle. I am working on modifying the code to improve the accuracy of the motor.

**Work In Progress:**

Now that I am equipped with formal C++ knowledge thanks to taking CS 2024, I plan to rework my code's data encapsulation and split the Movement.cpp file into the actual classes with proper header files. I also aim to declare the `servoConfig` virtual and declare `Coxa`, `Femur`, and `Tibia` classes to implement the virtual methods in `servoConfig` to reduce member function redundancy. 

Once the power distribution PCB and its components arrive, I am going to bring up the board and test its functionalities (super exciting). 

I also want to see how the new bearing shaft 3D prints interact with the servo motors during the hexapod structure assembly.

Thank you for reading!