# Iris-128S

![Iris-128S System](../images/iris-128s-system.jpg)
<p style="text-align:center"><i><b>Figure 1.</b> Iris-128S Neural Interface.</i></p>

## Description

The Iris-128S neural interface consists of 2 boards: the *headstage* and the *adapter*. The *headstage* is a small electronic board that is normally placed on top of or nearby the animal model being studied. It has been designed to be as small as possible while using standard, commercially available off-the-shelf components. The *adapter* is a small electronic board which has been designed to interface with the Intan Recording Controller, the Intan Rec/Stim Controller, and a programmer/computer to program the switches in the *headstage*.

```mermaid
graph LR
    c0["128-Ch
        Electrode
        Array"]
    c1["`**Headstage**`"]
    c2["`**Adapter**`"]
    c3["Intan Rec
        Controller"]
    c4["Intan Rec/Stim
        Controller"]
    c5["Programmer"]
    c0 <--> c1
    c1 <----> c2
    c2 <--> c3
    c2 <--> c4
    c2 <--> c5
```
<p style="text-align:center"><i><b>Figure 2.</b> System Architecture of Iris-128S.</i></p>


### Schematic

![Iris-128S System](../images/iris-128b-schematic.jpg)
<p style="text-align:center"><i><b>Figure 3.</b> Schematic of Iris-128S.</i></p>

## Specifications

* The headstage consists of the input 128-pin connector (*Conn1*), the analog switches (*Switches*), the recording (*R64*) and stimulation (*S16*) chips, and the output 36-pin connector (*Conn2*). This system is shown in the figure below, where the numbers inside the *Conn1* and *Conn2* blocks represent a set of pins from the connector.
* The PCB for the *headstage* has a size of 30.2 x 25.5 mm$^2$.
* *SEAM8 Samtec* connector for interfacing with 128-ch electrode array.
* 

## File Structure

### Top Folders

| Folder  | Subfolders                  | Description    |
| :-----: | :-------------------------- | :------------- |
| iris-128x / pcb | iris-128x <br> iris-128x-adapter <br> libraries <br> datasheets | Project, design, and fabrication files related to Iris-128X headstage PCB fabrication and assembly. <br> Project, design, and fabrication files related to Iris-128X adapter PCB fabrication and assembly. <br> Ki-Cad libraries and common files used in PCBs <br> Datasheets of components used in PCBs. |
| iris-128s / mcu | controller | Project and firmware files related to MCU programming. |
| images    |        | image files used in README and description files. |

### PCB Folders

| Folder  | Subfolders                  | Description    |
| :-----: | :-------------------------- | :------------- |
| iris-128x / pcb / `Iris-PCB` |  <br> manufacturing / gerber <br> manufacturing / assembly <br> manufacturing / bom | Project and design files related to `Iris-PCB`. <br> Gerber files for fabrication of `Iris-PCB`. <br> Assembly files for `Iris-PCB`. <br> Bill of Materials for `Iris-PCB`. |

### MCU Folders

| Folder  | Subfolders                  | Description    |
| :-----: | :-------------------------- | :------------- |
| iris-128x / mcu / controller | Core / Inc <br> Core / Src <br> Core / Startup <br> Debug <br> Drivers | `C` library files. <br> `C` source files. <br> Assembly startup file. <br> Debug-related files. <br> Driver files for target MCU. |

## File Types

| File | Folder | Description |
| :--- | :----- | :---------- |
| README.md | iris-128x | Description of Iris-128X system. |
| pcb-fab-specs.md | iris-128x / pcb | Specifications for the fabricatin of `Iris-PCB`.
| kicad-files | iris-128x / pcb / `Iris-PCB` | Ki-Cad project and design files. |
| iris-128x-schematic.pdf | iris-128x / pcb / `Iris-PCB` | PDF of PCB schematic. |
| gerber-files | iris-128x / pcb / `Iris-PCB` / manufacturing / gerber | Gerber files. |
| iris-128x-all-pos.csv | iris-128x / pcb / `Iris-PCB` / manufacturing / assembly | Assembly files in `csv` format. |
| iris-128x_bom.csv | iris-128x / pcb / `Iris-PCB` / manufacturing / bom | Bill of materials in `csv` format. |
| datasheet-files.pdf | iris-128x / pcb / datasheets | PDFs of the datasheets of all components used in PCBs. |
| symbol-libraries | iris-128x / pcb / libraries | Ki-Cad symbol libraries used in PCBs. |
| footprint-libraries | iris-128x / pcb / libraries | Ki-Cad footprint libraries used in PCBs. |
| main.c | iris-128s / mcu / controller / Core / Src | Main `C` file running on MCU. |
| c-files | iris-128s / mcu / controller / Core | `C` files related to MCU firmware. |
| c-files | iris-128s / mcu / controller / Debug | `C` files related to MCU debugging. |
| c-files | iris-128s / mcu / controller / Drivers | `C` file related to MCU drivers. |
| .*project | iris-128s / mcu / controller | STM32CubeIDE project-related files. |
| *.launch | iris-128s / mcu / controller | STM32CubeIDE debug-related files. |
| *.ioc | iris-128s / mcu / controller | STM32CubeIDE MCU system configuration file. |
| *.id | iris-128s / mcu / controller | STM32CubeIDE MCU memory configuration file. |