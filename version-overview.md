# Firmware

Here you can find the latest firmware. How to install the firmware and image can be found here:

{% content-ref url="firmware-update.md" %}
[firmware-update.md](firmware-update.md)
{% endcontent-ref %}

{% file src=".gitbook/assets/firmware_1.3.4.1.bin" %}

## Version 1.3.4.1 - 2022-12-27

### fixed

* There was a bug in the calculation temperature compensation.

## Version 1.3.4 - 2022-12-08

### Added

* Upside down detection: The Hydrom stops sending readings when it is upside down. This results in longer battery life and clearer use of readings.
* Temperature compensation: The Hydrom, like all free-floating hydrometers, is subject to the laws of physics. The measurement result is directly dependent on the temperature. This dependency has now been reduced with the temperature compensation.
* Telegram Support: With this version the device supports Telegram. By popular request this feature has been added. Sends Plato, temperature (in celsius), battery level (in %) and the transmit power RSSI.
* For Monitor.beer support, "tilt" was added to the json data. Monitor.beer should now be supported.

### Fixed

* Fixed a bug in calculating the time the device should sleep.
* Fixed URL placeholder values for Specific Density and Battery Percent.

### Changed

* for Ubidots Plato is now sent in the "tilt" variable and the raw value of the device's angle is sent in the "angle\_RAW" variable

## Version 1.3.1 - 2022-8-7

### Added

* The configuration page is now always accessible via Device Wifi. This means that every time you start the configuration mode with the hardware button, the Hydrom sets up its own network. This has many advantages:
  * reliable, even if the existing WLAN is not of good quality.
  * even if the router does not resolve the DNS address correctly, the Hydrom can be accessed
  * you don't need to know the IP of the target device, just enter 192.168.2.1 as described in the instructions.
  * some routers do not allow clients to communicate with each other, so you can still set up the device
  * a guest network can be used to send the data to the internet.
  * if the WiFi data is entered incorrectly, you can still access the device.
* Direct feedback WiFi setting. You can see directly if the wifi is connected or not. We are still working to find out the cause and output it.
* There are up to 6 languages for the user interface.
* Many more explanations have been added to each service.
* The initial password for the access point has been deleted. Just connect without a password and you're done.

## Version 1.2.16 - 2022-4-05

### Fixed

* Plainwater calibration was repaired.

## Version 1.2.15 - 2022-4-03

### Fixed

* Stabilisation of the position sensor measurements.
* Ubidots Interface\
  The last update contained an error, which has been eliminated with this update

## Version 1.2.14 - 2022-3-30

### Added

* LED on when started in configuration mode\
  The two LEDs are switched on immediately when the unit is started in configuration mode.
* Wifi reset\
  If the reset button is pressed for longer than 3 seconds, the Hydrom is started with reset Wifi settings.

### Fixed

* Brewfather Server\&Port is now stored persistently.\
  The Brewfather Server address & port has been made changeable.

\\

### Changed

* Default Brewblox port changed from 91 to 1883

## Version 1.2.13 - 2022-3-11

​​

### Added

* Energy saving: Dynamic WLAN transmission power\
  The Hydrom first tries to send the message with a lower transmission power and then slowly increases it until the message has been sent.
* Detection: Server reachable (in the service menu)\
  If a test message has been sent, a red or green square is displayed behind the input window for the server address, depending on whether there is a connection or not. To test whether an Internet connection exists, "google.de" can be entered as the server This feature helps to find errors.
* Detection: Port open on server (in service menu)\
  If a test message has been sent, a red or green square is displayed behind the input window for the port, depending on whether the port is open or not. This feature helps to find errors.

### Fixed

* Bluetooth transmission power had a spelling mistake

### Changed

* Default setting Brewbox Username/Password is now empty.
* Bluetooth is deactivated by default
* Higher resolution for battery level calculation

## Version 1.2.12 - 2022-2-18

### fixed

