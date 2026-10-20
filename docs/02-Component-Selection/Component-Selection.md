---
title: Component Selection
---
**Input Op amp**

1. CA3140AEZ MOSFET‑input op amp

    ![](TL081CP_CA3140AEZ.png)

    * $3.78/each
    * [link to product](https://www.digikey.com/en/products/detail/renesas-electronics-corporation/CA3140AEZ/821386)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Very high input impedance ideal for weak heart‑rate sensor signals                           | Not rail‑to‑rail limits output swing in low voltage designs |
    | Wide supply range (4 V–36 V)                      |Older design with limited availability                                        |
    | Low offset voltage stable baseline for pulse detection| Requires external biasing and filtering|


2. ### MCP6004-I/P Low-Power Quad Rail-to-Rail Op Amp

![](MCP6004IP.png)

* ~$0.60/each
* [Link to product](https://www.digikey.com/en/products/detail/microchip-technology/MCP6004-I-P/523060)

| Pros | Cons |
|--------|--------|
| Rail-to-rail input and output maximizes signal range on 3.3 V and 5 V systems | Lower bandwidth (1 MHz) than many high-speed op-amps |
| Very low power consumption (100 µA typical per amplifier) | Not ideal for high-frequency or RF applications |
| Includes four op-amps in one package, reducing PCB space and cost | Moderate input offset voltage (4.5 mV typical) |
| Operates from 1.8 V to 6 V, making it ideal for battery-powered sensor circuits | Limited slew rate (0.6 V/µs) for fast-changing signals |
| Extremely low input bias current (1 pA typical) works well with photodiodes and sensor interfaces | |

 
3. TL081CP JFET‑input op amp

    ![](TL081CP_CA3140AEZ.png)

    * $0.65/each
    * [link to product](https://www.digikey.com/en/products/detail/texas-instruments/TL081CP/458)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | JFET‑input like CA3140 excellent for high impedance heart‑rate sensors | Requires dual supply for full performance in some configurations |
    | High slew rate (13 V/µs) preserves pulse waveform shape               | Not rail to rail reduced output swing at low voltages           |
    | Through‑hole DIP‑8 easy prototyping and breadboard‑friendly           | Slightly higher input bias current than CA3140                   |

### Why the MCP6004 is the best op‑amp choice
The MCP6004 is a good op amp because it is low-power, rail-to-rail, and works with 3.3 V or 5 V supplies. It also includes four op amps in one chip, making it a compact and cost-effective choice for sensor and microcontroller projects like a heart rate monitor.

   **IR TX and RX Pair**

   
1. TSAL6200 (IR Transmitter) + TSOP38238 (IR Receiver)

    ![](TSAL6200.png)
    ![](TSOP38238.png)

    * TX: $0.72/each — TSAL6200
    * RX: $1.18/each — TSOP38238
    * [link to TX](https://www.digikey.com/en/products/detail/vishay-semiconductor-opto-division/TSAL6200/1681339)
    * [link to RX](https://www.digikey.com/en/products/detail/vishay-semiconductor-opto-division/TSOP38238/1025779)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Very strong IR output excellent for reflective heart‑rate sensing | Requires 38 kHz modulation for proper RX operation |
    | Through‑hole easy to mount and prototype | RX has narrow detection bandwidth |
    | High sensitivity receiver reduces noise in pulse detection | TX requires current‑limiting resistor |
   

3. SFH4550 (IR Transmitter) + SFH213 (IR Photodiode)

    ![](SFH-4550.png)
    ![](SFH-213.png)

    * TX: $0.48/each — SFH4550
    * RX: $0.62/each — SFH213
    * [link to TX](https://www.digikey.com/en/products/detail/osram-opto-semiconductors-inc/SFH4550/720473)
    * [link to RX](https://www.digikey.com/en/products/detail/ams-osram-ag/SFH-213/607286)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Photodiode RX allows analog signal extraction ideal for heart‑rate waveform | Requires external amplifier (op‑amp stage) |
    | Wide‑angle IR LED improves skin illumination | More sensitive to ambient light than demodulated receivers |
    | Very inexpensive pair                      | Requires careful PCB layout for noise reduction |

5. LTE‑4208 (IR LED) + LTR‑4206E (IR Phototransistor)

    ![](LTE-4208.png)
    ![](LTR-4206E.png)
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
