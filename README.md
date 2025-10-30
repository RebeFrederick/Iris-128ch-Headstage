# Iris-128

Open-source 128-channel headstages for neural stimulation and recording.

*The publication of this work can be found at DOI 10.1088/1741-2552/ae1876. The raw data files corresponding to the publication can be found at https://doi.org/10.17605/OSF.IO/XS2PU.*

![Iris-128](./images/iris-128-system.jpg)

| Type | Description |
| :--: | :---------- |
| [Iris-128B](iris-128b/README.md)  | Fully bidirectional headstage with recording or stimulation across all 128 electrode channels. |
| [Iris-128S](iris-128s/README.md) | Selective stimulation headstage with recording from 128 channels and stimulation on 16 simultaneous channels out of 32 available stimulation channels. |
| [Thin-film electrode](thin-film/README.md) | 128 channel surface array used as a test platform for the headstages. |


## File Structure

| Folder  | Description    |
| :-----: | :------------- |
| iris-128b | Project, design, and fabrication files related to Iris-128B Neural Interface System. |
| iris-128s | Project, design, and fabrication files related to Iris-128S Neural Interface System. |
| thin-film    | Design files related to the microelectrode test platform. |
| images    | image files used in README and description files. |

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
