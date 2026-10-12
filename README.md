# ATX Regulated power supply
Converting a conventional half-bridge ATX power supply into a regulated 1–30 V, 0.1–10 A bench power supply.

This project documents my second, successful attempt at converting a standard ATX power supply into an adjustable power supply. The bench PS turned out to have a usable voltage range of 1.1-32V and current limiting range of 0.2-12A. ATX PSUs with a combined PWM controller+supervisor IC are generally easier to modify than those with separate controllers, although the latter can also be converted.
For this build, I chose an old FSP Group ATX300F based on the FSP3528 PWM controller.

Power supply characteristics:

<img width="654" height="377" alt="FSP Group ATX300F" src="https://github.com/user-attachments/assets/01ba46af-4872-4b03-a961-55c03488b5ec" />

The following FSP3528 pinout is provided for reference only. The original controller will be removed during the modification, and the pinout shown here doesn't fully reflect the implementation in my particular power supply:

<img width="662" height="538" alt="FSP 3528 pinout" src="https://github.com/user-attachments/assets/aa2cf8f9-4406-42b9-b35a-b3dc68edbbe9" />

A lot of old ATX PSUs have typical schematic, so that's not a big deal if your isn't publicly available. My repurposing is based on Roberto Chirio's scheme for 1-30V and 0.1-10A regulated power supply. Go check [his site](https://www.chirio.com/switching_power_supply_atx.htm) and schematics as well. I made some changes in used components according to what I had to use more common values instead of more specific ones and to use as low amount of potentiometers as possible (ended up using only 2 (other 2 are Amps and Voltage pots so not in count)).

Original R. Chirio's schematic:
<img width="1189" height="764" alt="Roberto Chirio's schematic" src="https://github.com/user-attachments/assets/b34e73f8-2d35-46a1-b53a-108d69fd12b6" />

The ease of converting consists in using TL494 PWM generator instead of any controlling IC used in PSU. I used the module on small separate board where were all the components needed for the TL494. That was a really convenient solution because I fried the first PSU and did't want to repair it anymore. So it was pretty easy to solder out that small amount of wires that lead to the TL494 and move the whole module to another PSU.


