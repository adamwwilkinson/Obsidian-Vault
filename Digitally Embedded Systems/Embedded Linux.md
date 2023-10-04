Created: 01/10/2023 at 13:40
### Pi3 Board and Connections
![[Embedded Linux-1696138932822.jpeg]]
![[Embedded Linux-1696138951480.jpeg]]

All memory is in a MicroSD card.

### Raspberry Basics
1. Install OS on SD card, plug in, and boot.
2. Conect Raspberry
3. Ethernet LAN and WLAN connection
![[Embedded Linux-1696139204309.jpeg]]
4. SSH connection (after connecting to raspberry pi hotspot)
```bash
slogin -l pi 10.1.1.1
// password is rasp
```
5. File Transfer
From Mac to Raspberry Pi
```bash
scp myfile pi@rasp1:myfile
```
From Raspberry Pi to Mac
```bash
scp pi@rasp1:myfile newfile
```

### IP Address
Each device on a network has a unique IP address. The IP address is a 32-bit number, usually written as four decimal numbers separated by periods. Each decimal number represents one byte of the 32-bit number. The IP address is divided into two parts: the network address and the host address. The network address identifies the network to which the device is connected. The host address identifies the specific device on the network. The network address is determined by the network administrator. The host address is assigned by the network administrator or by a DHCP server.

When directly linking two devices, both devices have to be set to addresses in the same prefix range.

### Compiling
Compiling on Robot
```bash
gccarm -o hello hello.c
```

Compiling for sim
```bash
gccsim -o hello hello.c
```
