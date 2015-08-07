lineapro-phonegap-plugin
========================

## Quick start <-- this method is for xcode bbuild
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

## Quick start <-- this method is for use with phonegap build<br>
1.	Make sure you have Cordova installed and Phonegap<br>
2.	In the command line type: phonegap create HelloLineaproCitronium com.citronium.samples.hellolineapro<br>
3.	In the command line type:  cd HelloLineaproCitroniumTEST/<br>
4.	In the command line type:  phonegap  plugins add https://github.com/Little0ne95/Linea-Pro-Rachel-v1.git<br>
5.	Open up the file HelloLineproCitronium/www/js/index.js and place the following text in the very top on a new line (do not delete any script)<br>
<code>function onDeviceConnected(data) { alert("onDeviceConnected: " + data);} </code><br>
<code>function onSuccessScanPaymentCard(data) { alert("onSuccessScanPaymentCard: " + data);}</code><br>
<code>function onBarcodeScanned(data) {alert("onBarcodeScanned: " + data.rawCodesArr);}</code><br>
6.	In the same file add <br>
<code>LineaProCDV.initDT(onDeviceConnected, onSuccessScanPaymentCard, onBarcodeScanned);</code>  
directly under <br>
<code> app.receivedEvent('deviceready'); </code><br>
7.	In the config.xml file add<br>
<code><</code><code>gap:plugin name="cordova-plugin-whitelist" version="1" source="npm" /></code><br>
<code><</code><code>gap:plugin name="com.lineapro-plugin.rachel" version="0.1" source="pgb" /></code><br>
8.	In the index.html inside www folder add the following line<br>
<code><</code><code>script type="text/javascript" src="plugins/com.citronium.lineaprocdv.v2/www/LineaProCDV.js"></script></code><br>
9.	Back in the command line type: Cordova platforms add iOS<br>
10.	In the command line type: Cordova  build ios<br>
11.	In the command line type:  Phonegap build iOS<br>
12.	Now copy the config.xml file into platforms/iOS/www<br>
13.	To upload to phonegap, zip the www folder  which is inside platforms/iOS. This is the file you upload to phonegap build.<br>
14.	Enable debugging & Enable hydration ( This is once you have uploaded the file into phonegap build)<br>
15.	Click “ready to build”<br>
16.	Select your iOS Key ( you may need to  add this use this documentation if you don’t know how to http://docs.build.phonegap.com/en_US/3.3.0/signing_signing-ios.md.html . You will need an apple developer licence)<br>
17.	Once built scan the QR code with a QR reader on your device ( your ipod/ihone will have to be in developer mode, you can do this by connecting to xcode on a mac or follow ne of the many guids online)<br>
18.	Click on install when the notification shows<br>
19.	The app should now be one your device.<br>



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
