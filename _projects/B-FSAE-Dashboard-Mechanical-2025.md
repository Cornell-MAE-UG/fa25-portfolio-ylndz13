---
layout: project
title: FSAE Dash Mechanical (2025)
description: Integrating the Dash PCB to the rest of the car
technologies: [Integration, Inventor, RapidHarness, Jig, Communication]
image: /assets/images/dash_assembly.png
folder: project
---

<h5> Overview:</h5>

• Integration \\
• Designed in CAD \\
• Communication with other subteams --- Ergonomics, Monocoque, Firmware \\
• Improved on past years' designs \\
• Planned & manufactured dash harness using on RapidHarness \\
• Created jigs for drilling into the monocoque \\
• 3D printed waterproof enclosures to integrate dashboard screen & PCB 

The purpose of the dashboard is to display crucial information to the driver and people working on the car. The purpose of the dashboard on the 2026 car is to house the Dash PCB & screen, providing necessary electrical connections and a waterproof enclosure. In addition, Dash Mechanical displays drive-critical faults to drivers and holds the Estops & startup button. My part works closely around other parts, such as the dashboard screen and PCB, the monocoque (body of the car), and the low voltage harness. I also designed the mounting structure for the roll hoop estops this year.

<h5> Mechanical Enclosure: </h5>
<img src="{{ '/assets/images/enclosure_stackup.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">

The Dash enclosure is split into two parts: the screen lid and the PCB enclosure. The entirety of the enclosure is secured through four flathead M3 bolts. The design choice behind using flathead M3 bolts is to maintain the flat aesthetic of the screen lid of the enclosure.

The waterproofing is achieved by countersinking the screen lid and using gaskets at the enclosure’s interfaces with the screen and the monocoque. The enclosure needs to achieve the NEMA class 6 water intrusion standard. There are three gaskets currently in this version of the enclosure:

1. A gasket between the screen lid and the screen
2. A gasket between the screen lid and the monocoque
3. A gasket between the PCB enclosure and the monocoque. 


<h5> Integration</h5>

<div class = "two-images"> 
<img src="{{ '/assets/images/integration_monocoque.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">
<img src="{{ '/assets/images/integration_pcb.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">
</div>

The screen lid sandwiches the monocoque’s dashboard panel in the middle with the PCB enclosure. 4x M3 35mm flat head hex key bolts are used to connect to the heat-set inserts on the PCB enclosure. A gasket goes on either side of the dashboard panel for waterproofing purposes. Precision is needed for heat-set inserts so the bolt and insert threads align during installation. The fault lights and the startup button will be bonded to the monocoque after the holes for the fault lights are drilled.

The PCB enclosure will undergo slight modifications to ensure fitment inside the monocoque (work in progress).

<h5>Estop Mounts:</h5>
<div class = "two-images"> 
<img src="{{ '/assets/images/estop_integration.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">
<img src="{{ '/assets/images/estop_jig_on_car.JPG' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">
</div>
<figcaption>Estop mount on the car (right: after welded on car using jig)</figcaption>


The roll hoop estops will be welded onto the estop through mounting plates. The mounting plates are 0.125-inch-thick 4130 steel plates.

<h5>Electrical Harnessing:</h5>

The harnessing connections underwent a series of changes throughout the design season as sensors were adjusted. 

<img src="{{ '/assets/images/dash_harness_from_altium.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">

<img src="{{ '/assets/images/rapidharness_schematic.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">

<div class = "two-images"> 
<img src="{{ '/assets/images/rapidharness_page1.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">
<img src="{{ '/assets/images/rapidharness_page2.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">
 </div>
The harnessing connections to the fault lights and buttons were designed in RapidHarness and manufactured by me based on the dimensions in RapidHarness. 

<img src="{{ '/assets/images/dash_harness_real.JPG' | relative_url }}"
     style="display: block; width: 80%; margin: 0rem auto;">

This is a photo of the dashboard harness after I manufactured it. The wires are bundled, wrapped in black overwraps, and taped with Scotch 69 tape to protect the wires from accidental damage. 


<h5>Bill of Materials</h5>

<img src="{{ '/assets/images/components.png' | relative_url }}"
     style="display: block; width: 100%; margin: 0rem auto;">

Some more thought went behind the selection for the button, as according to last year, the startup button got jammed after someone pressed it too hard, so this year I looked for IK10 (maximum spring force rating) in addition to the waterproof rating.