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

## ios 9 Update - phonegap problems
There are a few things too fix if you are using ios 9 these include the screen not responding to touch and the black borders.
Fixing Screen not responding to touch:-
 1. Go to your app on Phone Gap Build
 2. Select Settings
 3. Unclick Enable Hydration
 
Fixing the black borders:- </br>
1. Create 10 Splash screens as following:-</br> iosDefault~iphone.png width= 320px height= 480px </br> Default@2x~iphone.png width= 640px height= 960px </br> Default-568h@2x.png width= 640px height= 1136px </br> Default-667h@2x.png width= 750px height= 1334px</br> Default-Portrait-736h@3x.png width= 1242px height= 2208px</br> Default-Landscape-736h@3x.png width= 2208px height= 1242px</br> Default-Portrait.png width= 768px height= 1024px</br> Default-Landscape.png width= 1024px height= 768px</br> Default-Portrait@2x.png width= 1536px height= 2048px</br> Default-Landsc10 ape@2x.png width= 2048px height= 1536px</br>
2. Add these images to the file res/screen/ios/</br>
3. Add this code to your config.xml</br>
<code><!-- iPhone and iPod touch --></code></br>
<code><</code><code>gap:splash src="res/screen/iosDefault~iphone.png" gap:platform="ios" width="320" height="480" /></code></br>
<code><</code><code>gap:splash src="res/screen/ios/Default@2x~iphone.png" gap:platform="ios" width="640" height="960" /></code></br>

<code><!-- iPhone 5 / iPod Touch (5th Generation) --></code></br>
<code><</code><code>gap:splash src="res/screen/ios/Default-568h@2x.png" gap:platform="ios" width="640" height="1136" /></code></br>

<code><!-- iPhone 6 --></code></br>
<code><</code><code>gap:splash src="res/screen/ios/Default-667h@2x.png" gap:platform="ios" width="750" height="1334" /></code></br>
<code><</code><code>gap:splash src="res/screen/ios/Default-Portrait-736h@3x.png" gap:platform="ios" width="1242" height="2208" /></code></br>
<code><</code><code>gap:splash src="res/screen/ios/Default-Landscape-736h@3x.png" gap:platform="ios" width="2208" height="1242" /></code></br>

<code><!-- iPad --></code></br>
<code><</code><code>gap:splash src="res/screen/ios/Default-Portrait.png" gap:platform="ios" width="768" height="1024" /></code></br>
<code><</code><code>gap:splash src="res/screen/ios/Default-Landscape.png" gap:platform="ios" width="1024" height="768" /></code></br>

<code><!-- Retina iPad --></code></br>
<code><</code><code>gap:splash src="res/screen/ios/Default-Portrait@2x.png" gap:platform="ios" width="1536" height="2048" /></code></br>
<code><</code><code>gap:splash src="res/screen/ios/Default-Landscape@2x.png" gap:platform="ios" width="2048" height="1536" /></code></br>


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
