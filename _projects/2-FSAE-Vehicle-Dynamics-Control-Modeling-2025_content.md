---
layout: project

title: FSAE Vehicle Dynamics Controls

subtitle: Vehicle Dynamics • MATLAB • Controls

timeline: July 2026 – Present

role: Part Designer

Status: Completed

description: Designing controllers to optimize FSAE race car performance

technologies: [MATLAB, Torque Vectoring, Traction Control, Power Limiting]

image: /assets/images/VD_pid_graph.png

folder: project

in_main: true

excerpt: Working to create mechanical models for our 2026 and 2027 FSAE EV car (Cornell FSAE Racing)  I am actively researching controllers, simulating in MATLAB, as well as planning, testing, and tuning controllers on car. I am also working as a data analyst on the team to shift the team towards data-driven design.


role: Vehicle Dynamics Controls Designer

status: Ongoing

platform: MATLAB

languages: C++, MATLAB

summary: > 
    Working to create mechanical models for our 2026 and 2027 FSAE EV car (Cornell FSAE Racing). I am actively researching controllers, simulating in MATLAB, as well as planning, testing, and tuning controllers on car. I am also working as a data analyst on the team to shift the team towards data-driven design.

tags:

- MATLAB
- FSAE Testing
- PID Controllers
- Vehicle Modeling


overview:
    This project documents my introduction to mechanical engineering through FIRST Robotics Competition Team 3566. Over the course of four years, I transitioned from learning CAD to designing competition components, manufacturing parts on a CNC mill, and mentoring teammates during the team's adoption of CAD-based workflows. Outside of competition, I explored drivetrain design by leading a swerve-drive training project and creating complete robot concepts for previous FRC games.

    # I worked closely with the mentors to design a robot that is feasible to build in our team's capabilities in CAD and faciliated with the manufacturing and assembly of the robot. 


contributions:

- Designing controllers for torque vectoring, launch control, power limiting, and regenerative braking

journey:

- title: Researching Vehicle Dynamics
  # image: /assets/images/robot_2022_cropped.jpg
  description: Spent the summer learning Vehicle Dynamics and researching different teams' algorithm design
  date: August 2026

- title: Power Limit Testing
  # image: /assets/images/swerve_drive_module.png
  description: Creating test plan for Power Limiting code and tuning parameters on-car
  date: September 2026

- title: Power Limiting and Launch Control Modeling 
  # image: /assets/images/cnc_machine.JPG
  description: Developing MVP (minimal-viable product) controllers and vehicle models for Power Limiting and Launch Control in MATLAB.
  date: September 2026

# - title: 2024 Robot CAD
#   image: /assets/images/Competition Robot CAD.png
#   description: Designed custom PCB.
#   date: Jan 2024

# - title: 2024 Competition On Field
#   image: /assets/images/Robot at Competition.JPG
#   description: Integrated complete system.
#   date: March 2024

challenges:

- icon: bi-journal-text
  title: Steep Learning Curve
  problem: VD Controls is a very new role and thus there's not much past information or feedback to base off of.
  solution: Researched extensively on other team's VD controllers design and learned VD through textbooks and online courses over the summer. Talked to past VD designers (2025) about existing code base and controller state.

- icon: bi-people
  title: Fast-Paced Timeline
  problem: ARG26 Testing, ARG27 controller design and validation need to strictly follow a past-paced timeline to ensure on-time readiness for RTOS integration
  solution: Integrated manageable deadlines into design timeline. Dedicating specific work session for controller design and testing.

- icon: bi-search
  title: Teamwide VD knowledge gap
  problem: Team moving towards data-driven design. Need people to sort out previously uncalibrated data and make data available to other part designers.
  solution: Working on data analyst role to process, interpret, and document car data for more part designers to utilize when designing their part.

technologies:

#   - icon: bi-cpu
#     name: Arduino Mega
#     description: Main robot controller

#   - icon: bi-code-slash
#     name: C++
#     description: Inverse kinematics & gait control

#   - icon: bi-window
#     name: PyQt
#     description: Robot visualization dashboard

#   - icon: bi-diagram-3
#     name: KiCad
#     description: Custom PCB design

  - icon: bi-box
    name: MATLAB
    description: Running simulations in MATLAB Simulink

  - icon: bi-layers
    name: 3D Printing
    description: PLA structural components

  - icon: bi-gear
    name: GitHub
    description: Code version control & branching


#   - icon: bi-battery-charging
#     name: Power Electronics
#     description: Buck converters & power distribution

#   - icon: bi-camera
#     name: AprilTags
#     description: Pose estimation

gallery:

# - /assets/images/2022 Prompt CAD Practice.png
# - /assets/images/swerve_assemble.JPG
# - /assets/images/3dprinted_gears.JPG
# - /assets/images/cnc-ed_plate.JPG

lessons:

# - Early planning and over-communication prevent many later integration problems.
# - Unexpected integration issues will occur, so leave enough time to troubleshoot.
# - Take ownership of your work from cradle to grave by actively learning new tools and seeking help when needed.

---