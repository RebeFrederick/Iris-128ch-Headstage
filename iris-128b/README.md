# Iris-128S

![Iris-128](./images/iris-128s-system.jpg)

*Fig. 1. System architecture.*

## Description

`IRIS-128S`.

### Overview

A **128-channel neural interface capable of stimulation and recording**.

This project develops a system that can stimulate and record from 128 channels using commercially available ICs and integrates into existing commercially available controllers (Intan RHS system). This can be used for small animal, anesthetized electrophysiology, non-human primates, or could be applied to clinical, intraoperative human use cases.

### Iris 128S Architecture

*The Iris 128S system consists of 2 boards: the headstage and the adapter.*

* The **headstage** is a small electronic system placed on top of or near the electrophysiological signals being recorded.
* It uses **commercially available off-the-shelf components**.
* The **adapter board** receives signals from the headstage and breaks them out into cables that interface with the **Intan Rec/Stim Controller**.

### Front Iris 128S
![Iris-128](./images/iris-128b-front.jpg)

Front of Iris 128S with a SEARAY 160 pin connector, four RHS2000 ICs, an 80-pin Molex connector, pinouts, decoupling capacitors, and terminating resistors. Mounting holes are M2.

### Back Iris 128S
![Iris-128](./images/iris-128b-back.jpg)
Back of Iris 128S with four RHS2000 ICs.

## Iris 128S Details

![Iris-128](./images/iris-128b-schematic.jpg)
*Fig. 1. Schematic of Iris 128B.*

### Components

| Component | Part                                         | Manufacturer | Description       |
| --------- | -------------------------------------------- | ------------ | ----------------- |
| J1        | SEAM8-20-S02.0-S-08-3                        | Samtec       | 160-pin connector |
| U1–U8     | RHS2116                                      | Intan        | Stimulation chip  |
| J2        | CONN NANO-PITCH I/O RCPT 80P RA, #1731620131 | Molex        | 80-pin connector  |

## Specifications

### Electrode128

*This is the output/input that interfaces with the electrophysiological signals.*

We are currently using the **SEAM8 Samtec connector** for interfacing with a 128-ch electrode array.
The footprint on the headstage is shown below.

The left and right two rows are dedicated for **GND** and **REF** connectors.
The remaining **16×8** are for connecting to the 128 electrodes.

This is the same footprint/connector used with **BlackRock Cereplex E headstages**, maintaining compatibility with interchangeable thin-film interfaces.

![Iris-128](./images/iris-128b-160connector.jpg)

*Fig. 2. Footprint of SEAM 160 (8x20) pin connector. Outer two rows are reserved for reference and gnd. The 3.3V and LED are unconnected. The locations of these gnd and reference pins are meant to match the Cereplex E headstages. We have used thin-films interchangeably between the two systems so we have preserved that footprint in this version of the headstage. The footprint is labeled C#, indicating the chip it routes to, and E# indicating the electrode.*

### Chip1 through Chip8

These are **RHS2116 chips** (QFN package) from Intan Technologies.
There are 8 total chips (16 electrodes each) communicating with the controller via **SPI (Serial Peripheral Interface)**.

SPI communication lines:

* Chip Select (CS)
* Serial Clock (SCLK)
* Serial Data Input (MOSI)
* Serial Data Output (MISO)

Because **LVDS (Low-Voltage Differential Signaling)** is used to decrease noise sensitivity, each line type has a + and – pair:

* CS+, CS–
* SCLK+, SCLK–
* MOSI+, MOSI–
* MISO+, MISO–

LVDS transmits low-voltage paired differential signals, reducing electromagnetic interference (EMI).

**Power requirements:**

* ±3.3V to ±7V for stimulation
* 3.3V for digital logic and analog power
* ~50 mW consumption (RHS2116, 16 channels recording)

For comparison:

* **RHD2164**: 3.3V single supply, no stimulation, ~75 mW for 64 channels.

SPI lines are routed through the **adapter board** to the **Intan RHS controller ports A–D**.
SCLK and CS lines are shared between all chips, while data input/output lines are individually connected.

### Fabrication Notes

If you use the commercially available **Molex cables**, note:

* In this design, pins *Chip 5 – MOSI+* and *Chip 5 – MOSI–* connect to **unused pins** on the cable (A20 and A21).

#### Table 4. PCB Specifications

| PCB Specification               | Value           |
| ------------------------------- | --------------- |
| Size                            | 30.2 × 25.5 mm² |
| Trace Width / Space             | 3 mil / 3 mil   |
| Layers                          | 8               |
| Thru-Hole Via (Hole / Diameter) | 8 mil / 14 mil  |
| Microvia (Hole / Diameter)      | 6 mil / 12 mil  |
| Thickness                       | 0.039 in (1 mm) |
| Surface Finish                  | ENIG            |
| Copper Weight                   | 1 oz            |

![Iris-128](./images/iris-128b-layers.jpg)


#### Table 5. Headstage PCB Stack Up

| Layer | Notes                                                      |
| ----- | ---------------------------------------------------------- |
| 1     | Minimal local routing + GND plane                          |
|       | *Prepreg*                                                  |
| 2     | Supplies + SPI + some electrode signal routing + GND plane |
|       | *Core*                                                     |
| 3     | GND plane                                                  |
|       | *Prepreg*                                                  |
| 4     | Signal routing + some supply traces + GND plane            |
|       | *Core*                                                     |
| 5     | Signal routing + GND plane                                 |
|       | *Prepreg*                                                  |
| 6     | Signal routing + GND plane                                 |
|       | *Core*                                                     |
| 7     | GND plane + SPI routing                                    |
|       | *Prepreg*                                                  |
| 8     | Minimal local routing + GND plane                          |

