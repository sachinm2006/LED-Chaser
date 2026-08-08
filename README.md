<div align="center">

# 🔴 LED CHASER CIRCUIT

### Design and Implementation of an LED Chaser Circuit Using NE555 Timer and CD4017 Counter

<p>
  <strong>Department of Electronics and Communication Engineering (ECE)</strong>
</p>

<p>
  <strong>Project Type:</strong> Mini-Project
  &nbsp;&nbsp; | &nbsp;&nbsp;
  <strong>Date:</strong> 25 May 2026
</p>

<p>
  <a href="https://www.tinkercad.com/things/3ehealz7Wxp-led-chasser">
    <strong>🔗 View Tinkercad Simulation</strong>
  </a>
</p>

</div>

<hr>

<h2>📌 Introduction</h2>

<p>
The objective of this mini-project is to design and implement an
<strong>LED Chaser Circuit</strong> using an
<strong>NE555 Timer IC</strong> and a
<strong>CD4017 Decade Counter IC</strong>.
</p>

<p>
The circuit produces a sequential lighting effect in which LEDs turn
<strong>ON and OFF one after another</strong>, creating a running or
chasing light pattern.
</p>

<p>
LED chaser circuits are widely used in decorative lighting systems,
advertisement displays, emergency warning indicators, automotive lighting,
and digital display applications.
</p>

<p>
This project demonstrates the practical implementation of:
</p>

<ul>
<li>Pulse generation</li>
<li>Clock signal propagation</li>
<li>Sequential digital logic</li>
<li>LED interfacing</li>
<li>Current limiting</li>
<li>Timing and frequency control</li>
</ul>

<p>
The <strong>NE555 Timer</strong> is configured in
<strong>astable mode</strong> to generate continuous clock pulses.
These pulses are supplied to the <strong>CD4017 decade counter</strong>,
which activates its output pins sequentially.
</p>

<p>
Each counter output drives an LED, producing the characteristic
<strong>running or chasing light effect</strong>.
</p>

<p>
By physically constructing the circuit, this project bridges the gap between
theoretical concepts of electronics and real-time circuit implementation.
</p>

<hr>

<h2>⚙️ Working Principle and Theoretical Context</h2>

<h3>2.1 Pulse Generation Using NE555 Timer</h3>

<p>
The <strong>NE555 Timer IC</strong> operates in
<strong>astable multivibrator mode</strong> to generate a continuous square-wave
clock signal.
</p>

<p>
The frequency of oscillation depends on the externally connected timing
resistors and capacitor.
</p>

<p>
The generated clock pulses are continuously supplied to the clock input of
the <strong>CD4017 counter IC</strong>.
</p>

<h3>📐 Astable Frequency Equation</h3>

<div align="center">

<h3>

f = 1.44 / ((R₁ + 2R₂) × C)

</h3>

</div>

<p>Where:</p>

<ul>
<li><strong>R₁</strong> and <strong>R₂</strong> are the timing resistors.</li>
<li><strong>C</strong> is the timing capacitor.</li>
<li><strong>f</strong> is the output frequency of the NE555 timer.</li>
</ul>

<p>
The output pulse rate directly determines the
<strong>speed of the LED chasing effect</strong>.
</p>

<p>
Increasing or decreasing the timing resistance or capacitance changes the
frequency of the generated clock signal and therefore changes the LED
sequence speed.
</p>

<hr>

<h3>2.2 Sequential Operation of CD4017 Counter</h3>

<p>
The <strong>CD4017</strong> is a CMOS decade counter with ten decoded outputs.
It responds to each incoming clock pulse by activating one output at a time.
</p>

<p>The sequence operates as follows:</p>

<div align="center">

<pre>
Clock Pulse
     ↓
   Q0 → Q1 → Q2 → Q3 → Q4
                         ↓
   Q5 → Q6 → Q7 → Q8 → Q9
                         ↓
                       RESET
                         ↓
                         Q0
</pre>

</div>

<p>For every incoming clock pulse:</p>

<ul>
<li>Only one output becomes HIGH at a time.</li>
<li>The HIGH state shifts sequentially from <strong>Q0 to Q9</strong>.</li>
<li>After Q9, the sequence returns to <strong>Q0</strong>.</li>
</ul>

<p>
Each output is connected to an LED through a
<strong>current-limiting resistor</strong>.
</p>

