# Switch Configuration and VLAN Setup Demo

This project demonstrates the basic configuration of a network switch using a console terminal, including creating VLANs, assigning ports, and configuring IP settings for communication between devices.

## 📹 Video Demo

[Switch Configuration Lab Video](https://www.youtube.com/watch?v=8O7WKteMwBQ)

## 🛠️ Tools Used

- Cisco Catalyst 1000 Switch
- PuTTY (Serial Communication)
- Console Cable
- Two end devices (e.g. laptops or PCs)

## 🧪 Process Overview

1. **Initial Cable Setup**
   - Connected devices to switch using appropriate ports and cables.

2. **Accessing the Switch via PuTTY**
   - Opened PuTTY and set connection type to **Serial**, COM3.
   - Launched the terminal interface.

3. **Initial Switch Configuration**
   - Entered privileged mode with `enable` and `config terminal`.
   - Changed hostname: `hostname MK_Switch`.
   - Set enable secret: `enable secret 1234mk`.

4. **VLAN Creation**
   - Created VLAN 4 with name `MK_VLAN_1`:
     ```bash
     vlan 4
     name MK_VLAN_1
     ```
   - Verified using `do show vlan`.

5. **Port Assignment**
   - Assigned ports GigabitEthernet1/0/13 and 1/0/14 to VLAN 4:
     ```bash
     interface gigabitEthernet1/0/13
     switchport access vlan 4
     exit

     interface gigabitEthernet1/0/14
     switchport access vlan 4
     ```
   - Confirmed using `do show vlan`.

6. **IP Address and Gateway Configuration**
   - Assigned IP to VLAN 4 interface:
     ```bash
     interface vlan 4
     ip address 198.18.10.5 255.255.255.0
     exit
     ip default-gateway 198.18.10.1
     ```

7. **Device IP Setup**
   - Manually configured static IPs on both connected devices.
   - Verified connectivity using `ping`.

8. **Verification**
   - Used `show ip interface brief` and `ipconfig` to confirm IP assignments and connectivity.

## ✅ Outcome

- Successfully created and configured VLAN 4.
- Assigned ports to VLAN and ensured communication between devices.
- Configured IPs and verified bi-directional pings with success.
