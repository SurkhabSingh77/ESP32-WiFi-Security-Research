# Home Wi-Fi Security Hardening Checklist

A defensive checklist for reviewing a home wireless router. This is a general reference, not a record of settings verified on any particular router. Menu names and available options vary by manufacturer and model.

## Before changing settings

- [ ] Confirm that I own the router or have permission from its administrator.
- [ ] Find the router manufacturer's documentation for the exact model and firmware.
- [ ] Save or record the current configuration in a secure place.
- [ ] Make changes from a trusted device connected to the router.
- [ ] Avoid publishing the SSID, public IP address, MAC addresses, passwords, recovery codes, or screenshots containing private details.

## Authentication and passwords

- [ ] Use WPA3-Personal when all required devices support it.
- [ ] If WPA3 is not practical for older devices, choose the strongest compatible mode recommended by the router manufacturer; avoid WEP and WPA/TKIP.
- [ ] Use a long, unique Wi-Fi passphrase that is not reused elsewhere.
- [ ] Change the router administrator password from its default.
- [ ] Disable WPS if it is not needed and the router provides that option.

## Router administration

- [ ] Install firmware updates from the router manufacturer.
- [ ] Disable remote administration from the internet unless there is a documented need.
- [ ] Use HTTPS for local administration when supported.
- [ ] Review connected devices and remove unknown entries only after identifying them.
- [ ] Disable services and features that are not needed, following the manufacturer's guidance.

## Network separation

- [ ] Use a guest network for visitors when available.
- [ ] Consider a separate network for IoT devices that do not need access to personal computers or storage.
- [ ] Check whether guest/IoT isolation is enabled and understand what devices can communicate.
- [ ] Keep trusted computers and phones on the primary network.

## Radio and Wi-Fi configuration

- [ ] Understand that 2.4 GHz and 5 GHz are separate Wi-Fi bands with different range and compatibility characteristics.
- [ ] Choose channel and channel-width settings based on the router's guidance and the local environment; do not assume wider is always better.
- [ ] Use automatic channel selection unless there is a measured reason to choose a channel manually.
- [ ] Do not confuse Wi-Fi channel selection or band steering with frequency hopping.
- [ ] Remember that NRF24 devices use a different radio protocol from Wi-Fi, even though both operate in the 2.4 GHz spectrum.

## Review and recovery

- [ ] Reconnect a small set of known devices after making changes.
- [ ] Confirm that required devices still work and that guest/IoT separation behaves as expected.
- [ ] Keep router firmware and configuration review dates in a private record.
- [ ] Store configuration backups securely; do not commit them to a public repository.
- [ ] If a change breaks connectivity, use the manufacturer's recovery procedure.

## Record of a real review

Complete this section only after personally checking the router. Do not add passwords, network names, device identifiers, or other sensitive values.

- **Date reviewed:**
- **Router manufacturer/model (optional):**
- **Firmware version (optional):**
- **Security mode observed:**
- **Updates checked/installed:**
- **Administrative settings reviewed:**
- **Network separation reviewed:**
- **Changes actually made:**
- **Issues or limitations:**
- **Follow-up date:**

## Scope and safety

This checklist is for defensive configuration of a network I own or am authorized to administer. It does not instruct readers to access, disrupt, or intercept other people's networks. Follow local law and the router manufacturer's documentation.