<p>
As the outputs change sequentially, the LEDs illuminate one after another,
creating the running-light effect.
</p>

<p>
This demonstrates the principle of
<strong>sequential digital logic and clock-driven state transitions.</strong>
</p>

<hr>

<h2>🔌 Circuit Architecture &amp; Signal Flow</h2>

<h3>3.1 Block Diagram Description</h3>

<p>
The LED chaser circuit consists of the following major functional blocks:
</p>

<table>
<thead>
<tr>
<th>Block</th>
<th>Function</th>
</tr>
</thead>

<tbody>
<tr>
<td><strong>Power Supply</strong></td>
<td>Provides the required DC voltage to the circuit</td>
</tr>

<tr>
<td><strong>NE555 Timer</strong></td>
<td>Generates continuous clock pulses</td>
</tr>

<tr>
<td><strong>CD4017 Counter</strong></td>
<td>Converts clock pulses into sequential output states</td>
</tr>

<tr>
<td><strong>LED Output Section</strong></td>
<td>Displays the sequential counting operation visually</td>
</tr>
</tbody>
</table>

<h3>🔄 Signal Flow</h3>

<div align="center">

<pre>
     3.7V DC Power Supply
             │
             ▼
      ┌──────────────┐
      │ NE555 Timer  │
      │ Astable Mode │
      └──────┬───────┘
             │
        Clock Pulses
             │
             ▼
      ┌──────────────┐
      │   CD4017     │
      │ Decade       │
      │ Counter      │
      └──────┬───────┘
             │
       Q0 → Q9 Outputs
             │
             ▼
      ┌──────────────┐
      │ LED Output   │
      │   Section    │
      └──────────────┘
             │
             ▼
       Sequential LED
          Chasing Effect
</pre>

</div>

<p>The complete signal flow is:</p>

<ol>
<li>The <strong>3.7 V power supply</strong> powers the circuit.</li>
<li>The <strong>NE555 timer</strong> generates periodic clock pulses.</li>
<li>The clock pulses are supplied to the <strong>CD4017 counter</strong>.</li>
<li>The CD4017 activates its outputs sequentially from <strong>Q0 to Q9</strong>.</li>
<li>The LEDs connected to the outputs illuminate one after another.</li>
<li>After Q9, the sequence repeats from Q0.</li>
</ol>

<hr>

<h3>3.2 Timing and Signal Integrity</h3>

<p>
The timing capacitor and resistors determine the frequency of the clock pulses
generated by the NE555 timer.
</p>

<p>
Stable timing components are necessary to maintain smooth and consistent LED
transitions.
</p>

<p>
The current-limiting resistors protect the LEDs from excessive current and
improve the reliability of the circuit.
</p>

<p>
Proper grounding and secure breadboard connections are also important to
prevent signal noise, unstable timing, and irregular LED operation.
</p>

<hr>

<h3>3.3 Reset Mechanism</h3>

<p>
The reset pin of the CD4017 can be configured strategically to limit the number
of active outputs in the sequence.
</p>

<p>For example:</p>

<table>
<thead>
<tr>
<th>Reset Configuration</th>
<th>Result</th>
</tr>
</thead>

<tbody>
<tr>
<td>Reset connected to Q5</td>
<td>Creates a 5-LED chaser</td>
</tr>

<tr>
<td>Full Q0–Q9 sequence</td>
<td>Allows 10-LED operation</td>
</tr>
</tbody>
</table>

<p>
This provides flexibility for designing customized LED chasing patterns.
</p>

<hr>

<h2>🧰 Components Used</h2>

<table>
<thead>
<tr>
<th>Component</th>
<th>Specification</th>
<th>Purpose</th>
</tr>
</thead>

<tbody>

<tr>
<td><strong>NE555 Timer IC</strong></td>
<td>DIP-8</td>
<td>Generates clock pulses in astable mode</td>
</tr>

<tr>
<td><strong>CD4017 Counter IC</strong></td>
<td>CMOS Decade Counter</td>
<td>Activates outputs sequentially</td>
</tr>

<tr>
<td><strong>LEDs</strong></td>
<td>5 mm Standard LEDs</td>
<td>Provides visual indication of the running sequence</td>
</tr>

