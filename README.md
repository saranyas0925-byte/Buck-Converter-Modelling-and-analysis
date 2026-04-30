# Buck-Converter-Modelling-and-analysis
# Buck Converter Design and Modeling (Simulation Project)
## Project Overview
This project models and analyzes a buck DC-DC converter using MATLAB/Simulink  and simscape electrical,examining open loop switching behaviour and volateg mode feedback control implementation
A buck converter is a circuit that:
- Takes a higher DC voltage
- Converts it into a lower DC voltage
The project is learning based and helps in understanding basic power electronics concepts through simulation.
![Project Overview](screenshots/01_project_overview_simulink_model.png)
## 2. Motivation
Buck converters are commonly used in:
- Electric vehicles
- Electronic systems
This project was done to:
- analyze buck converter switching behaviour under open loop and closed loop conditions
- study voltage mode feedback control implementstion using simscape electrical
- understand duty cycle to output voltage relationship in DC-DC step down conversion
## 3. System Description
The system studied is a buck (step-down) DC–DC converter.
- Input: 12v DC voltage source  
- Output: 6v (refernce) DC voltage  
- Load: Resistive load
- switching frequency: approximately 10khz
- duty cycle range: 25 % to 75%(open loop analysis)
![System Description](screenshots/02_system_block_level_view.png)
## 4. Circuit Components Used
- DC voltage source
- MOSFET (acts as a switch)
- Diode
- Inductor
- Capacitor
- Load resistor
Each component plays a role in reducing and smoothing the ripples in output voltage.
![Circuit Components](screenshots/03_base_circuit_components.png)
## 5. Base Circuit Construction
The power stage was constructed using simscape electrical components -dc voltage source,mosfet switch,freewheeling diode,filter inductor,output capacitor and load resistor.
- All components are connected correctly
-feedback control is not yet used
![Base Circuit Connections](screenshots/04_base_circuit_connections.png)  
![Base Circuit Complete](screenshots/05_base_circuit_complete.png)
## 6. Open-Loop Operation
- The MOSFET is driven using a fixed duty cycle
- The output voltage is not automatically controlled
By changing the duty cycle:
- Output voltage changes
- The relationship between duty cycle and output voltage is observed
![PWM Settings](screenshots/06_open_loop_pwm_settings.png)  
![Open Loop Output voltage](IMG_0947.jpeg)
## 7. Switching Action Observation
The MOSFET switches ON and OFF repeatedly.
There is a point in the circuit where:
- Voltage changes very fast
- This point connects the MOSFET, diode, and inductor
This fast switching impacts how energy flows to the output.
![Switching Node Waveform](screenshots/08_switching_node_voltage_waveform.png)  
![Switching Node Zoomed](screenshots/09_switching_node_zoomed_view.png)
## 8. Introduction of Feedback Concept
To increase output voltage control, feedback is introduced.
- Output voltage is measured
- It is compared with a reference voltage
- The difference is used to adjust switching
![Feedback Path](screenshots/10_feedback_signal_path.png)
## 9. Voltage based Control
- Only output voltage is used for feedback
- No current sensor is used
Steps:
1. Measure output voltage
2. Compare with reference voltage
3. Generate control signal
4. Adjust MOSFET switching
![Voltage Mode Control Blocks](screenshots/11_voltage_mode_control_blocks.png)  
![Error Signal](screenshots/12_error_signal_generation.png)
## 10. Gate Drive Implementation
The MOSFET requires a voltage at its gate to switch ON and OFF.
- A controlled voltage source is used
- It applies the required gate-to-source voltage
![Gate Drive Source](screenshots/13_gate_drive_controlled_voltage_source.png)  
![Gate Source Connection](screenshots/14_gate_source_connection.png)
## 11. Control Implementation
- Feedback signals are connected
- Control signals are routed correctly
![Closed Loop  Structure Overview](91C4B6F1-1383-4506-8DE0-625FAA6C65C2.png)  
![Control to Gate Signal](screenshots/16_control_signal_to_gate.png)
## 12. Results and Observations
- Open-loop output voltage confirmed to follow duty cycle relationship-higher duty cycle produces hugher output voltage approaching 6v reference
- Switching node voltage transistions observed at gate drive frequency of 10khz
- Voltage mode feedback control structure implemented with error signal generation between measured output and 6v reference.
![Open vs Closed Loop](screenshots/17_open_loop_vs_closed_loop_comparison.png)  
![Output Voltage Response](IMG_0944.jpeg)
## 13. Tools Used
- MATLAB
- Simulink
- Simscape Electrical
## 14. Technical Outcomes
- verified Buck converter step down operation with output voltage voltage follwoing duty cycle
- observed Switching node voltage tranistions between high and low states 
- Demonstrated open-loop duty cycle  to output voltage relationship 
- identified and resolved signal type compatability challenges in simscape simulink interference
## 15. Conclusion
This project provides a clear and simple understanding of buck converter operation and basic control using simulation.
It builds a strong foundation for further learning in:
- Power electronics
- Control systems
- Electric vehicle power systems
![Final Model](screenshots/19_final_simulink_model.png)
