lineapro-phonegap-plugin
========================

## Quick start <-- this method currently only works on xcode build and not phonegap build
1. Make sure you have Cordova installed and not Phonegap.  No idea why, but Cordova gave me less problems.<br>
2. From command line.<br>
3. cordova create HelloLineaproCitronium com.citronium.samples.hellolineapro<br>
4. cd HelloLineaproCitronium/<br>
5. cordova plugins add https://github.com/Little0ne95/Linea-Pro-Rachel-v1.git<br>
6. Open up the file HelloLineproCitronium/www/js/index.js and place the following text in the very top on a new line (do not delete any script)<br><code>function onDeviceConnected(data) { alert("onDeviceConnected: " + data);}</code> <br><code>function onSuccessScanPaymentCard(data) { alert("onSuccessScanPaymentCard: " + data);}</code><br><code>function onBarcodeScanned(data) {alert("onBarcodeScanned: " + data.rawCodesArr);}</code><br>
7. In the same file add <code>LineaProCDV.initDT(onDeviceConnected, onSuccessScanPaymentCard, onBarcodeScanned); </code> directly under <code> app.receivedEvent('deviceready');</code><br>
8. cordova platforms add ios<br>
9. cordova build ios<br>
10. Now open up HelloLineproCitronium/platforms/ios/HelloCordova.xcodeproj in XCode<br>
11. Build the program to your Linea target<br>
12. The program should start and alert OnDeviceConnected: 1<br>

**If you are using a device with a Lightning Connector YOU MUST DISCONNECTIT FROM THE COMPUTER**
7. The program will alert OnDeviceConnected: 2
8. Scan your barcode and watch the magic happen!

## Device support
Universal plugin for following devices:

* PPAD 1.0
* MPED-400
* BluePad-500
* BluePad-50
* Infinea TAB mini
* Infinea TAB 4
* Infinea TAB
* Linea Pro 5
* Linea Pro 4
* PP-60
* iSerial
* Linea-Pro

## Supported features:

* Automatically device connection
* Log all events
* Start/Stop Barcode methods

## Additional info

Using iOS SDK from http://www.datecs.bg/en/products/Universal-iOS-SDK/8/121
Using Advice and guild created by https://gist.github.com/johnvilsack
Using Plugin base craeted by https://github.com/ttatarinov/lineapro-phonegap-plugin

(c) Citronium, 2014
http://citronium.com
