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
          <col style="width: 150px">
          <col style="width: 100px">
          <col style="width: 100px">
          <col style="width: 500px">
     </colgroup>
     <thead>
     <tr>
          <th>Part Name</th>
          <th>Part Number</th>
          <th>Quantity</th>
          <th>Cost</th>
          <th>Justification</th>
     </tr>
     </thead>
     <tbody>
     <tr>
          <td> <b> Collapsible Gates (Amazon) </b> </td>
          <td> B08L5FQYHS </td>
          <td> 2 </td>
          <td> $46 </td>
          <td> This part is mainly for the expandable and collapsible portion of the shaft, which is essential for the top-most portion of our design. It is also not on McMaster, where we are only able to source it from Amazon. </td>
     </tr>
     <tr>
          <td> <b> Mesh (Amazon) </b> </td>
          <td> B087RSWLY8 </td>
          <td> 1 </td>
          <td> $8 </td>
          <td> A mesh is also an important part of our design. It acts as the main protective layer against SLFs. However, McMaster only has extremely heavy meshes, which are not structurally good for our design purposes. We are also not able to make this in the TDS or by machining any parts, so the only way is to buy it from Amazon.  </td>
     </tr>
     <tr>
          <td> <b> Wheels (Amazon) </b> </td>
          <td> B0FLX9WQBH </td>
          <td> 2 </td>
          <td> $37.16 </td>
          <td> This part is used for the rolling motion of the mesh and structural components. Wheels from McMaster are incredibly expensive, which makes buying wheels from Amazon the only realistic option for our team. </td>
     </tr>
     <tr>
          <td> <b> Motor (Amazon) </b> </td>
          <td> WB089GTHGPZ </td>
          <td> 2 </td>
          <td> $30  </td>
          <td> This part is used for electrically powering our wheels. This allows us to automate our system. Motors from McMaster are incredibly clunky, heavy, costly, and the specs are too high for our use case. Amazon was the only reasonably priced option. </td>
     </tr>
     <tr>
          <td> <b> 80/20 extrusions (McMaster)  </b> </td>
          <td> 47065T101 </td>
          <td> 2  </td>
          <td> $66.50  </td>
          <td> 6 ft each </td>
     </tr>
     <tr>
          <td> <b> U channels (McMaster) </b> </td>
          <td> 9001K787 </td>
          <td> 2 </td>
          <td> $17.48  </td>
          <td> 4 ft each </td>
     </tr>
     <tr>
          <td> <b> L brackets + more nuts (Amazon) </b> </td>
          <td> B0855V2JV3 </td>
          <td> 1 </td>
          <td> $18  </td>
          <td> These L brackets are for securing our frames together. These brackets could be found on McMaster, but McMaster charges $8 for each bracket, which is ludicrously overpriced and would put us over budget. </td>
     </tr>
     </tbody>
</table>

Totals: $233

<h3>Work Cited:</h3>
<ol>
     <li>Bekelja, K. M. (2026). NY grapes and the spotted lanternfly problem. Cornell Integrated Pest Management</li>
     <li>Phillips-Russo, J. (2026). Spotted lanternfly mechanical harvester study. Lake Erie Regional Grape Program</li>
</ol>