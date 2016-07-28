Digi XBee ANSI C Library: Sample Programs
=========================================
Each port includes a subset of the following sample programs.  Find
additional documentation in comments at the top of the source code.
Many of samples make use of shared source files in `samples/common`,
with platform-specific support code in each `samples/<target>` directory.

## General Samples

- **apply profile**:
  Connect to an XBee module and execute a sequence of AT Commands stored
  in a Legacy X-CTU Profile (`.PRO` file).

- **atinter**:
  Short for "AT Interactive", this simple sample demonstrates the 
  `xbee_atcmd` API for reading and setting AT parameters on the XBee
  radio.  This is a good starting sample to verify correct communication
  with an XBee module in API mode.

- **eblinfo**:
  Displays information stored in the headers of XBee firmware images
  (`.EBL` files) used for XBee S2, S2B and S2C models.

- **gpm**:
  Sample program demonstrating the General Purpose Memory API, used to access
  flash storage on some XBee modules (868LP, 900HP, Wi-Fi).  This space is
  available for host use, and is also used to stage firmware images before
  installation.

- **install ebl**:
  Sends firmware updates (.ebl and .gbl files) to XBee modules with 
  Ember processors (e.g., ZigBee and Smart Energy firmware to XBee S2, 
  S2B and S2C) and EFR32 processors (e.g., XBee3 Cellular, 802.15.4, 
  DigiMesh, and Zigbee).

- **network scan**:
  Perform an `ATAS` "active scan" and report the results.  Intended for
  Zigbee and Wi-Fi networks, but could work for others after updating
  `src/xbee/xbee_scan.c` for new scan types.

- **transparent client**:
  Demonstrate the "transparent serial" cluster used by XBee modules in
  "AT mode", along with node discovery using the ATND command.  Send
  strings between XBee modules on a network.

- **xbee term**:
  Simple, stand-alone terminal emulator to interact with a module's
  bootloader or its regular firmware in command mode 

## Platform-Specific Samples

### Rabbit (Dynamic C) Samples

See `samples/rabbit/ReadMe.txt` for a description of that platform's
collection of sample programs.

### Windows (Win32) Samples

- **comports**:
  This sample doesn't use this library, but it's useful for seeing a
  list of what COM ports are available.

## Product-Specific Samples

### Programmable XBee Samples

- **pxbee ota update**:
  Test tool for sending OTA (over-the-air) firmware updates to
  Programmable XBee modules.

- **pxbee update**:
  Install firmware update to a Programmable XBee module over a wired
  serial connection.

### Cellular Samples

- **ipv4_client**:
  Demonstrates communication via TCP over IPv4 frames.

- **sms_client**:
  Demonstrates sending and receiving SMS messages.

### Zigbee Samples

These samples target XBee modules joined to Zigbee-compliant networks.
 
- **commissioning client** and **commissioning server**:
  Client and server samples demonstrating the use of the ZCL Commissioning
  Cluster to configure network settings on a Zigbee device.

- **zigbee walker**:
  "Walks" a Zigbee device using discovery packets to list all ZCL
  attributes.  Starts with ZDO requests to enumerate a device's endpoints
  and clusters, and then uses ZCL requests to list the attribute ID, type
  and value for each cluster.

- **zcltime**:
  This utility converts a ZCL UTCTime value (32-bit number of seconds
  since 1/1/2000) to a `struct tm` and human-readable date string.