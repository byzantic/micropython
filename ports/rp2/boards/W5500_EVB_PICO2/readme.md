# Wiznet W5500-EVB-Pico2

This board is a clone of the pico2, with an added Wiznet W5500 hardware ethernet chip and RJ45. A PoE daughterboard can also be added.

This board definition was created by copying the board files for W5500_EVB_PICO, changing names, and merging in features from the pico2. The board header file for "pico2" is used as the pico-sdk board, since the pinouts are the same (and everything seems to work OK ..).

## Network Example

To use network / socket based code, connect ethernet port to network with DHCP running:

```
>>> import network
>>> nic = network.WIZNET5K()
>>> nic.active(True)
>>> nic.ifconfig()
('0.0.0.0', '0.0.0.0', '0.0.0.0', '0.0.0.0')
>>> nic.ifconfig("dhcp")
('192.168.0.10', '255.255.255.0', '192.168.0.1', '192.168.0.1')
>>> nic.isconnected()
True
```
At this point standard network communications libraries should work.
