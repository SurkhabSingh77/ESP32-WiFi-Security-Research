# ESP32 Wireless Security & Embedded Hardware Lab

A personal learning lab documenting hands-on exploration of ESP32-based devices, third-party Bruce firmware, 2.4 GHz wireless concepts, and security improvements to a network I own.

> **Project status:** Documentation-first learning project. This repository does not currently contain independently developed Bruce firmware, custom ESP32 firmware, packet-capture tools, or a validated detection engine.

## Overview

I used several compact ESP32 devices to explore embedded hardware and wireless-security concepts. I installed and explored the open-source [Bruce firmware](https://github.com/pr3y/Bruce) using its web flasher, then experimented with the functionality available on the devices.

My goal was to understand how embedded devices interact with wireless environments and apply what I learned to improve the security of my own home network.

## Hardware used

| Hardware | My use |
| --- | --- |
| LilyGO T-Watch S3 | ESP32-S3 smartwatch running Bruce firmware; explored its available features |
| M5StickC Plus2 | Portable ESP32 device running Bruce; wireless-security learning and hardware experimentation |
| 2.8-inch CYD touchscreen board | Bruce firmware on a touch-operated ESP32 display with a microSD slot |
| NRF24 radio module | Connected and experimented with alongside the M5StickC Plus2 |

The CYD board is identified by its visible characteristics (2.8-inch touchscreen and microSD slot). Its exact board revision and controller have not yet been verified.

## Firmware attribution

- **Bruce firmware:** [pr3y/Bruce](https://github.com/pr3y/Bruce), an upstream open-source project.
- I installed it on my hardware using the project's web flasher and explored its available functionality.
- I do not claim authorship of Bruce or its built-in features.
- Any future code added here will be clearly identified as my own work or as third-party material with original attribution and license information.

## Areas explored

- Exploring Bruce firmware features on the devices listed above.
- Learning about Wi-Fi operation and the 2.4 GHz band.
- Experimenting with an NRF24 module as a separate 2.4 GHz radio platform.
- Understanding the differences between 2.4 GHz and 5 GHz Wi-Fi bands.
- Reviewing wireless-security settings and improving the configuration of my own home network, including enabling WPA3 where supported.
- Exploring touchscreen interaction and microSD-based operation on the CYD board.

These are areas I explored; they are not claims that I implemented the underlying firmware features or built custom attack or detection tools.

## Learning notes

Topics to document with reproducible observations:

- ESP32 and ESP32-S3 hardware differences
- Firmware flashing and recovery workflow
- Wi-Fi bands, channels, channel width, and interference
- WPA2/WPA3 security modes and router configuration
- Differences between Wi-Fi and NRF24 radio protocols
- Touchscreen and microSD usage on the CYD board
- Safe handling of wireless observations and captured data

## Safety and authorization

Active security testing documented here is limited to devices and networks I own or have explicit permission to assess. I do not publish other people's network identifiers, credentials, packet captures, or personal data.

Wireless experimentation can disrupt nearby equipment. I aim to use controlled, low-impact tests and follow applicable laws and vendor guidance. This repository is for education and defensive learning, not unauthorized access or interference.

## Documentation

- [Hardware inventory](docs/hardware-inventory.md) — the devices and radio module used in this lab, with unverified details clearly marked.
- [Experiment log template](docs/experiment-log-template.md) — a reusable format for recording authorized, privacy-conscious experiments.

## Current repository contents

At present, this is a documentation-first record of the lab. It does not yet provide reproducible source-code projects or automated tests. Original scripts, diagrams, photos, and experiment logs will be added only when they exist and can be documented with setup instructions.

## Planned documentation

- [ ] Verify exact board revisions and hardware specifications
- [ ] Add my own photos of each device and its setup
- [ ] Record firmware versions and flashing dates where available
- [ ] Add a safe home-router hardening checklist
- [ ] Document NRF24 wiring, module variant, and observed behavior
- [ ] Add experiment notes with setup, observations, and limitations
- [ ] Add diagrams showing the devices and their roles

## References

- [Bruce firmware](https://github.com/pr3y/Bruce)
- [Espressif documentation](https://docs.espressif.com/)
- [Wireshark](https://www.wireshark.org/)

---
A personal hardware-learning project focused on accurate documentation of what I actually flashed, configured, experimented with, and learned.
