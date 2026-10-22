# Ideal Diode
Author: opilitethesmartdev

This is a small PCB featuring an ideal diode emulator using a comparator and a P-MOSFET.

[![View PCB on KiCanvas](https://hack.club/pcb-badge)](https://kicanvas.org/?repo=opilitethesmartdev%2FIdealDiode)

<img width="852" height="616" alt="image" src="https://github.com/user-attachments/assets/873d8a7c-72e6-48a7-8ada-5619079e41e4" />

<img width="744" height="461" alt="image" src="https://github.com/user-attachments/assets/c8864c66-eec1-4104-84c7-3751e3c57eff" />
<img width="1249" height="845" alt="image" src="https://github.com/user-attachments/assets/f30d5337-86e8-495e-a3fe-d151219c3668" />


# Principle
<img width="1268" height="665" alt="image" src="https://github.com/user-attachments/assets/da8d7c96-b4a5-4f9e-b76e-13e7b4ead7a4" />

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
I used Falstad for the simulation. [Here is the link](https://www.falstad.com/circuit/circuitjs.html?ctz=DwYwlgTgBAZgvAIgIwKgFwM6IAwDpsEECsqYIiSeATAVQOx0DM2AHFQGwCcndqIARoiLZUAB0EIALI1QA3CENQBbTEICmAWiQoAfACgoUYAHcoAD0RN2UFpJZQrNliNg4EAen2HgAYQD2SqIAhhBBaH7QFgjskthOcTFxLEjsqPDIHl5GplFEdNZ0NFCJDjRpbp4GRgAm5pbs9oVx+fbsheUILkp+iNVqMEEArgA2aJlVwLW5+aVxedZtVB1dPQh9AyNjld45iHbNRURIVLPL4zt1CM4HSTGnrp3n2ZclTcVEBWUPItvPUXTYSSzBwNe7pH5ZYAAc0ujhYzgcjGsLE4qW+T2ASiUUAAdkpEABBAAKzgActgqKSAGJnKCyNA4XDsEhQfhqSySVAYCQoKDVDAATzcrOqFFQ-AZjyg3NFGV+wBgsMBNkYJzhqtp3UJJOw5MpNPluyudzothsJq+4IxRoajSKAKBTTOhsuRzVh0kjstFUhRs9dri+zBPomftVwP9wceLqikbecdszshMNjdnNQMj8JcVvlkT2adNGbTLA16KgCikGIAMgBRAAil0z4czMU1q3WQ1GGmGamqfArvJAUOFAmFSn45E6+BQ8oASpdOMdgZxPVGUqhjFaoEogmZZIooJBFPKMJcWBa4ov3dnhaIxfLaw2ouegSWTi-023ev1O2hu73+zFKAhxHCQugnRlsBnSE82NR0zQ-N9aQrTl5RTRBELuRDnCTCZ5yiRgzTeRgiGvDp1ygTcx13fcEBZI86IxU8CKIoppDIss7zlSEsVxfEEDrABZIlmG4KtaXpIC2UQGRpR5VB+SFKV+FlXkJWFGV70hRUokWBxSOKQo12UVYhJE7AxOtV0Zj0ohOBOZk0RzX1YVBPS6AMxzcIuf5PI+YpWHeJyQx8xB2ECxyoDshyPm8v4woi-zwsaBo4pMF4jI8hzMtS9EYzCnLGiREEWDSo1HBaRFkQo5yJlgyLKteXKtwHQgrN0-zGsKsqXliEqApS0q8pg3qkgIYoqFfAhkIoNr8uiPrkgWRbpuG0MXkmmxxuSrab2jFzdMC64BpKnrdMWlJinhGwapC+LomuparvsJC1tCh6XvDB0VSWN77vYTaswmoErzOsLNqvKLV1Bv70tyaGlyIVcnVho15mBJGvT2iF1o65EEUimHavewml2Oom7rhjDxsh46UeJ+66ftUF6ZDYB3HACB9CAA)
