# CUK CONVERTER

Built a DC-DC CUK converter on a perf board using an IRFZ44N MOSFET, TL494 PWM controller, power diodes, capacitors, inductors, and a potentiometer.

The TL494 was used to generate PWM pulses for switching the MOSFET. A potentiometer was used to change the duty cycle and control the output voltage. The capacitors and inductors helped in energy transfer and reducing output ripple.

After assembling and soldering the circuit on a perf board, the converter was tested using an oscilloscope. Gate pulses, inductor voltages, diode current, and output voltage waveforms were captured and analyzed.

The converter was successfully operated in both Continuous Conduction Mode (CCM) and Discontinuous Conduction Mode (DCM), and the hardware results were compared with simulation results for verification.

Components Used : ---
1. IRFZ44N MOSFET
2. TL494 PWM Controller
3. Power Diodes
4. 220 µF Capacitors
5. Inductors(500 uH)
6. Potentiometer(Sliding potentiometer)
7. Perf Board


CIRCUIT DIAGRAM :-- 
<img width="1774" height="887" alt="image" src="https://github.com/user-attachments/assets/8b6ebe27-57f1-4eb4-835d-758dc8ad0c6a" />



 ## Operation
1. MOSFET ON (Switch Closed)
The TL494 turns the IRFZ44N MOSFET ON by applying a PWM gate pulse.

Input voltage charges inductor L1, causing its current to increase and store energy.

At the same time, the coupling capacitor C1 discharges through inductor L2 and the load.
 
The diode is reverse-biased during this interval.

Result:

L1 stores energy.

C1 transfers energy to the output.

L2 maintains a continuous current through the load.

2. MOSFET OFF (Switch Open)
The MOSFET turns OFF.

The current in inductor L1 cannot change instantly, so it flows through the diode.

This current charges the coupling capacitor C1.

The stored energy in L2 continues supplying current to the load.

Result:

L1 transfers its stored energy to C1
	​
L2 continues powering the load.

The output voltage remains smooth due to the output capacitor.


Duty Cycle Control

The potentiometer connected to the TL494 changes the PWM duty cycle.


For an ideal Ćuk converter,

Vout = -D/(1 - D) * Vin
	​
where:

Vout  = Output voltage

Vin = Input voltage

D = PWM duty cycle

The negative sign indicates that the output polarity is inverted with respect to the input.
