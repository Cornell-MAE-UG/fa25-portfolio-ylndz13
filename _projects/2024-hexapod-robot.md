---
layout: project
title: Hexapod Robot
description: Making a hexapod from scratch and learning about the electrical system and code...
technologies: [C++, PCB, Inverse Kinematics, Power regulator circuit, CAD]
image: /assets/images/hexapod_v1_real.jpeg
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

I started building a personal hexapod robot project in the summer of 2024.

This project started out as an endeavor to learn about working with Arduino microcontrollers and setting up electrical components. I started out with a very simple ideal for the hexapod in CAD, then followed YouTube videos of other makers' hexapod projects and took inspiration from commercially-available hexapod designs to flesh out the design.


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

The new design thickens the joints, avoiding the need of using as many heated inserts and improving the printing accuracy. I also redesigned the bearing holder and changed its printing method to horizontal. As a short test of validation for the design, I ran some FEA simulations in ANSYS to make sure that the newly designed parts are able to withstand normal stress and potential torsion when the robot moves. I am working on modeling anisotropic (direction-dependent) 3D printed material properties in ANSYS FEA simulations.


<h5> Electrical: </h5>

I initially set up the electrical circuitry according to other maker's suggestions online: using a 3S Lipo battery, a buck stepdown converter board with jumper wires to two Adafruit PCA9685 servo controllers, and 18 heavy duty MG996R servo motors. It turns out that the servo motors experience occasional voltage spikes or cutouts that could be a result of unstable connection or insufficient current supplied to the servos. Therefore, I designed a custom power distribution board consisted of two 8A MP2238GD-Z buck converter ICs and their relevant circuitry, distributing power from the lipo battery to the servo motors on the hexapod and powering the two Adafruit PCA 9685 servo drivers. To decide on the MP2238GD-Z, I took into consideration maximum current rating, power dissipation rating, manufacturer location, cost, and solderability. 

Schematics:

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

Buck Converter Voltage Divider Resistors:
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

The slot in the copper pour is used to prevent the the noisy current from directly going to the connectors and forces the current to go through the decoupling capacitors, which reduces the noise in the power circuit. The performance of the board still needs to be tested and validated, as this is the first rev of the board. If there are still persistent overheating issues with the board's components, I may consider changing the board's thickness to 2oz copper instead.

The inductor is a noisy element in the circuit as its magnetic field can induce current in nearby traces. Therefore, it should be placed away from sensitive circuits like the feedback pin on the switching regulator IC. In the layout, we can see that the inductor is placed near the LED's circuitry, which is not a sensitive element to noise. 

<h5> Code: </h5>

I first wrote the code in the Arduino editor using the Servo.h library with pwm. As my code grew longer, I moved to VSCode with the PlatformIO extension. I also implemented interpolated inverse kinematics to control the robot's leg movements. The robot was able to move, but the servo positions displayed slight drifts in the values after each cycle. I am working on modifying the code to improve the accuracy of the motor.

I implemented inverse kinematics based on the position of the tip of the foot of each leg. I plotted a Bezier curve with the one control point $p_1$'s projection at the midpoint onto the line from $p_0$ to $p_2$. From the reference frame of the body of the robot, if the goal for the robot is to move from the tip of the robot's foot always moves along a plane that is parallel to vector $r_{A / B}$.

