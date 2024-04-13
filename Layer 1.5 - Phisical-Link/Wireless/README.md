## Wireless Capture Files 

#### In This section, you will find captures files for WLAN 802.11 Standard.


Prerequisites for the capture filters: 

- [Wireshark](https://www.wireshark.org/download.html) installed on your machine.

The following filters strings was tested in Version 4.0.6 (v4.0.6-0-gac2f5a01286a) of Wireshark.

### Wireshark configuration To Coloring-Rules:

To use the coloring rules, you can use the filters described below to create a new rule in Wireshark. 

```
View -> Coloring Rules -> New Coloring Rule
```

![ExampleConfig](./.examples/config.png)

### Captures filters Sintax 802.11: 

---
#### Filter for all control frames:

```
wlan.fc.type == 0	
```
- Description: The filter will show all control frames in the capture file.

---
#### Filter For All Association Frames:

```
wlan.fc.type_subtype == 0 || wlan.fc.type_subtype == 1 || wlan.fc.type_subtype == 2 || wlan.fc.type_subtype == 3 
```
- Description: The filter will show all association frames in the capture file. 

---
#### Filter For All Probe Frames:

```
wlan.fc.type_subtype == 4 || wlan.fc.type_subtype == 5 	
```
- Description: The filter will show all probe frames in the capture file.

---
#### Filter For All Beacon Frames:

```
wlan.fc.type_subtype == 8	
```
- Description: The filter will show all beacon frames in the capture file.

---
#### Filter For All Disassociation Frames:

```
wlan.fc.type_subtype == 10 || wlan.fc.type_subtype == 11 || wlan.fc.type_subtype == 12	
```
- Description: The filter will show all disassociation frames in the capture file.

---
#### Filter For All Data Frames:

```
wlan.fc.type == 2 
```
- Description: The filter will show all data frames in the capture file.

---
#### Filter For 4-Way Handshake:

```
wlan.addr == <STA_MAC_ADDR> && (eapol || eap) || wlan.fc.type_subtype == 0x000b	
```
- Description: The filter will show all 4-way handshake frames in the capture file.

---
#### Filter For CTS/RTS Frames:

```
wlan.fc.type_subtype == 27 || wlan.fc.type_subtype == 28	
```
- Description: The filter will show all CTS/RTS frames in the capture file.

---
#### Filter For Acknowledgement Frames:

```
wlan.fc.type_subtype == 24 || wlan.fc.type_subtype == 25 || wlan.fc.type_subtype == 29	
```
- Description: The filter will show all Acknowledgement frames in the capture file.

---
#### Filter for Roaming (802.11v):

```
wlan.fixed.action_code == 23 || wlan.fixed.action_code == 24	
```
- Description: The filter will show all roaming frames in the capture file.

---
#### Filter for Roaming (802.11r):

```
(wlan.fc.type_subtype==0) && (wlan.rsn.akms.type == 3) || (wlan.fc.type_subtype==1) && (wlan.tag.number == 55) || (wlan.fc.type_subtype==2) && (wlan.tag.number == 55) || (wlan.fc.type_subtype==3) && (wlan.tag.number == 55)	
	
```
- Description: The filter will show all roaming 802.11r frames in the capture file.

---
#### Filter for Roaming (802.11k):

```
wlan.rm.action_code == 4 || wlan.rm.action_code == 5	
	
```
- Description: The filter will show all roaming 802.11k frames in the capture file.

---
#### Filter for Roaming (802.11v):

```
wlan.rm.action_code == 4 || wlan.rm.action_code == 5	
	
```
- Description: The filter will show all roaming 802.11v frames in the capture file.

---