# Hardware Milkway Netgear Switch ProSafe M4100-26G
Managed Switch config.

***! Always save configuration under Maintenance -> Save Configuraiton !***
## Access
- Set ip to 169.254.100.200/16 (255.255.0.0) Gateway 0.0.0.0
- https://169.254.100.100
  - admin/<PW>
  - guest/<empty> -> readonly

## Reset vs. Factory Reset
Reset only resets power. No factory reset.

## Model
- Netgear ProSafe M4100-26G

## Ports
- 1-20 -> normal switching
- 21-22 -> admin (not working)
- 23-26 -> LAG (Link Aggregation Group)

### How to do factory reset
- Use MiniUSB cable (port is at the back)
  - check ```dmesg for interface```
- for arch linux
  - ```pacman -S minicom```
  - use provided config or do ```minicom -s```
    - Baud rate: 115200 (some older models of Fully Managed Switch use 9600. The required baud rate will be printed beside the console port on the switch)
    - Data bits: 8
    - Parity: None
    - Stop bit: 1
    - Flow control: None
  - reset switch, boot sequence will pop up in minicom
  - wait for ***Checking for application***
    - press q (p worked also?!)
  - select ***11 - Restore configuration to factory defaults***