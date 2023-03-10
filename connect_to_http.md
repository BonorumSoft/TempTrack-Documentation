---
description: >-
  Hypertext Transfer Protocol (HTTP) is an application-layer protocol for
  transmitting hypermedia documents. It was designed for communication between
  web browsers and web servers.
cover: https://labs.tadigital.com/wp-content/uploads/2019/11/http.jpg
coverY: 0
---

# Send Measurements via Webhook



{% hint style="success" %}
**Prerequisite:**

1. **Access to user interface**\
   To make this setting, you must have access to the user interface. If this is not the case, see here how to do it:[access-to-the-user-interface.md](access-to-the-user-interface.md "mention")
2. **Access to an http-Server server/Cloud Service**.\
   An http-Server server has been set up or there is access to a cloud http-Server.
{% endhint %}

## Datatransfer

### Via URL

If placeholders are used in the URL specified in the "URL", the TempTrack will replace them with the current variables.

{VALUE\_TEMPERATURE\_C} --> 25.3

* **{NAME\_DEVICE}** If this variable is used, the TempTrack replaces this placeholder with the current name of the TempTrack. Default: "TempTrack001
* **{VALUE\_TEMPERATURE\_C}** If this variable is used, the TempTrack replaces this placeholder with the currently measured temperature. The unit of this variable is Celsius
* **{VALUE\_RSSI}** If this variable is used, the TempTrack replaces this placeholder with the currently measured Signal Quality.
* **{VALUE\_BATTERY\_VOLTAGE}** If this variable is used, the TempTrack replaces this placeholder with the currently measured Batteryvoltage. The unit of this variable is Volt
* **{VALUE\_BATTERY\_PERCENTAGE}** If this variable is used, the TempTrack replaces this placeholder with the current battery level. The unit of this variable is Percent.

#### Example URL

```url
https://maker.ifttt.com/trigger/TempTrack/with/key/clLb9jfjgngkdovIx?value1={VALUE_TEMPERATURE_C}&value2={VALUE_BATTERY_PERCENTAGE}
```

<figure><img src="https://github.com/BonorumSoft/TempTrack-Handbook/blob/main/.gitbook/assets/Webhook.png" alt=""><figcaption></figcaption></figure>

### via JSON

The TempTrack sends, if you have activated "http", then the TempTrack sends a JSON file to the path specified in the "URL".\
How the file looks like and what the parameters contain you can read here.

* **name**\
  Each device has the name "TempTrack001" by default. This name can be changed at any time to distinguish several devices from each other.\
  [changing-the-TempTrack-name.md](changing-the-TempTrack-name.md "mention")\\
* **angle**\
  This reading is the raw reading of the slope of the TempTrack without any processing.\\
* **temperature**\
  This value is the measured temperature in degrees Celsius.\\
* **temp\_units**\
  A "C" for Celsius is sent here.\\
* **battery**\
  Battery voltage in V\\
* **interval**\
  The interval during which the measured values are sent (+ approx. 23s).\\
* **RSSI**\
  Wifi transmit power

Sample content of the JSON:

```json
{
"name":"TempTrack001",
"ID":3,
"temperature":26.43,
"temp_units":"C",
"battery":3.9,
"interval":900,
"RSSI":63.5
}
```

## Step 1: Open the Menue

To access the menu bar you have to click on the three lines in the upper left corner. (See arrow)\
Then the menu bar will open.

![access the menu bar by clicking the three lines in the upper left corner](.gitbook/assets/Folie4.png)

## Step 2: Select "Service"

The "Services" page is a resource that allows users to select and configure various interfaces and cloud services for use with their system. On this page, users can choose from three different interfaces - HTTP, MQTT, and TCP - and several cloud services, and then activate and parameterize these options to suit their needs. This page is a useful tool for those who want to connect their system to the cloud or other external services and customize the way in which data is transmitted and received. With the options available on the "Services" page, users can tailor their system to meet their specific requirements and ensure that it is able to communicate effectively with other devices and systems.

### Activate http-client and change the settings

On the "Service" page, the http-Server service must be activated.

<figure><img src="https://github.com/BonorumSoft/TempTrack-Handbook/blob/main/.gitbook/assets/Webhook.png" alt=""><figcaption></figcaption></figure>

### additional settings

In order not to consume too much power, we would turn Bluetooth off when it is not needed. It was documented here:

{% content-ref url="add-bluetooth.md" %}
[add-bluetooth.md](add-bluetooth.md)
{% endcontent-ref %}

In order for the TempTrack to transmit the data reliably, a DeepSleep time must be set. This is documented on this page:

{% content-ref url="enable-deepsleep.md" %}
[enable-deepsleep.md](enable-deepsleep.md)
{% endcontent-ref %}

### Save Settings

Saving the data is important because it is the only way to connect to the service after waking up from DeepSleep.

![Pressing the "save" button saves the settings.](.gitbook/assets/Folie5.png)

You can check whether the saving was successful by looking at the settings file at http://TempTrack001/settings.json/. to check if the save was successful. This file is the permanent memory of the TempTrack.

A second way to check the saving is to reload the page (all modern browsers offer this Feature). If the properties are then reloaded, the TempTrack has accepted them, otherwise the old settings are reloaded.

### Send Test-message

By activating this button, you can check whether the TempTrack has a connection to the service and to the individual parts of the service. If you now click on "Save", the set services are executed once and the page is reloaded. On the new page you can see whether the servers are accessible and the ports are open.

![Sending a test message can greatly simplify the process of checking the connection.](.gitbook/assets/Folie6.png)

### activate DeepSleep

Activating DeepSleep is mandatory for the TempTrack to be able to send data. If DeepSleep is activated, the TempTrack wakes up after the set time and sends the data to the set service. Afterwards, the TempTrack goes back to sleep and waits for the new service.

{% content-ref url="enable-deepsleep.md" %}
[enable-deepsleep.md](enable-deepsleep.md)
{% endcontent-ref %}

{% hint style="success" %}
To ensure that the device sends measured values to the Service in the set interval as intended, the TempTrack must be put into deep sleep.

There are two ways to put the TempTrack into deep sleep.

Turning the _**power switch off and on**_ is the easiest way to put the TempTrack into deep sleep.

The alternative way is to put it to sleep _**via the UI**_. To do this, open the navigation bar and go to the "DeepSleep" tab.
{% endhint %}
