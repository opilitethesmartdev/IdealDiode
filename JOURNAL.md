---
title: "IdealDiode"
github: "https://github.com/opilitethesmartdev/idealdiode"
description: "Simple Ideal Diode based on MOSFETs and a comparator"
created_at: "2026-10-18"
total_time: "5h 24m"
---

# October 18, 2026: Designed Ideal Diode PCB
<!-- fabricate:entry 627 -->

!! DISCLAIMER !!
For some reason, i chose journal instead of lapse tracking, but i always make lapses, so hopefulyl it'll be alright.
Lapse link: https://lapse.hackclub.com/timelapse/HqBTf7VsXuRH
-- DISCLAIMER DONE --

I actually first made the design in my other project, PowerSourceArbitrator, adn only made this because i wanted some of them as discrete components, please take a look there:
https://fabricate.hackclub.com/projects/425

The PCB itself wasn't that hard, it was basically just placing the parts and routing them - but i do hope i got the schematics right:
![](https://fabricate.hackclub-assets.com/c25c3b173be5932132cac2474f1929f56347c3dfc668bbac5cdf7f0e203c3bd2/image-png/image.png)
Then the routing:
![](https://fabricate.hackclub-assets.com/2b2506fd0b03e6f8418dba7aa9da70d79ca752da211ae4c0d8852fe3c51c1461/image-png/image.png)
I tried to make the board as small as possible (because i'd be using it on breadboards), but i think it worked out fine.
I also panelized it (because i want a lot of them):
![](https://fabricate.hackclub-assets.com/24e3b31790b28c4d2ebf8e671e5878668217bc749f7dd4544dc4495a343f1453/image-png/image.png)
(jk, thats a mess)
![](https://fabricate.hackclub-assets.com/fb1bb310a37b545740ae2f27b34e4f97576c8befc354b0a539cca97628e4ccbd/image-png/image.png)
Anyways, i'll check what else i need to do then submit it for review!

**Total time spent: 2h**

# October 18, 2026 (entry 2): Prepared for submission
<!-- fabricate:entry 638 -->

So, I prepared the project for submission!

Lapse link: https://lapse.hackclub.com/timelapse/w9MwiGvONKC0

I followed the submission guide, and did all the steps:
- the BOM, which ended up to be 7$ for a panel of 10 boards (yipee)
- the README, describing the project, and it also has a link to the Falstad simulation i used to design the schematic. Anyways, here is the 3d render:
![](https://fabricate.hackclub-assets.com/86aa8458e9c52ffb09c9409140e77bfd5f8f15a94f2083ddae0c3d194f346c3b/image-png/image.png)

(I hope i can get PCBA on everything except the pins, bc uh idk if it'll be nice to hand solder such small SMDs)
Anyways, I hope it works (it would be my first ever ship in this whole org)
:D

**Total time spent: 54m**

# October 19, 2026: Prepared for PCBA
<!-- fabricate:entry 697 -->

Lapse link: https://lapse.hackclub.com/timelapse/Gbnmnvr_Dl3C

I prepared the diode for production. I first reduced the panelling from 10 pieces to 2, given the minimum order quantity is 5, and i dont really need 50 ideal diodes (and it'd be expensive af).

But i also had to quickly reroute the PCB, because JLCPCB only had one sided assembly (at least i couldnt find double sided).
I managed to get it to fit, but idk whether itll work:
![](https://fabricate.hackclub-assets.com/0bc7fb827b8f078110b32649465af9d7e047857853469a7154c1121d18c97032/image-png/image.png)
![](https://fabricate.hackclub-assets.com/e8559967e7ba4b8c58830a750eb7f205ffb696fef04c96c23ff7a5a567b34a52/image-png/image.png)
I also removed the pins from the board because i'll be soldering them by hand - there is this secret technique i found for soldering singular pins that happen to be in the 2.54mm pitch setup (just take a pin header with ALL the pins that would fit, then just take out the pins that you dont have a hole for)
Anyways, i'll see whether i can get the PCBA process done, then i'll ship it

Last thing:
![](https://fabricate.hackclub-assets.com/90327fb05314edd951cdbfcc3feac3e4b6b66467f741f54c2e0089d11ed46293/image-png/image.png)

**Total time spent: 2h**

# October 22, 2026: Fixed project issues
<!-- fabricate:entry 1032 -->

Following the guides from the reviewer, i adjusted the netlabels to be ... a bit more readable:
![](https://fabricate.hackclub-assets.com/6e8d416518d346fd9c9d5496c629abd1f7906c26e44446c292fe15d202be0526/image-png/image.png)
I also ensured the changes propagated into the PCB:
![](https://fabricate.hackclub-assets.com/290a144631e4f9e370faccb970b2e9ae30e7ff24eff32d4b0c2fd2ca8f5fd982/image-png/image.png)
And made sure to put everything neatly into its folder.

I also updated the falstad simulation to be a bit more readable (and less space-optimized):
![](https://fabricate.hackclub-assets.com/1eb5e8bf4529b446eb56ac43011c5e82adb2e130b08dae322a6b49a1f7b621e0/image-png/image.png)
[Use this because falstad's link shortener seems to be down due to PHP's vulnerability](https://www.falstad.com/circuit/circuitjs.html?ctz=DwYwlgTgBAZgvAIgIwKgFwM6IAwDpsEECsqYIiSeATAVQOx0DM2AHFQGwCcndqIARoiLZUAB0EIALI1QA3CENQBbTEICmAWiQoAfACgoUYAHcoAD0RN2UFpJZQrNliNg4EAen2HgAYQD2SqIAhhBBaH7QFgjskthOcTFxLEjsqPDIHl5GplFEdNZ0NFCJDjRpbp4GRgAm5pbs9oVx+fbsheUILkp+iNVqMEEArgA2aJlVwLW5+aVxedZtVB1dPQh9AyNjld45iHbNRURIVLPL4zt1CM4HSTGnrp3n2ZclTcVEBWUPItvPUXTYSSzBwNe7pH5ZYAAc0ujhYzgcjGsLE4qW+T2ASiUUAAdkpEABBAAKzgActgqKSAGJnKCyNA4XDsEhQfhqSySVAYCQoKDVDAATzcrOqFFQ-AZjyg3NFGV+wBgsMBNkYJzhqtp3UJJOw5MpNPluyudzothsJq+4IxRoajSKAKBTTOhsuRzVh0kjstFUhRs9dri+zBPomftVwP9wceLqikbecdszshMNjdnNQMj8JcVvlkT2adNGbTLA16KgCikGIAMgBRAAil0z4czMU1q3WQ1GGmGamqfArvJAUOFAmFSn45E6+BQ8oASpdOMdgZxPVGUqhjFaoEogmZZIooJBFPKMJcWBa4ov3dnhaIxfLaw2ouegSWTi-023ev1O2hu73+zFKAhxHCQugnRlsBnSE82NR0zQ-N9aQrTl5RTRBELuRDnCTCZ5yiRgzTeRgiGvDp1ygTcx13fcEBZI86IxU8CKIoppDIss7zlSEsVxfEEDrABZIlmG4KtaXpIC2UQGRpR5VB+SFKV+FlXkJWFGV70hRUokWBxSOKQo12UVYhJE7AxOtV0Zj0ohOBOZk0RzX1YVBPS6AMxzcIuf5PI+YpWHeJyQx8xB2ECxyoDshyPm8v4woi-zwsaBo4pMF4jI8hzMtS9EYzCnLGiREEWDSo1HBaRFkQo5yJlgyLKteXKtwHQgrN0-zGsKsqXliEqApS0q8pg3qkgIYoqFfAhkIoNr8uiPrkgWRbpuG0MXkmmxxuSrab2jFzdMC64BpKnrdMWlJinhGwapC+LomuparvsJC1tCh6XvDB0VSWN77vYTaswmoErzOsLNqvKLV1Bv70tyaGlyIVcnVho15mBJGvT2iF1o65EEUimHavewml2Oom7rhjDxsh46UeJ+66ftUF6ZDYB3HACB9CAA)

Also, i decided i would *NOT* do PCBA and instead (try) to hand solder it, because taxes alone cost 14$:
![](https://fabricate.hackclub-assets.com/dfae32a81e8bce41125c5d9d492ee7295e072bc577da015adc62281369fc57f1/image-png/image.png)
fahhhh
Well then, off we go.
(I'll put the PCBA prices for now, but i'll be resubmitting with the new prices)

**Total time spent: 30m**
