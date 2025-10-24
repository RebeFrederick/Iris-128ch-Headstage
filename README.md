# Iris-128

Open-source 128-channel headstages for neural stimulation and recording.

| Type | Description | Link |
| :--: | :---------- | :--- |
| Iris-128B | Fully bidirectional headstage with recording or stimulation across all 128 electrode channels. | [iris-128s/README.md](iris-128s/README.md) |
| Iris-128S | Selective stimulation headstage with recording from 128 channels and stimulation on 16 simultaneous channels out of 32 available stimulation channels. |

## File Structure

| Folder  | Subfolder                   | Description    |
|:-------:|:----------------------------|:---------------|
| iris-128b |  |  |
| iris-128s | mcu <br> pcb | Project files related to MCU programming. <br> Project and fabrication files related to PCB fabrcitaion and assembly.  |
| images    |        | image files used in README and description files. |

## EDA Tools used in the Development

| EDA Tool     | Version | Usage           |
| :----------: | :-----: | :-------------- |
| KiCad        | 8.0.5   | Design of PCBs. |
| STM32CubeIDE | 1.16.0  | Design of firmware for MCU. |


## Developers

* Deku Lab, University of Oregon, Eugene, OR
* OpenIC, Eagan, MN

## License

Copyright Manuel Monge, Emma Jacobs 2025.

This source describes Open Hardware and is licensed under CERN-OHL-P v2.

You may redistribute and modify this source and make products using it under the terms of the CERN-OHL-P v2 ([https:/cern.ch/cern-ohl](https:/cern.ch/cern-ohl)). This source is distributed WITHOUT ANY EXPRESS OR IMPLIED WARRANTY, INCLUDING OF MERCHANTABILITY, SATISFACTORY QUALITY AND FITNESS FOR A PARTICULAR PURPOSE. Please see the CERN-OHL-P v2 for applicable conditions.
