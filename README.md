# TSL UHF RFID reader plugin for Cordova

This plugin provides API abstraction for TSL UHF RFID reader (Tested with 1128 Bluetooth UHF RFID Reader device)

Based on work by Don Coleman https://github.com/don/tslRfid and Matej Kriz https://github.com/matejkriz/tslRfid


## Supported Platforms

* Android
* iOS

# Installing

Install with Cordova cli

    $ cordova plugin add https://github.com/don/tslRfid


	# API

## Methods

- [tslRfid.connect](#connect)
- [tslRfid.disconnect](#disconnect)
- [tslRfid.showBluetoothSettings](#showBluetoothSettings)
- [tslRfid.isEnabled](#isEnabled)
- [tslRfid.isConnected](#isConnected)
- [tslRfid.getPairedDevices](#getPairedDevices)
- [tslRfid.readTag](#readTag)
- [tslRfid.readTagUserMemory](#readTagUserMemory)
- [tslRfid.writeTagEpcHex](#writeTagEpcHex)
- [tslRfid.writeTagMemory](#writeTagMemory)
- [tslRfid.writeTagMemoryFixed32Bytes](#writeTagMemoryFixed32Bytes)
- [tslRfid.writeTagMemoryHex](#writeTagMemoryHex)
- [tslRfid.writeToTag](#writeToTag)
- [tslRfid.sendCommand](#sendCommand)
- [tslRfid.getOutputPower](#getOutputPower)
- [tslRfid.setOutputPower](#setOutputPower)
- [tslRfid.setSwitchSinglePressCommand](#setSwitchSinglePressCommand)
- [tslRfid.setSwitchSinglePressCommandInventoryScan](#setSwitchSinglePressCommandInventoryScan)
- [tslRfid.setSwitchDoublePressCommand](#setSwitchDoublePressCommand)
- [tslRfid.setSwitchDoublePressCommandBarcodeScan](#setSwitchDoublePressCommandBarcodeScan)


## Events

- [tslRfid.onRfidScanned](#onRfidScanned)
- [tslRfid.onBarcodeScanned](#onBarcodeScanned)


## Helpers

- [tslRfid.memBank](#memBank)
- [tslRfid.hexToString](#hexToString)
- [tslRfid.memBank](#memBank)





## connect

Connect to the device

    tslRfid.connect(macAddress_or_uuid, connectSuccess, connectFailure);

### Description

Function `connect` connects and subscribes to the TSL RFID device

### Hint

The 'id' property of the device from the 'getPairedDevices' function call could be used by both iOS as well as Android as the parameter

#### Android
For Android, `connect` takes a MAC address of the remote device.

#### iOS
For iOS, `connect` takes the UUID of the remote device.  Optionally, you can pass an **empty string** and the plugin will connect to the first BLE peripheral.

### Parameters

- __macAddress_or_uuid__: Identifier of the remote device.
- __connectSuccess__: Success callback function that is invoked when the connection is successful.
- __connectFailure__: Error callback function, invoked when error occurs or the connection disconnects.


## disconnect

Disconnect

    tslRfid.disconnect(win, fail);

### Description

Function `disconnect` stops the event listener and disconnects from the device

### Parameters

- __win__: Success callback function that is invoked when the connection is successful. [optional]
- __fail__: Error callback function, invoked when error occurs. [optional]


