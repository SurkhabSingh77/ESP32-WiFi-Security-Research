# ESP32 WiFi Security Research — README

Version: 1.0.0  
Last updated: 2026-01-21

## Overview
This repository contains code, experiments, and notes for an ESP32-based WiFi security research project. The goal is to learn how the 802.11 stack and WiFi security mechanisms interact with embedded devices, to build safe testbeds for protocol analysis, and to prototype defensive and detection approaches on low-cost hardware.

This project is explicitly research-oriented and intended for:
- Security students and researchers learning about WiFi and embedded security.
- Developers building defensive tools and detection experiments on ESP32-class hardware.
- Educators wishing to demonstrate WiFi concepts in a controlled lab.

Scope:
- Firmware sketches and ESP-IDF/Arduino examples for packet capture, beacon/probe generation (for lab-only testing), and telemetry.
- Guidance for setting up an isolated test network and capturing/analyzing 802.11 traffic.
- Notes on mitigations, detection strategies, and ethical handling of data.

## Important legal & ethical notice (read first)
All experiments and testing MUST be performed only on devices/networks you own or for which you have explicit written permission. Interacting with, intercepting, or attacking networks or devices that you do not own or have authorization to test is illegal in many jurisdictions and may cause serious harm.

By using this repository you agree to:
- Only test on equipment and networks you control, or where you have explicit, documented consent.
- Follow responsible disclosure practices if you identify vulnerabilities in third-party products.
- Comply with applicable laws and institutional policies.

If you are unsure whether an action is allowed, do not perform it — seek written permission from the owner or legal advice.

## Tools & Components Used
Hardware
- ESP32 development board (e.g., ESP32-WROOM or similar DevKit)
- Reliable USB cable and a host PC
- Optional: external WiFi adapter that supports monitor mode (for passive capture) — recommended for more advanced sniffing/monitoring

Software / Libraries
- ESP-IDF (official Espressif development framework) — recommended for lowest-level access
- Arduino-ESP32 (alternative for Arduino users)
- esptool.py (flashing)
- Python 3.8+ and common packages (see requirements.txt)
- Wireshark or tcpdump (packet capture & analysis)
- hostapd / dnsmasq (for creating isolated test APs)
- Optional: scapy (for crafted-frame experiments in lab)

Recommended versions / links:
- ESP-IDF: https://docs.espressif.com/projects/esp-idf/
- Wireshark: https://www.wireshark.org/
- scapy: https://scapy.net/

## Repository layout (example)
- /firmware/ — ESP-IDF projects and Arduino sketches
- /tools/ — host-side helpers and capture scripts (Python)
- /docs/ — research notes, diagrams, references
- /examples/ — minimal example builds and safe test scenarios
- requirements.txt — Python dependencies for host tools and scripts

## Quickstart — safe lab setup
1. Hardware and network
   - Use an isolated test network or VLAN with no internet access for experiments.
   - Power your ESP32 and connect it via USB to your development machine.
   - If packet capture beyond what the ESP32 can provide is needed, use a separate WiFi adapter in monitor mode on the host.

2. Prerequisites (host)
   - Install Python 3.8+ and pip.
   - Install ESP-IDF (follow official installer) or set up Arduino-IDE with the ESP32 board package.
   - Install Wireshark for packet analysis.

3. Prepare repository (example)
   - git clone <this-repo-url>
   - cd <repo>
   - python -m venv .venv
   - source .venv/bin/activate  (Windows: .venv\Scripts\activate)
   - pip install -r requirements.txt

4. Build & flash (ESP-IDF example)
   - cd firmware/espidf-project
   - idf.py set-target esp32
   - idf.py build
   - idf.py -p /dev/ttyUSB0 flash monitor
   - The device will print logs to the monitor and start the configured safe test behavior.

5. Build & upload (Arduino example)
   - Open the sketch in Arduino IDE or use PlatformIO.
   - Select the correct board and serial port, then upload.
   - Open the serial monitor to view output.

6. Capture & analyze (host)
   - If using a monitor-mode adapter:
     - Put the adapter in monitor mode (platform-specific; e.g., via `airmon-ng` on Linux) — only on your test network or hardware you own.
     - Start Wireshark and capture on the monitor interface.
   - For capture from the ESP32, use the provided firmware to forward logs or summarized packet metadata to the host over serial or a dedicated management AP.

Notes:
- Replace `/dev/ttyUSB0` with the correct serial device for your OS.
- The repository includes safe example scenarios (e.g., beacon flood simulator) that are intentionally rate-limited and designed for closed lab environments only.

## Safe experiment examples (high-level)
- Passive packet logging: firmware collects metadata (timestamps, RSSI, frame types) and forwards anonymized logs to a host for analysis.
- Beacon/probe generation: controlled generation of custom beacons on a lab AP to test detection signatures — strictly rate-limited and isolated.
- Detection prototype: ESP32-based anomaly detector that flags unusual management-frame patterns and reports them for offline analysis.

Do NOT use these examples against third-party devices or networks.

## Learning outcomes
By working through this project you will:
- Understand ESP32 development workflow with ESP-IDF and Arduino.
- Learn the fundamentals of 802.11 management, control, and data frames.
- Be able to capture, filter, and analyze WiFi packets using Wireshark and related tools.
- Gain experience building safe, reproducible wireless testbeds and experiments.
- Learn ethical research practices, responsible disclosure, and mitigation strategies.
- Prototype lightweight detection and telemetry on resource-constrained embedded hardware.

## Responsible disclosure & ethics
If you discover a vulnerability in a vendor product while using this repository:
- Stop testing that target immediately.
- Collect minimal, non-sensitive proof-of-concept material.
- Check the vendor's security policy or vulnerability disclosure program (VDP) for reporting instructions.
- If none exists, contact the vendor privately and allow reasonable time for remediation before public disclosure.
- When in doubt, consult your institution's legal or compliance team.

Keep captured data secure and delete or anonymize any personally identifiable or sensitive content as soon as analysis is complete.

## Contributing
Contributions are welcome if they align with the ethical requirements above. Please:
- Open an issue describing proposed addition or improvement.
- Submit pull requests with tests/examples that are safe to run in a lab environment.
- Document any potentially sensitive behavior and add clear warnings in code and documentation.

## License
This repository is provided for educational and research purposes. You may include your preferred open-source license here (e.g., MIT, Apache-2.0). Ensure license terms are compatible with any included third-party code.

## Contact
Open an issue on this repository or reach me via my GitHub profile: https://github.com/SurkhabSingh77

## References
- Espressif ESP-IDF documentation — https://docs.espressif.com/
- Wireshark User Guide — https://www.wireshark.org/docs/
- scapy — https://scapy.net/

Acknowledgment: Always obtain authorization before testing. This project is intended to improve defensive capabilities and research understanding of WiFi security, not to facilitate unauthorized attacks.
