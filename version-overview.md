# Firmware

Here you can find the latest firmware. How to install the firmware and image can be found here:

{% content-ref url="firmware-update.md" %}
[firmware-update.md](firmware-update.md)
{% endcontent-ref %}

{% file src=".gitbook/assets/firmware_1.3.4.1.bin" %}

## Version 1.3.4.1 - 2022-12-27

### Added
* Telegram Support: With this version the device supports Telegram. By popular request this feature has been added. Sends temperature (in celsius), battery level (in %) and the transmit power RSSI.

* The configuration page is always accessible via Device Wifi. This means that every time you start the configuration mode with the hardware button, the TempTrack sets up its own network. This has many advantages:
  * reliable, even if the existing WLAN is not of good quality.
  * even if the router does not resolve the DNS address correctly, the TempTrack can be accessed
  * you don't need to know the IP of the target device, just enter 192.168.2.1 as described in the instructions.
  * some routers do not allow clients to communicate with each other, so you can still set up the device
  * a guest network can be used to send the data to the internet.
  * if the WiFi data is entered incorrectly, you can still access the device.
* Direct feedback WiFi setting. You can see directly if the wifi is connected or not. We are still working to find out the cause and output it.
* There are up to 6 languages for the user interface.
* Many more explanations have been added to each service.
* The initial password for the access point has been deleted. Just connect without a password and you're done.
* LED on when started in configuration mode\
  The two LEDs are switched on immediately when the unit is started in configuration mode.
* Wifi reset\
  If the reset button is pressed for longer than 3 seconds, the TempTrack is started with reset Wifi settings.
* Energy saving: Dynamic WLAN transmission power\
  The TempTrack first tries to send the message with a lower transmission power and then slowly increases it until the message has been sent.
* Detection: Server reachable (in the service menu)\
  If a test message has been sent, a red or green square is displayed behind the input window for the server address, depending on whether there is a connection or not. To test whether an Internet connection exists, "google.de" can be entered as the server This feature helps to find errors.
* Detection: Port open on server (in service menu)\
  If a test message has been sent, a red or green square is displayed behind the input window for the port, depending on whether the port is open or not. This feature helps to find errors.
* Parameter passing in the URL was introduced.\
  Instruction you find here[#url-replacement-feature](connect\_to\_http.md#url-replacement-feature "mention")
* Deepsleep
* Firmware upload via web interface
* Calibration wizard (sugar and reference method)
* BLE support
* Wifi (standalone and client mode)
* Ultra low power consumption algorithm
* Multible cloud INterfaces support
  * Http
  * Mqtt
  * Tcp
  * Telegram
  * ThingSpeak
  * Ubidots
* Support of multiple units for temperature
  * Kelvin
  * Fahrenheit
  * Celsius
* Support of signal LEDs to increase usability.
* Intuitive web interface
* Smoothing of measured values
* Support for a reset button
* Configurable name to support multiple devices in parallel.
