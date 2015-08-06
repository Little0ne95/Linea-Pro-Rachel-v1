lineapro-phonegap-plugin
========================

## Quick start <-- this method currently only works on xcode build and not phonegap build
1. Make sure you have Cordova installed and not Phonegap.  No idea why, but Cordova gave me less problems.<br>
2.From command line:<br>
2.1 cordova create HelloLineaproCitronium com.citronium.samples.hellolineapro<br>https://github.com/Little0ne95/Linea-Pro-Rachel-v1/edit/master/README.md#fullscreen
2.2 cd HelloLineaproCitronium/<br>
2.3 cordova plugins add https://github.com/Little0ne95/Linea-Pro-Rachel-v1.git<br>
2.4 Open up the file HelloLineproCitronium/www/js/index.js and place the following text in the very top on a new line (do not delete any script)<br>
<code>
function onDeviceConnected(data) { alert("onDeviceConnected: " + data);}
function onSuccessScanPaymentCard(data) { alert("onSuccessScanPaymentCard: " + data);}
function onBarcodeScanned(data) {alert("onBarcodeScanned: " + data.rawCodesArr);}
</code><br>
2.5 In the same file add LineaProCDV.initDT(onDeviceConnected, onSuccessScanPaymentCard, onBarcodeScanned); directly under app.receivedEvent('deviceready');<br>

2.6 cordova platforms add ios<br>
2.7 cordova build ios<br>
3. Now open up HelloLineproCitronium/platforms/ios/HelloCordova.xcodeproj in XCode<br>
4. Build the program to your Linea target<br>
5. The program should start and alert OnDeviceConnected: 1<br>

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
Using Adive and guild created by https://gist.github.com/johnvilsack
Tested on Cordova ver.3.3

(c) Citronium, 2014
http://citronium.com