<tr>
<td><strong>LED Resistors</strong></td>
<td>680 Ω</td>
<td>Limits current through the LEDs</td>
</tr>

<tr>
<td><strong>Timing Resistor R₁</strong></td>
<td>1 kΩ</td>
<td>Controls the NE555 timing frequency</td>
</tr>

<tr>
<td><strong>Timing Resistor R₂</strong></td>
<td>1 kΩ</td>
<td>Controls the NE555 timing frequency</td>
</tr>

<tr>
<td><strong>Timing Capacitor</strong></td>
<td>10 µF</td>
<td>Determines oscillation timing</td>
</tr>

<tr>
<td><strong>Control Capacitor</strong></td>
<td>0.01 µF</td>
<td>Improves timer stability</td>
</tr>

<tr>
<td><strong>Breadboard</strong></td>
<td>Standard</td>
<td>Circuit assembly and prototyping</td>
</tr>

<tr>
<td><strong>Jumper Wires</strong></td>
<td>Standard</td>
<td>Electrical interconnections</td>
</tr>

<tr>
<td><strong>Power Supply</strong></td>
<td>3.7 V DC</td>
<td>Provides power to the circuit</td>
</tr>

</tbody>
</table>

<hr>

<h2>📊 Results</h2>

<p>
The implemented LED chaser circuit successfully generated sequential blinking
of LEDs using clock pulses from the NE555 timer and output sequencing from the
CD4017 counter.
</p>

<p>
The LEDs turned ON one after another in a cyclic manner, demonstrating proper
operation of both the timer and counter stages.
</p>

<h3>🔢 Observed Performance</h3>

<table align="center">
<thead>
<tr>
<th>Clock Pulse</th>
<th>Active Output</th>
<th>LED Status</th>
</tr>
</thead>

<tbody>
<tr><td>1st Pulse</td><td>Q0</td><td>LED1 ON</td></tr>
<tr><td>2nd Pulse</td><td>Q1</td><td>LED2 ON</td></tr>
<tr><td>3rd Pulse</td><td>Q2</td><td>LED3 ON</td></tr>
<tr><td>4th Pulse</td><td>Q3</td><td>LED4 ON</td></tr>
<tr><td>5th Pulse</td><td>Q4</td><td>LED5 ON</td></tr>
<tr><td>6th Pulse</td><td>Q5</td><td>LED6 ON</td></tr>
<tr><td>7th Pulse</td><td>Q6</td><td>LED7 ON</td></tr>
<tr><td>8th Pulse</td><td>Q7</td><td>LED8 ON</td></tr>
<tr><td>9th Pulse</td><td>Q8</td><td>LED9 ON</td></tr>
<tr><td>10th Pulse</td><td>Q9</td><td>LED10 ON</td></tr>
</tbody>
</table>

<p>
The speed of the LED chasing pattern was successfully varied by changing the
timing resistor and capacitor values.
</p>

<h3>✅ Hardware Testing Confirmed</h3>

<ul>
<li>Stable pulse generation by the <strong>NE555 timer</strong>.</li>
<li>Correct sequential counting by the <strong>CD4017</strong>.</li>
<li>Smooth LED chasing effect.</li>
<li>Reliable operation under a <strong>3.7 V DC supply</strong>.</li>
</ul>

<hr>

<h2>🎯 Applications</h2>

<p>
The LED chaser circuit has several practical applications in electronics and
lighting systems.
</p>

<h3>1. Decorative Lighting Systems</h3>

<p>
Used in festivals, homes, events, and entertainment lighting to create
attractive running-light patterns.
</p>

<h3>2. Advertisement Displays</h3>

<p>
Used in signboards and commercial displays to attract attention through
sequential lighting patterns.
</p>

<h3>3. Emergency Warning Indicators</h3>

<p>
Sequential flashing lights can be used in safety and alert systems to provide
visual warnings.
</p>

<h3>4. Automotive Lighting</h3>

<p>
Similar sequential lighting concepts are used in vehicle indicator systems
and decorative automotive lighting.
</p>

<h3>5. Educational Demonstration</h3>

<p>
The circuit provides a practical demonstration of timer circuits, counters,
clock pulses, and sequential digital logic.
</p>

<h3>6. Sequential Control Systems</h3>

<p>
The same principle can be applied to systems requiring ordered activation of
multiple outputs.
</p>

<hr>

