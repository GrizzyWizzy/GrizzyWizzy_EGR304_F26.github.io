---
title: Component Selection Example
---
**Input Op amp**

1. CA3140AEZ MOSFET‑input op amp

    ![](image1.png)

    * $3.78/each
    * [link to product](http://www.digikey.com/product-detail/en/ECS-40.3-S-5PX-TR/XC1259TR-ND/827366)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Very high input impedance ideal for weak heart‑rate sensor signals                           | Not rail‑to‑rail limits output swing in low voltage designs |
    | Wide supply range (4 V–36 V)                      |Older design with limited availability                                        |
    | Low offset voltage stable baseline for pulse detection| Requires external biasing and filtering|


2. LT1498IN8#PBF low‑noise precision op amp

    ![](image3.png)

    * $11.67/each
    * [link to product](https://www.digikey.com/en/products/detail/analog-devices-inc/LT1498IN8-PBF/891552)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Low input bias current ideal for photoplethysmography (PPG) sensors | More expensive increases BOM cost |
    | High slew rate preserves pulse waveform shape                      | Requires careful PCB layout to minimize noise |
    | Wide temperature range  suitable for fitness/outdoor HR devices     | |
 
3. TL081CP JFET‑input op amp

    ![](image2.png)

    * $0.65/each
    * [link to product](https://www.digikey.com/en/products/detail/texas-instruments/TL081CP/458)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | JFET‑input like CA3140 excellent for high impedance heart‑rate sensors | Requires dual supply for full performance in some configurations |
    | High slew rate (13 V/µs) preserves pulse waveform shape               | Not rail to rail reduced output swing at low voltages           |
    | Through‑hole DIP‑8 easy prototyping and breadboard‑friendly           | Slightly higher input bias current than CA3140                   |

### Why the CA3140AMZ is the best op‑amp choice
The CA3140AMZ works best for your heart‑rate monitor because it’s one of the few through hole op amps that performs reliably at a single 5 V supply while still offering extremely high input impedance and low offset—two traits that are essential when amplifying the tiny current changes produced by a photodiode. Its MOSFET input architecture makes it far more forgiving in low signal, high noise environments, and its wide supply range gives you design flexibility on your custom PCB without forcing dual‑rail power. Overall, it provides clean, stable analog gain with minimal fuss, which is exactly what a reflective PPG circuit needs.


   **IR TX and RX Pair**

   
1. TSAL6200 (IR Transmitter) + TSOP38238 (IR Receiver)

    ![](image1.png)

    * TX: $0.72/each — TSAL6200
    * RX: $1.18/each — TSOP38238
    * [link to TX](https://www.digikey.com/en/products/detail/vishay-semiconductor-opto-division/TSAL6200/1681339)
    * [link to RX](https://www.digikey.com/en/products/detail/vishay-semiconductor-opto-division/TSOP38238/1025779)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Very strong IR output excellent for reflective heart‑rate sensing | Requires 38 kHz modulation for proper RX operation |
    | Through‑hole easy to mount and prototype | RX has narrow detection bandwidth |
    | High sensitivity receiver reduces noise in pulse detection | TX requires current‑limiting resistor |
   

2. SFH4550 (IR Transmitter) + SFH213 (IR Photodiode)

    ![](image2.png)

    * TX: $0.48/each — SFH4550
    * RX: $0.62/each — SFH213
    * [link to TX](https://www.digikey.com/en/products/detail/osram-opto-semiconductors-inc/SFH4550/720473)
    * [link to RX](https://www.digikey.com/en/products/detail/ams-osram-ag/SFH-213/607286)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Photodiode RX allows analog signal extraction ideal for heart‑rate waveform | Requires external amplifier (op‑amp stage) |
    | Wide‑angle IR LED improves skin illumination | More sensitive to ambient light than demodulated receivers |
    | Very inexpensive pair                      | Requires careful PCB layout for noise reduction |

3. LTE‑4208 (IR LED) + LTR‑4206E (IR Phototransistor)

    ![](image3.png)

    * TX: $0.38/each — LTE‑4208
    * RX: $0.52/each — LTR‑4206E
    * [link to TX](https://www.digikey.com/en/products/detail/liteon/LTE-4208/121707)
    * [link to RX](https://www.digikey.com/en/products/detail/liteon/LTR-4206E/121710)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Matched LED + phototransistor pair ideal for reflective heart‑rate sensing | Phototransistor slower response than photodiode |
    | Through‑hole DIP package easy to mount and prototype | More sensitive to ambient IR interference |
    | Good sensitivity for low cost PPG setups | Requires external biasing and filtering circuitry |

### Why the SFH4550 + SFH213 pair is the best IR choice
The SFH4550 + SFH213 pair is ideal for a DIY heart rate sensor because it gives you a true analog photoplethysmography signal rather than a digital IR presence output. The SFH4550’s wide angle IR emission illuminates the skin evenly while the SFH213 photodiode produces a fast, linear current response that captures subtle blood‑volume changes accurately. Both parts are through hole, easy to mount on a custom PCB, and work perfectly with a transimpedance amplifier like the CA3140. This combination yields a clean, responsive waveform that can be filtered and amplified without fighting the limitations of slower phototransistors or demodulated IR receivers.
