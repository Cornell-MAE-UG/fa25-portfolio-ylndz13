---
layout: project
title: Thermodynamics Device Analysis (FA 2025)
description: Heat Exchanger
technologies: [Thermodynamics - Control Volme Analysis]
# image: /assets/images/ENGRD-2210-Heat-Exchanger-Device-Analysis.png
# image width: 100%
---
<img src="/assets/images/ENGRD-2210-Heat-Exchanger-Device-Analysis.png"
     style="display: block; width: 100%; margin: 2rem auto;">

<style>
h5 {
  margin-top: 4rem;
  margin-bottom: 0;
}
</style>

<script>
  MathJax = {
    tex: {
      inlineMath: [['$', '$'], ['\\(', '\\)']],
      displayMath: [['$$', '$$'], ['\\[', '\\]']]
    }
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js" defer></script>

For ENGRD 2210 Thermodynamics, we experimented with heat exchangers in a minilab and have the option to analyze a specific thermodynamic system or device. The questions that I am interested in answering are: 
1. What is the flow rate of the water through the heat exchanger?
2. What is the change in entropy of the system?
3. What is the rate of heat transfer inside the heat exchanger?
4. How much entropy is generated?

<h5> Schematic: </h5>
<img src="{{ '/assets/images/ENGRD-2210-Parallel-Flow.jpg' | relative_url }}"
     style="display: block; width: 100%; margin: 2rem auto;">
<img src="{{'/assets/images/ENGRD-2210-Counter-Flow.jpg' | relative_url}}"
     style="display: block; width: 100%; margin: 2rem auto;">


<h5> Method: </h5>
Since our system has mass entering and leaving, we need to use the Control Volume method for analyzing this system.

<h5> Assumptions: </h5>
1. Water in its liquid state is not highly sensitive to pressure and volume change. Therefore, we can model water in the system as **incompressible**.
2. There is no significant change in height in the heat exchanger system, so the gravity and potential energy terms in the energy balance equations can be disregarded.
3. The water in the heat exchanger is not significantly changing speed. Therefore, the change in kinetic energy is negligible.
4. There is insulation around cold reservoir, and the hot reservoir is held at constant temperature, so we can approximate the heat transfer between the environment and the reservoirs as 0. 
5. We assume that the device operates at steady state, so we cannot look at the initial transient state when the pumps just started operating in the reservoirs, and likewise for when the pumps are turned off. All measurements were taken at a steady state scenario.


<h5> Materials: </h5>
1. 2x Pumps from Vivosun (Aqua Pump)
2. 1x Anova Precision Cooker for heating up the hot reservoir
3. 1x Heat exchanger
4. 4x rubber tubes 
5. 1x Red and blue food coloring. Red for the hot reservoir, blue is for the cold reservoir 


<h5> Experiment Setup: </h5>
Four experiments were run in total. Each experiment was run with different heat exchanger setup or pump flowrate setup. The independent variables of the experiment are **heat exchanger flow direction** and **pump flowrate**. The heat exchanger can be set up to be either parallel flow or counter flow, and the pumps could flow at a low or a high rate. <br>


<h5> Collected Data: </h5>

<style>
  table.spaced-table th,
  table.spaced-table td {
    padding: 0.3rem; /* vertical | horizontal spacing */
  }
</style>

<table class = "spaced-table">
  <colgroup>
    <col style="min-width: 160px">
    <col style="min-width: 200px">
    <col style="min-width: 200px">
  </colgroup>
  <thead>
    <tr>
      <th>Pump Speed</th>
      <th>Paralell Flow</th>
      <th>Counter Flow</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td> <b> High </b> </td>
      <td>
          $T_{hot,in}: 43 ^\circ C$ <br>
          $T_{cold,in}: 17.5 ^\circ C$ <br>
          $T_{hot,exit}:31.8 ^\circ C$ <br>
          $T_{cold,exit}: 29.3 ^\circ C$ 
      </td>
      <td>
        $T_{hot,in}: 44.8 ^\circ C$ <br>
        $T_{cold,in}: 18 ^\circ C$ <br>
        $T_{hot,exit}: 28.2 ^\circ C$ <br>
        $T_{cold,exit}: 31.8 ^\circ C$
      </td>
    </tr>
    <tr>
      <td> <b> Low </b> </td>
      <td>
          $T_{hot,in}: 42.8 ^\circ C$ <br>
          $T_{cold,in}:  21.6 ^\circ C$ <br>
          $T_{hot,exit}: 30.5 ^\circ C$ <br>
          $T_{cold,exit}: 28.9 ^\circ C$ <br>
      </td>
      <td>
        $T_{hot,in}: 45.6 ^\circ C$ <br>
        $T_{cold,in}: 13.8 ^\circ C$ <br>
        $T_{hot,exit}:  25.3 ^\circ C$ <br>
        $T_{cold,exit}: 33.4 ^\circ C$ 
      </td>
    </tr>
  </tbody>
</table>



<h5> Calculations: </h5> <br>
<h6> Mass Balance: </h6> <br>
Since we are operating at steady state, the sum of masses flowing into and out of the device sum to 0.<br>
\\[\dot{m_{inlet}}-\dot{m_{exit}} = 0\\]
Since we have two separate channels for the hot and cold water to flow through, rearranging the above equation gives us:
\\[\dot{m_{hot,i}} = \dot{m_{hot, e}} = \dot{m_h}\\]
\\[\dot{m_{cold,i}} = \dot{m_{cold, e}} = \dot{m_c}\\]
 <br>
 <br>
<h6> 1st Law Energy Balance: </h6> <br>
Since we are in the steady state:<br>
\\[\dot{E} = 0\\]
\\[\dot{Q} - \dot{W} + \dot{m_h}\left(\Delta h_{h} + \frac{\Delta v_{h}^2}{2} + g \Delta z_{h} \right) + \dot{m_c}\left(\Delta h_{c} + \frac{\Delta v_{c}^2}{2} + g \Delta z_{c} \right)=0\\]
Since we assumed that change in kinetic energy and elevation are negligible:
\\[\dot{Q} - \dot{W} + \dot{m_h}\left(\Delta h_{h} \right) + \dot{m_c}\left(\Delta h_{c} \right)=0\\]
Since we know that water is incompressible, the change in the rate of work is also 0:
\\[\dot{Q} + \dot{m_h}\left(\Delta h_{h} \right) + \dot{m_c}\left(\Delta h_{c} \right)=0\\]

\\[\dot{m} \Delta h_h = -\dot{m} \Delta h_c\\]
\\[\dot{m} = -\frac{\Delta h_c}{\Delta h_h} = -\frac{cp \Delta T_c}{cp \Delta T_h}\\]
\\[\dot{m} = -\frac{T_{c,e}-T_{c,i}}{T_{h,e}-T_{h,i}}\\]

Parallel Flow, High:
\\[\dot{m} = -\frac{29.3-17.5}{31.8-43} = 1.0536 \frac{kg}{s} \\]

Parallel Flow, Low:
\\[\dot{m} = -\frac{28.9-21.6}{30.5-42.8} = 0.5935 \frac{kg}{s} \\]

Counter Flow, High:
\\[\dot{m} = -\frac{31.8-18}{28.2-44.8} = 0.8313 \frac{kg}{s} \\]

Counter Flow, Low:
\\[\dot{m} = -\frac{33.4-13.8}{25.3-45.6} = 0.9655 \frac{kg}{s} \\]

We observe that the mass flow rate when the pump is on the "high" setup is almost twice as much as when the pump is set to "low". 
 <br>
 <br>
<h6> Change in Entropy </h6>
\\[\Delta s = c \ln \frac{T_e}{T_i}\\]
One thing to note is that since we are no longer taking the difference of two temperatures, we need to convert the measurements from Celsius into Kelvin for the above formula to work. We will take $c = 4.184 \frac{kJ}{kgK}$ as the specific heat of liquid water. <br>

Parallel Flow, High: <br>
Hot channel: $\Delta s = 4.184 \frac{kJ}{kgK} \cdot \ln \frac{304.95}{316.15} = -0.1509 \frac{kJ}{kgK}$ <br>
Cold channel: $\Delta s = 4.184 \frac{kJ}{kgK} \cdot \ln \frac{302.45}{290.65} = 0.1665 \frac{kJ}{kgK}$ <br>

Parallel Flow, Low: <br>
Hot channel: $\Delta s = 4.184 \frac{kJ}{kgK} \cdot \ln \frac{303.65}{315.95} = -0.1661 \frac{kJ}{kgK}$ <br>
Cold channel: $\Delta s = 4.184 \frac{kJ}{kgK} \cdot \ln \frac{302.05}{294.75} = 0.1024 \frac{kJ}{kgK}$ <br>

Counter Flow, High: <br>
Hot channel: $\Delta s = 4.184 \frac{kJ}{kgK} \cdot \ln \frac{301.35}{317.95} = -0.2244 \frac{kJ}{kgK}$ <br>
Cold channel: $\Delta s = 4.184 \frac{kJ}{kgK} \cdot \ln \frac{304.95}{291.15} = 0.1938 \frac{kJ}{kgK}$ <br>

Counter Flow, Low: <br>
Hot channel: $\Delta s = 4.184 \frac{kJ}{kgK} \cdot \ln \frac{298.45}{318.75} = -0.2753 \frac{kJ}{kgK}$ <br>
Cold channel: $\Delta s = 4.184 \frac{kJ}{kgK} \cdot \ln \frac{306.55}{286.95} = 0.2764 \frac{kJ}{kgK}$ <br>

We observe that the change in entropy from the counterflow setup is greater than the change in entropy from the parallel flow setup. This seems to suggest that there is more heat transfer from the counter flow setup. Is this hypothesis true? We will find out by calculating the rate of heat transfer between the hot and cold reservoirs. To do this, we need to adjust our system boundary to surround just the hot channel in the heat exchanger or just the cold channel in the heat exchanger. 

 <br>
 <br>
<h6> Rate of Heat Transfer: </h6>
\\[\dot{Q} = - \dot{m} (\Delta h) = - \dot{m} c \Delta T\\]

Parallel Flow, High: <br>
Hot channel: $\dot{Q} = - \dot{m} \frac{kg}{s} \cdot 4.184 \frac{kJ}{kgK} \cdot (304.95 - 316.15)K = -49.37 \frac{kJ}{s}$ <br>
Cold channel: $\dot{Q} = - \dot{m} \frac{kg}{s} \cdot 4.184 \frac{kJ}{kgK} \cdot (302.45 - 290.65)K = 52.02 \frac{kJ}{s}$ <br>

Parallel Flow, Low: <br>
Hot channel: $\dot{Q} = - \dot{m} \frac{kg}{s} \cdot 4.184 \frac{kJ}{kgK} \cdot (303.65-315.95) K = -30.54 \frac{kJ}{s}$ <br>
Cold channel: $\\dot{Q} = - \dot{m} \frac{kg}{s} \cdot 4.184 \frac{kJ}{kgK} \cdot (302.05-294.75) K = 18.13 \frac{kJ}{s}$ <br>

Counter Flow, High: <br>
Hot channel: $\\dot{Q} = - \dot{m} \frac{kg}{s} \cdot 4.184 \frac{kJ}{kgK} \cdot (301.35 - 317.95) K = -57.74 \frac{kJ}{s}$ <br>
Cold channel: $\dot{Q} = - \dot{m} \frac{kg}{s} \cdot 4.184 \frac{kJ}{kgK} \cdot (304.95 - 291.15) K = 48.00 \frac{kJ}{s}$ <br>

Counter Flow, Low: <br>
Hot channel: $\dot{Q} = - \dot{m} \frac{kg}{s} \cdot 4.184 \frac{kJ}{kgK} \cdot (298.45 - 318.75) K = -82.01 \frac{kJ}{s}$ <br>
Cold channel: $\dot{Q} = - \dot{m} \frac{kg}{s} \cdot 4.184 \frac{kJ}{kgK} \cdot (306.55 - 286.95) K = 79.18 \frac{kJ}{s}$ <br>

The data does support the previous hypothesis that putting the heat exchanger in counter flow improves the rate of heat transfer. This suggests that the counter flow setup is more efficient than the parallel flow setup at exchanging heat.