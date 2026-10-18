# Ideal Diode
Author: opilitethesmartdev

This is a small PCB featuring an ideal diode emulator using a comparator and a P-MOSFET.

[![View PCB on KiCanvas](https://hack.club/pcb-badge)](https://kicanvas.org/?repo=opilitethesmartdev%2FIdealDiode)

<img width="849" height="542" alt="image" src="https://github.com/user-attachments/assets/d8c95fc5-d186-4423-b2c2-8f05bab134cd" />
<img width="390" height="277" alt="image" src="https://github.com/user-attachments/assets/4c857e56-f97c-4ad5-af75-87c68062b213" />
<img width="378" height="278" alt="image" src="https://github.com/user-attachments/assets/178656e4-ba4a-4801-9135-ed59ab32fa96" />

# Principle
<img width="246" height="370" alt="image" src="https://github.com/user-attachments/assets/97d23efa-05b2-4fcd-b588-a49541965718" />

1. It uses two diodes to let power in from any side without connecting them, used to feed the comparator and the voltages for the MOSFETS
2. a P-MOS sits between the diodes, with its internal diode directed at the side to be blocked.
3. This P-MOS is pulled high by the same two diodes from #1
4. An N-MOS sits below the P-MOS gate, and will pull it down when activated (turning the P-MOS on)
5. A comparator compares the two sides, and when the forward side is higher than the reverse side, it pulls its output high,
activating the N-MOS, which pulls the P-MOS down, which lets current flow

# Performance
The performance of such constructs is dependent on the P-MOS they use - for simulation, I have used the specs of an DMP3099L P-MOS
(~100mOhm Rdson at -5V), which yield about a 0.1V drop at 1A current - much lower for smaller currents.
However, this PCB component uses the AO3401A, which has a much lower RDSon (about 45 mOhm at the same voltage)

# Simulation
I used Falstad for the simulation. [Here is the link](https://www.falstad.com/circuit/circuitjs.html?ctz=DwYwlgTgBAZgvAIgIwKgFwM6IAwDpsEECsqYIiSeATAVQOx0DM2AHFQGwCcndqIARoiLZUAB0EIALI1QA3CENQBbTEICmAWiQoAfACgoUYAHcoAD0TsqkqCyTsoVm3Rqp4CEQHp9hk+cR02M7sLFCBNiwEbjgI3gZGphYI7C5hRFRhQWEh0R6xPkbQSSkZdOmORA50ObAxUArIhPnxfsWV2aEhodUsuV4FrZbtPRUOkSK1eXG+iZaS2GkZ7MM17v0ts8ks3SGZzul9zb5FQ2P2o7ZRkxMNlFHTCf4ITGORYYxVrtdHj8WpLOwbCVbJFDg9BslrCCFk5bPYwQNNoCFgCgfNoQiWgBhAD2SlEAEMIAS0DiTsl2qiLnZ2LkUOCkVCXDD0czMb4ACZPcJhGh7RaHKBKHGIDlqGAEgCuABs0D9gFziqy+ciBd8hSKEGKJTK5QynpUFsyoEROKUvmt5UjKedgTT2b8Ah9eSiCC6HRDVcblp8Jpb9UkecaXu7vuCAObcrIsSTdaOAj2bHksRilaOxj1KJRQAB2SkQAEEAAqRABy2CopYAYoLZGgcLhlqh+GoApJUBgJCgoByMABPOr8DkUZv1vJQTvD5DymBPO3nZPw9XCwsl7Dlys1gOIcZhGOXI0WmLbrbdPlBo9TREGs0uxxMy-rGYGqhnhaG0P+69JIhIc3v19P2Pb8hEA410m6GMPUjH9AKpCCMTDAZyQQuh9wQlMqEFBp23BAAZABRAARF9Qkwk04ITZdNW1KVZQ0aU1A5Phbj4cM6gEOolH4cgPHwekBgAJSeGM32hIDkFpKBjEtIUCTMWRFCgSBFHBDARLdY1RIkiZRBHfDiI0lFUwPWwqNklctXFOi0AYpiWJHKAQHY8dOPHbjeLwbABJacldzQiI3Uw7DEFwgYYJ3ILAVM7Y-WAlphKSSRouNaR-zpKSZK4+TFIQEhlIaEg1KeZLnD5X90vVPTp3BLNc3zBAiIAWSLZhuDw2sx27FtEBkCcu1QXsB3HIdHP4McJknfSBlnP5SnKYE2UmbtLOa1rsHaq05yhWLHHRWLE25Z1drtUEkL0YBPHACB9CAA)
