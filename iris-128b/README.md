# Iris-128B

[!NOTE]
Detail documentation and user guides can be found at https://docs.openic.org/iris-128/iris-128b.

<br>

![Iris-128](../images/iris-128b-system-labels.jpg)

*Fig. 1. Iris-128B Neural Interface.*

## Description

### Overview

A **128-channel neural interface capable of stimulation and recording**.

This project develops a system that can stimulate and record from 128 channels using commercially available ICs and integrates into existing commercially available controllers (Intan RHS system). This can be used for small animal, anesthetized electrophysiology, non-human primates, or could be applied to clinical, intraoperative human use cases.

### Iris 128B Architecture

*The Iris 128B system consists of 2 boards: the headstage and the adapter.*

* The **headstage** is a small electronic system placed on top of or near the electrophysiological signals being recorded.
* It uses **commercially available off-the-shelf components**.
* The **adapter board** receives signals from the headstage (through the 80 pin nanopitch Molex connector and cable) and breaks them out into cables that interface with the **Intan Rec/Stim Controller**.

![Iris-128](../images/iris-128b-architecture.jpg)

*Fig. 2. System architecture.*

<br>

## Specifications

* Recording and stimulation from all 128 channels.
* Compatible with Intan Recording Controller and Intan Stim/Record Controller.
* *SEAM8 Samtec* connector for interfacing with 128-ch electrode array and compatible with *BlackRock Cereplex E headstages*.
* The *headstage* has a size of 27 x 44 mm$^2$.
* *Molex Nanopitch 76-POS* connector to interface with *Adapter* board through a single cable.
* *Adapter* board draws power from power supply.
* The *adapter* has a size of 57 x 58 mm$^2$.

<br>

## File Structure

### Top Folders: /iris-128b

| Folder  | Subfolders                  | Description    |
| :-----: | :-------------------------- | :------------- |
| pcb | iris-128b <br> iris-128b-adapter <br> libraries | Project, design, and fabrication files related to Iris-128B headstage PCB fabrication and assembly. <br> Project, design, and fabrication files related to Iris-128B adapter PCB fabrication and assembly. <br> Ki-Cad libraries and common files used in PCBs |

<br>

### PCB Folders: /iris-128b/pcb/

| Folder  | Subfolders                  | Description    |
| :-----: | :-------------------------- | :------------- |
| . / |  | Project and design files related to Iris128B. |
| manufacturing |  gerber <br> assembly <br> bom | Gerber files for fabrication of `Iris-PCB`. <br> Assembly files for `Iris-PCB`. <br> Bill of Materials for `Iris-PCB`. |

<br>

## File Types

| File | Folder | Description |
| :--- | :----- | :---------- |
| README.md | iris-128x | Description of Iris-128X system. |
| kicad-files | iris-128x / pcb / | Ki-Cad project and design files. |
| gerber-files | iris-128x / pcb / manufacturing / gerber | Gerber files. |
| iris-128x-all-pos.csv | iris-128x / pcb / manufacturing / assembly | Assembly files in `csv` format.|
| iris-128x_bom.csv | iris-128x / pcb / manufacturing / bom | Bill of materials in `csv` format. |
| symbol-libraries | iris-128x / pcb / libraries | Ki-Cad symbol libraries used in PCBs. |
| footprint-libraries | iris-128x / pcb / libraries | Ki-Cad footprint libraries used in PCBs. |