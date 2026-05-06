---
layout: project
title: MAE 2250 Client Report
description: Solving the Spotted Lantern Fly Problem
permalink: /projects/MAE2250/client-report/
technologies: [Communication, Teamwork, CAD, Building, BOM]
folder: MAE2250
image: /assets/images/2250_prototype_close.png
in_main: false
---
<style>
h5 {
  margin-top: 4rem;
  margin-bottom: 0;
}
</style>

<style>
h3 {
  margin-top: 4rem;
  margin-bottom: 0;
}
</style>

**Team Bug-anators**

**Client(s):** Cornell CALS Extension / E&J Gallo Winery / National Grape

<h3>Context & Problem Statement</h3>

<h5> Specific Problem: </h5>
During mechanical harvesting, up to ~60% of SLF present on vines are collected into grape bins, and even 1–2 insects in a 1000 g sample can cause an entire shipment to be rejected.

<h5> Why it Matters: </h5>
 This leads to significant economic losses, reduced crop quality, and inefficiencies since mechanical systems do not allow for manual sorting. As SLF continues to spread, this issue will scale rapidly across vineyards.

<h5> Constraints: </h5>

<ol>
     <li> Must work with mechanical harvesting systems (no interference)</li>
     <li> Must allow airflow and sunlight for plant health</li>
     <li> Must be scalable across vineyard rows</li>
     <li> Must be retractable for operational efficiency</li>
     <li> Must be structurally stable under outdoor conditions</li>
</ol>


<h3>Final Prototype and Application</h3>

**Prototype Overview:** A retractable vineyard enclosure that expands to protect grapevines from SLF and contracts to allow harvesting operations.

<img src="{{ '/assets/images/2250_prototype_close.png' | relative_url }}"
     style="display: block; width: 80%; margin: 2rem auto;">

<img src="{{ '/assets/images/2250_prototype_open.png' | relative_url }}"
     style="display: block; width: 80%; margin: 2rem auto;">

**How it Works:**
<ol>
     <li>A scissor linkage expands horizontally to form a frame</li>
     <li>Mesh stretches across the frame to create a barrier</li>
     <li>A wheel–rail system enables smooth expansion and retraction</li>
     <li>The system encloses vines during growth and retracts during harvest</li>
</ol>

**Key Components:**
<ol>
     <li>Scissor linkage (expandable structure)</li>
     <li>Mesh enclosure (physical barrier)</li>
     <li>Wheel–rail system (guided motion)</li>
     <li>Structural support frame</li>
     <li>Fasteners and joints</li>
</ol>

**Application:** Used in vineyards to prevent SLF contamination before harvest, reducing reliance on pesticides and eliminating the need for post-harvest sorting.

<h3>Conclusion and Recommendation</h3>

**Recommendation:** Proceed with further development of the retractable enclosure design, with targeted improvements. The current bill of materials (displayed below) reflects a low cost prototype using readily available components from limited options rather than optimized ones. The following test results indicate that future iterations will require a greater variety of plentiful stronger materials to choose from for low cost mass production in order to span a whole vineyard.
**Justification:** The prototype successfully demonstrates a prevention-based solution that blocks SLF at the source while maintaining compatibility with harvesting operations.

**Based on testing results:**
<ol>
     <li>Structural instability (tilting under load) needs improvement</li>
     <li>Wheel–rail misalignment caused jamming</li>
     <li>Fasteners loosened after repeated cycles</li>
</ol>
**Feasibility:** The concept is feasible as a scalable vineyard solution, but requires refinement in structural rigidity, alignment precision, and durability for real-world deployment.

**Next Steps:**
<ol>
     <li>Reinforce the scissor linkage with stronger materials like Aluminum 6061</li>
     <li>Improve wheel–rail alignment tolerances</li>
     <li>Add locking mechanisms for fasteners</li>
     <li>Integrate motorized actuation for consistent operation</li>
     <li>Conduct field testing in real vineyard conditions</li>
</ol>

**Testing and Results:**
**Test 1:** Structural Stability (Scissor Linkage)
<img src="{{ '/assets/images/2250_tilt_angle_weights.png' | relative_url }}"
     style="display: block; width: 80%; margin: 2rem auto;">
**Purpose:** Evaluate how the structure behaves under load
**Method:** Added calibrated weights to the center of the linkage and measured the tilt angle
**Results:**
<ol>
     <li>Tilt angle increased with increasing load initially</li>
     <li>After a certain weight threshold (~mid-range loads), the tilt began to plateau around ~10°</li>
     <li>Additional weight beyond this point did not significantly increase deformation</li>
</ol>

**Implications:**
<ol>
     <li>The structure exhibits limited stiffness, deforming quickly under initial loading</li>
     <li>The plateau suggests the system reaches a geometric or structural limit, where further deformation is constrained</li>
     <li>While deformation does not increase indefinitely, a ~10° tilt is still significant and may impact performance</li>
     <li>Indicates need for increased rigidity (stronger materials, bracing, or improved linkage design)</li>
</ol>

**Test 2:** Wheel–Rail Motion Performance 
<img src="{{ '/assets/images/2250_jams_per_cycle.png' | relative_url }}"
     style="display: block; width: 80%; margin: 2rem auto;">

**Purpose:** Evaluate the reliability and smoothness of the wheel–rail system during repeated expansion and contraction cycles.
**Method:** The prototype was run through 10 full expansion–contraction cycles. During each cycle, the number of jams (instances where motion was obstructed or stopped) was recorded.
**Results:** 
Early cycles showed smooth motion with little to no jamming
Later cycles exhibited increased jamming events
The total number of jams increased as the cycle number increased
Implications: 
The system is initially functional, but loses reliability over repeated use
Small misalignments in the wheel–rail system accumulate and lead to jamming
Precise alignment and tighter tolerances are critical for consistent performance