*   Wrong values for Grainfather, Brewfather and Ubidots.\\

    Note on Ubidots:\
    The provider only allows a certain number of variables per device.\
    Deleting the variables that are not needed can prevent transmission artefacts.

{% file src="broken-reference" %}

## Version 1.2.11 - 2022-2-10

### Fixed

* Reading the temperature more stable\
  some customers had experienced unstable temperature values. A mechanism was installed that checks the temperature for plausibility and only accepts it if it is given.

## Version 1.2.10 - 2022-1-16

### Added

* Parameter passing in the URL was introduced.\
  Instruction you find here[#url-replacement-feature](connect\_to\_http.md#url-replacement-feature "mention")

### Fixed

* Support page was revised
* InfluxDB name was fixed

### Changed

* The default path for Brewfather was adjusted
* Telegram UI was deleted, because not yet implemented in the backend
* Thimgsspeak UI was deleted, because not implemented in the backend yet
* SoftwareReset was deleted, because there were unintended resets. To reset the Hydrom via software, the URI "/reset" must be entered after the IP address.

## Version 1.2.9 - 2022-1-10

### Geändert

* Die Werte für Tilt und Plato wurden in den Services vertauscht. Dadurch ist das Hydrom kompatibel zu den iSpindel-Anwendungen.

## Version 1.2.8 - 2022-1-5

### Hinzugefügt

* Plainwatercalibration wird unterstützt

## Version 1.2.7 - 2022-1-1

### Hinzugefügt

* Grainfather wird unterstützt

## Version 1.2.6 - 2021-12-31

### Behoben

* Fehler beim Zurücksetzen auf die Werkseinstellungen wurde behoben

### Geändert

* Die LEDs blinken nun nicht mehr, wenn das Hydrom durch den Timer aufgeweckt wird.
* Vor dem Werksreset werden alle Einstellungen eingelesen, da die Offsets der MPU6050 nicht zurückgesetzt werden.

## Version 1.2.5 - 2021-12-30

### Behoben

* Das Zurücksetzen wurde stabilisiert, so dass ein Zurücksetzen immer noch möglich ist, wenn Einstellungen das Hydrom zu früh zum Absturz bringen.

### Geändert

* Es wird per LED angezeigt, wenn Sie sich auf ein "Zurücksetzen" zubewegen. Die LEDs flackern in 500ms, bis die 8 Sekunden Wartezeit erreicht sind. Dann endet das Flackern mit einer grünen LED.

## Version 1.2.4 - 2021-12-15

### Behoben

* Einige Verbesserungen aus dem Feedback der Tester

### Geändert

* Anpassungen an der UI nach Rückmeldungen der Tester
* Die Grenze des Plato-Berechnungspolynoms wurde von max x^3 auf x^6 angehoben.

## Version 1.2.0 - 2021-11-03

### Hinzugefügt

* Deepsleep so lange wie nötig
* Firmware-Upload über Webinterface
* Kalibrierungsassistent (Zucker- und Referenzmethode)
* BLE-Unterstützung
* Wifi (Standalone und Client-Modus)
* Sichern/Wiederherstellen von Einstellungen
* Ultra niedriger Stromverbrauchsalgorithmus
* Multible Cloud-Services Unterstützung
  * Brewblox
  * Brewfather
  * Craftbeerpi
  * Fhem
  * Http
  * InfluxDB
  * Mqtt
  * Prometheus
  * Tcontrol
  * Tcp
  * Telegram
  * ThingSpeak
  * Ubidots
* MPU ist kalibriert
* Drift Compansation
* Unterstützung mehrerer Einheiten für Temperatur und Plato
  * Plato
  * Spezifische Schwerkraft
  * Schwerkraft (Lage des Hydroms im Raum)
  * Kelvin
  * Fahrenheit
  * Celsius
* Unterstützung von Signal-LEDs zur Erhöhung der Bedienbarkeit.
* Intuitive Weboberfläche
* Glättung der Messwerte
* Unterstützung für eine Reset-Taste
* Konfigurierbarer Name zur Unterstützung mehrerer Geräte parallel.