<h2>📈 Key Concepts Demonstrated</h2>

<table>
<thead>
<tr>
<th>Concept</th>
<th>Demonstration</th>
</tr>
</thead>

<tbody>
<tr>
<td>Astable Multivibrator</td>
<td>NE555 generates continuous clock pulses</td>
</tr>

<tr>
<td>Frequency Control</td>
<td>Resistor and capacitor values control pulse frequency</td>
</tr>

<tr>
<td>Sequential Logic</td>
<td>CD4017 activates outputs one at a time</td>
</tr>

<tr>
<td>Clock Propagation</td>
<td>Counter changes state with every clock pulse</td>
</tr>

<tr>
<td>LED Interfacing</td>
<td>LEDs provide visual output indication</td>
</tr>

<tr>
<td>Current Limiting</td>
<td>680 Ω resistors protect LEDs</td>
</tr>

<tr>
<td>Digital Electronics</td>
<td>Demonstrates practical sequential logic operation</td>
</tr>
</tbody>
</table>

<hr>

<h2>📁 Recommended Project Structure</h2>

<pre>
LED-Chaser-NE555-CD4017/
│
├── README.md
│
├── Simulation/
│   └── Tinkercad-Link.txt
│
├── Circuit/
│   ├── Circuit-Diagram.png
│   └── Breadboard-Implementation.png
│
├── Documentation/
│   └── Mini-Project-Report.pdf
│
└── Images/
    ├── LED-Chaser-1.png
    ├── LED-Chaser-2.png
    └── LED-Chaser-3.png
</pre>

<hr>

<h2>🔗 Tinkercad Simulation</h2>

<div align="center">

<a href="https://www.tinkercad.com/things/3ehealz7Wxp-led-chasser">

<img src="https://img.shields.io/badge/Tinkercad-Open%20Simulation-orange?style=for-the-badge">

</a>

<br><br>

<a href="https://www.tinkercad.com/things/3ehealz7Wxp-led-chasser">

<strong>▶ Open LED Chaser Simulation</strong>

</a>

</div>

<hr>

<h2>🏁 Conclusion</h2>

<p>
The <strong>LED Chaser Circuit</strong> was successfully designed and
implemented using the <strong>NE555 Timer IC</strong> and
<strong>CD4017 Decade Counter IC</strong>.
</p>

<p>
The project demonstrated the practical application of
<strong>pulse generation, clock-driven sequencing, and digital output control.</strong>
</p>

<p>
The circuit operated reliably and produced a smooth sequential lighting
pattern. The project provided valuable hands-on experience in:
</p>

<ul>
<li>Circuit design</li>
<li>Breadboard implementation</li>
<li>Timer configuration</li>
<li>Frequency and timing analysis</li>
<li>Sequential counter operation</li>
<li>LED interfacing</li>
<li>Digital electronics</li>
</ul>

<p>
This mini-project serves as an effective educational experiment for understanding
<strong>sequential logic systems, timer circuits, counters, and real-world
electronic circuit applications.</strong>
</p>

<hr>

<h2>👨‍💻 Project Information</h2>

<table>
<tr>
<td><strong>Project</strong></td>
<td>LED Chaser Circuit</td>
</tr>

<tr>
<td><strong>Technology</strong></td>
<td>NE555 Timer + CD4017 Decade Counter</td>
</tr>

<tr>
<td><strong>LEDs</strong></td>
<td>10 × 5 mm LEDs</td>
</tr>

<tr>
<td><strong>Supply Voltage</strong></td>
<td>3.7 V DC</td>
</tr>

<tr>
<td><strong>Department</strong></td>
<td>Electronics and Communication Engineering (ECE)</td>
</tr>

<tr>
<td><strong>Project Type</strong></td>
<td>Mini-Project</td>
</tr>

<tr>
<td><strong>Date</strong></td>
<td>25 May 2026</td>
</tr>
</table>

<hr>

<div align="center">

<h3>⭐ Project Highlight</h3>

<p>
<em>
"From clock pulses to sequential illumination — this project demonstrates how
timer-generated signals can control a digital counter to create a practical
LED sequencing system."
</em>
</p>

<br>

<a href="https://www.tinkercad.com/things/3ehealz7Wxp-led-chasser">

<strong>🔗 View Project Simulation on Tinkercad</strong>

</a>

</div>