**Test 3:** Fastener Reliability

<img src="{{ '/assets/images/2250_loose_fasteners_vs_cycles.png' | relative_url }}"
     style="display: block; width: 80%; margin: 2rem auto;">

**Purpose:** Assess the durability of fasteners under repeated expansion–contraction cycles.
**Method:** After performing 10 full expansion–contraction cycles, all bolts and fasteners in the prototype were inspected. The number of loosened fasteners was recorded after each cycle.
**Results:** 
Fasteners began to loosen after several cycles
The number of loose fasteners increased over time
By later cycles, multiple fasteners required retightening
**Implications:**
<ol>
     <li>Repeated motion and vibration lead to gradual fastener loosening</li>
     <li>The current fastening method is not sufficient for long-term durability</li>
     <li>Indicates a need for locking mechanisms (e.g., lock nuts, thread-locking compounds)</li>
</ol>

**Prototype and Testing Details:**
**Design Details:** The design uses a horizontally expanding scissor linkage system combined with a mesh barrier to create a retractable enclosure that surrounds grapevines while maintaining environmental exposure.

**Assembly Overview:**
<ol>
     <li>Constructed a 4-bar scissor-linkage frame constrained to 1 DOF, ensuring the entire mechanism moves from a single input motion.</li>
     <li>Cut 80/20 extrusion channels to length using a bandsaw and connect them with L-brackets to form the rigid end frames.</li>
     <li>Pinned the top of the scissor linkage to the frame (fixed) while leaving the bottom free to translate, enabling linear extension and retraction.</li>
     <li>Fabricated a wheel-motor mount in CAD, assembled it under the free end of the frame, and powered the motor via a DC adaptor with alligator clips provided to us. </li>
     <li>Secured the insect mesh enclosure to the scissor linkage using zip ties along the aluminum frame.</li>
     <li>Mounted the full assembly onto an L-bracket rail system, allowing the system to roll along a fixed linear track.  </li>
</ol>

**Testing Setup:** The prototype was tested using controlled, repeatable setups to evaluate structural stability, motion performance, and fastener reliability under conditions that simulate real operation.
**Test 1: Structural Stability (Scissor Linkage):** The prototype was fully expanded and placed on a stable surface. Calibrated weights were incrementally added to the center of the scissor linkage to simulate loading conditions. At each load step, the tilt angle of the structure was measured relative to the horizontal to quantify deformation.
**Test 2: Wheel–Rail Motion Performance:** The prototype was mounted on its rail system and manually operated through repeated expansion and contraction cycles. A total of 10 full cycles were performed. During each cycle, the system was observed for interruptions in motion, and any instances of jamming or resistance were recorded.
**Test 3: Fastener Reliability:** Following the motion testing, all fasteners (bolts and joints) were inspected after each cycle. The number of loosened fasteners was recorded to evaluate how repeated motion and vibration affected connection integrity over time.



<h3> Bill of Materials</h3>

<table class = "spaced-table" style = "margin: 0 auto; text-align: center">
     <colgroup>
          <col style="width: 140px">
          <col style="width: 270px">
          <col style="width: 150px">
          <col style="width: 150px">
          <col style="width: 150px">
     </colgroup>
     <thead>
     <tr>
          <th>Part Name</th>
          <th>Description</th>
          <th>Material</th>
          <th>Source (McMaster Code or Amazon link)</th>
          <th>Fabrication Method</th>
     </tr>
     </thead>
     <tbody>
     <tr>
          <td> <b> T-Slotted Framing Rail </b> </td>
          <td> Single four-slot rail, 1" × 1", length = 6 ft </td>
          <td> Aluminum </td>
          <td> McMaster 47065T101 </td>
          <td> Purchased & used </td>
     </tr>
     <tr>
          <td> <b> Aluminum U-Channel </b> </td>
          <td> 6063 aluminum, 1/16" wall, 3/8" × 5/8", length = 4 ft </td>
          <td> Aluminum </td>
          <td> McMaster 9001K787 </td>
          <td> Purchased & used </td>
     </tr>
     <tr>
          <td> <b> Garden Mesh Netting </b> </td>
          <td> 4' × 10' fine bug netting for pest protection </td>
          <td> Polymer mesh </td>
          <td> mesh </td>
          <td> Purchased but not used bc didn’t arrive on time </td>
     </tr>
     <tr>
          <td> <b> Expandable Coat Rack (Wall Hanger) </b> </td>
          <td> Wooden expandable peg rack, 14 hooks </td>
          <td> Wood </td>
          <td> l brackets  </td>
          <td> Purchased but not used bc didn’t arrive on time </td>
     </tr>
     <tr>
          <td> <b> DC Gear Motor  </b> </td>
          <td> 12V, 10 RPM high torque geared motor, 37 mm shaft </td>
          <td> Metal/plastic  </td>
          <td> motor  </td>
          <td> Purchased but not used bc didn’t arrive on time </td>
     </tr>
     <tr>
          <td> <b> Corner Brackets (Set) </b> </td>
          <td> 2020 aluminum extrusion L-brackets with M5 bolts/nuts </td>
          <td> Aluminum </td>
          <td> corner brackets  </td>
          <td> Purchased but not used bc didn’t arrive on time </td>
     </tr>
     </tbody>
</table>
