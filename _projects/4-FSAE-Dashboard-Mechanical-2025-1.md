---
layout: project

title: FSAE Dashboard Mechanical

subtitle: Inventor, Harness Design, 3D printing

timeline: July 2025 – June 2026

description: Integrating the Dashboard PCB to the rest of the 2026 EV car

technologies: [Integration, Inventor, RapidHarness, Jig, Communication]

image: /assets/images/dash_dashboard.JPG

role: Powertrain Peripherals Part Designer

folder: project

excerpt: I designed the dashboard on our 2026 FSAE EV car. 

status: Completed

platform: Autodesk Inventor, RapidHarness, Altium 365

languages: C++

hero: /assets/images/dash_dashboard.JPG

in_main: true

summary: > 
    I designed the dashboard on our 2026 FSAE EV car. 

tags:

- Electromechanical Integration
- Inventor CAD
- RapidHarness
- Jig Design
- Communication

overview:
  The purpose of the dashboard is to display crucial information to the driver and people working on the car. The purpose of the dashboard on the 2026 car is to house the Dash PCB & screen, providing necessary electrical connections and a waterproof enclosure. In addition, Dash Mechanical displays drive-critical faults to drivers and holds the Estops & startup button. My part works closely around other parts, such as the dashboard screen and PCB, the monocoque (body of the car), and the low voltage harness. I also designed the mounting structure for the roll hoop estops this year.


contributions:

- Designed and fabricated a compact, 3D-printed dashboard enclosure in Autodesk Inventor around PCB, monocoque, and steering-column packaging constraints
- reducing wall thickness and fastener count while meeting rain-test requirements
- designed and routed the dashboard harness in RapidHarness for display, debugging, and fault information.
- Designed and fabricated drilling and welding jigs for FSAE vehicle integration, including locating dashboard mounting features on the carbon-fiber monocoque and AISI 4130 steel E-stop mounting tabs for welding to the rollhoop
- improved repeatability of hole placement and weld-tab alignment during assembly.


journey:

- title: Designing in CAD
  image: /assets/images/dash_assembly.png
  description: Initial mechanical concept.
  date: October 2025

- title: Harness Planning
  image: /assets/images/dash_rapidharness_schematic.png
  description: First walking robot.
  date: November 2025

- title: Harness Manufacturing 
  image: /assets/images/dash_harness_real.JPG
  description: Developed visualization dashboard.
  date: January 2026

- title: PCB Integration
  image: /assets/images/dash_board_integration.JPG
  description: Designed custom PCB.
  date: March 2026

- title: Dashboard on Car
  image: /assets/images/dash_mounted.JPG
  description: Integrated complete system.
  date: March 2024

challenges:

- icon: bi-journal-text
  title: Learning a New Technical Environment
  problem: Getting up to speed with tools on the team
  solution: Actively seeking help and asking questions to more experienced members

- icon: bi-people
  title: Resolving a CAD-to-Manufacturing Mismatch
  problem: The CAD of the monocoque was missing a fillet behind the dashboard panel the actual manufactured monocoque had
  solution: Revised PCB enclosure design by slanting the board and avoiding interference with the fillet to accommodate the change

- icon: bi-search
  title: Designing Under Evolving Requirements
  problem: The dashboard enclosure requirements changed throughout the fall as surrounding vehicle components and packaging constraints were finalized, requiring repeated updates to the design.
  solution: Maintained an adaptable design process by incorporating feedback quickly, tracking changing constraints, and revising the enclosure as vehicle-level requirements became clearer.

technologies:

#   - icon: bi-cpu
#     name: Arduino Mega
#     description: Main robot controller

#   - icon: bi-window
#     name: PyQt
#     description: Robot visualization dashboard

#   - icon: bi-diagram-3
#     name: KiCad
#     description: Custom PCB design

  - icon: bi-box
    name: Autodesk Inventor CAD
    description: Mechanical CAD

  - icon: bi-layers
    name: 3D Printing
    description: PLA structural components

  - icon: bi-gear
    name: RapidHarness
    description: Harness planning routing

  - icon: bi-gear
    name: Altium 365
    description: Harness planning schematic

  - icon: bi-code-slash
    name: C++
    description: Adding State of Charge to display


#   - icon: bi-battery-charging
#     name: Power Electronics
#     description: Buck converters & power distribution

#   - icon: bi-camera
#     name: AprilTags
#     description: Pose estimation

gallery:

- /assets/images/dash_enclosure_stackup.png
- /assets/images/dash_integration_monocoque.png
- /assets/images/dash_estop_jig_on_car.JPG
- /assets/images/dash_components.png

lessons:

- Early planning and over-communication prevent many later integration problems.
- Unexpected integration issues will occur, so leave enough time to troubleshoot.
- Take ownership of your work from cradle to grave by actively learning new tools and seeking help when needed.

---