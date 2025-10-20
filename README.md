# Innovative-electronic-door
📖 Introduction
The project consists of an electronic door handle system that uses the basic principles of digital electronics and implements a variety of features, keeping in mind the recent coronavirus pandemic situation. The various features of the door are studied from the simulations obtained in the Verilog implementation as well as the Logisim model.

🛠️ Tools and Software Used
Verilog: A hardware description language (HDL) used to model and simulate the digital circuits. The Xilinx Vivado 2016 Version is used to design and simulate the various features of the door.

Logisim: A graphical system for logical circuit design and simulation.

✨ Features of the Electronic Door
Password Verification: The password verification machine is based on the property of XNOR gates, where the output is 1 only when both inputs are the same. If the user's input matches the stored password, the door becomes accessible.

Magic Counter: This feature counts and displays the number of times the gate has been used on a 7-segment display. It is implemented using two cascaded binary counters to display a two-digit number.

Crowd Factor Calculator: This feature detects the number of people inside the room and indicates the crowd level with a colored LED:

Green: Few people (low crowd)

Yellow: Moderate crowd

Red: Crowded This is achieved by using two counters (one for entries, one for exits), a subtractor to find the difference, a comparator, and a priority encoder to light the appropriate LED.

Privacy Mode: This allows a user to lock the door from the inside. When Privacy Mode is on (logic 1), an AND gate ensures the output remains 0, keeping the door closed regardless of password input. When the mode is off (logic 0), a correct password entry will open the door.

💻 Verilog Implementation
The various features of the door are implemented as separate modules and are then instantiated in a top-level module. The design uses a mix of gate-level, dataflow, and behavioral modeling.

1)Password Machine: Implemented using gate-level modeling with XNOR gates and an AND gate.

Mod 16 Counter: A 4-bit counter that counts from 0 to 15 (16 states) and resets to 0.



2)Magic Counter: Designed using behavioral modeling, this module uses the mod_16_counter to count the number of times the gate has been opened.



Subtractor: This module finds the difference between two inputs, assigning the value only if the difference is positive.


3)Crowd Factor Calculator: This module calculates the crowd in the room and lights one of the three LEDs. It uses two instances of the mod_16_counter and one instance of the subtractor.

Top-Level Module (innovative_door): The main module where all other sub-modules are instantiated to complete the design.
4) Privacy Mode: This allows a user to lock the door from the inside. When Privacy Mode is on (logic 1), an AND gate ensures the output remains 0, keeping the door closed regardless of password input. When the mode is off (logic 0), a correct password entry will open the door


Testbench
A Verilog testbench was implemented to verify, analyze, and simulate the functionality of the complete design. All modes and features were tested by specifying input values in the testbench.

📊 Simulations and Outputs
Logisim Simulation
The simulation of the various features of the electronic door as obtained in Logisim.


Verilog Simulation
The simulation waveform obtained from Verilog. It shows the various modes (privacy, password) and all relevant outputs, including the crowd factor, password match status, and the gate usage count.

