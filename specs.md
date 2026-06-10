---
title: Specifications
layout: default
---
{: .note }
**it is currently unknown how/if these specifications change between units**

| Spec | Detail |
|-|-|
| Model | HDR-300T/AU/500GB |
| Hard Disk | Seagate Video 3.5 HDD 500GB Serial ATA |
| System on Chip | Broadcom BCM7241 (Specific SKU: Broadcom BCM7241ZBKFEBA01G TA1510 P20 4622-97 N3A) |
| RAM | 2x SAMSUNG K4BG1646D-BCK0 (1Gbit per chip, likely configured as 256M according to ChatGPT) |
| Flash | Spansion ML04G200BHIOO (Likely 4Gbit) |
| OS | Linux of some kind |

## User-Agent
Extracted from a PCAP I made using a RasPi

`Opera/9.80 (Linux mips; Opera TV Store/5954; HbbTV/1.2.1 (+PVR; Humax; hdr3000t; AUTFAD 1.00.53; 1.0.0; wired; UX-PRISM--OP-NONE); ce-html/1.0) Presto/2.12.407 Version/12.50`


## SoC Specifications
* **CPU:** 1x MIPS, likely 32-bits, 1.30Ghz, 3000 DMIPS
* **RAM:** DDR3
* **GPU:** OpenGL 2.0
* **Interfaces:** Ethernet, USB, SATA, SDIO
* **Node:** 40nm

Source: [wi-cat](https://wikidevi.wi-cat.ru/Broadcom/SoC#:~:text=BCM7241)
