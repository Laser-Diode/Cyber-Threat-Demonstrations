## Half-Handshake Attack
### _Disclaimer_
Do not use the contained information for hacking devices which you do not have permission to access as that is a criminal offence and a violation of individuals privacy.

### Description
#### How the protocal works?
Whenever an individual connects their smart phone or other gadgets wirewlessly into a network they input the network name (SSID) and password (PSK). For convienence, that device will then keep an eye out for networks with the same name and attempt to use the stored password to gain access by connecting again. Normally when a device attempts to join a WiFi network there is a four way handshake that allows for authentication and proper connection for valid users.

#### Description of the Threat
A half-handshake attack takes advantage of this protocal by advertising itself as a cloned WiFi network SSID. This is sent out as the first part (or packet) of the handshake. In response, a device that has previously connected to a network with that SSID and is configured to automatically join, will respond back with a second packet that includes a cryptographically hidden password.

The following stages of the handshake cannot be completed as the password for the clone of the network does not possess the genuine password at this point; resulting in only half of the handshake being completed. This cryptographically hidden password can be decoded using software, taking more time depending on the complexity of the password that was set. This can be done with programs such as HashCat or Aircrack-ng.

In this demonstration I used the common password list RockYou.txt to choose a complex password that was part of the list and set it as the password to a demonstration network. Then using a WiFi Pineapple and HashCat, I captured a handshake from the air and retrieved the password in under an hour using a very low-power virtual machine. A dedicated high-power machine would be able to make much quicker work decoding a password that was a basic dictionary word or had low entropy.

### Citations
This guide is based on the work done in this [HakByte video by Hak5](https://www.youtube.com/watch?v=5guDKTc6Hak).
