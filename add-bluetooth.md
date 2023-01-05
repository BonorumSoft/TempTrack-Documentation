---
description: >-
  The TempTrack supports iBeacon technology and enables Bluetooth Low Energy data
  transmission to smartphones and tablets in the surrounding area.
---

# Change Bluetooth Settings



{% hint style="success" %}
**Precondition:**

To make this setting you must have access to the user interface. If this is not the case, see here how to do it:[access-to-the-user-interface.md](access-to-the-user-interface.md "mention")
{% endhint %}

## Step 1: Open the Menue

To access the menu bar you have to click on the three lines in the upper left corner. (See arrow)\
Then the menu bar will open.

<figure><img src=".gitbook/assets/Folie4.png" alt=""><figcaption></figcaption></figure>

## Select "Service"

The "Services" page is a resource that allows users to select and configure various interfaces and cloud services for use with their system. On this page, users can choose from three different interfaces - HTTP, MQTT, and TCP - and several cloud services, and then activate and parameterize these options to suit their needs. This page is a useful tool for those who want to connect their system to the cloud or other external services and customize the way in which data is transmitted and received. With the options available on the "Services" page, users can tailor their system to meet their specific requirements and ensure that it is able to communicate effectively with other devices and systems.

## Step 3: Enable Bluetooth

The TempTrack will now send the following measured values via bluetooth after a restart by DeepSleep. For this, DeepSleep must also be activated as shown in the picture below.

{% hint style="warning" %}
The "test message" option is not available for Bluetooth. So you have to wait until the TempTrack wakes up from a deep sleep. Hier findest du die Anleitu
{% endhint %}

![Enabled Bluetooth](.gitbook/assets/Folie26.png)

{% hint style="warning" %}
The "test message" option is not available for Bluetooth. So you have to wait until the TempTrack wakes up from a deep sleep.
{% endhint %}

## Choose UUID

Up to 8 TempTrack can be connected in parallel via Bluetooth. The different devices are then assigned different colors.

## Choose the transmission power

In the TempTrack, the power with which Bluetooth is transmitted can be set here. The range increases with higher transmission power. But beware, the battery life will also decrease with higher transmission power.

The powers with ascending transmission power:

*   ESP\_PWR\_LVL\_N14

    Corresponding to -14dbm
*   ESP\_PWR\_LVL\_N11

    Corresponding to -11dbm
*   ESP\_PWR\_LVL\_N8

    Corresponding to -8dbm
*   ESP\_PWR\_LVL\_N5

    Corresponding to -5dbm
*   ESP\_PWR\_LVL\_N2

    Corresponding to -2dbm
*   ESP\_PWR\_LVL\_P1

    Corresponding to 1dbm
*   ESP\_PWR\_LVL\_P4

    Corresponding to 4dbm
*   ESP\_PWR\_LVL\_P7

    Corresponding to 7dbm

### Save Settings

Saving the data is important because it is the only way to connect to the service after waking up from DeepSleep.

![Pressing the "save" button saves the settings.](.gitbook/assets/Folie5.png)

You can check whether the saving was successful by looking at the settings file at http://TempTrack001/settings.json/. to check if the save was successful. This file is the permanent memory of the TempTrack.

A second way to check the saving is to reload the page (all browsers offer this). If the properties are then reloaded, the TempTrack has accepted them, otherwise the old settings are reloaded.

### activate DeepSleep

Activating DeepSleep is mandatory for the TempTrack to be able to send data. If DeepSleep is activated, the TempTrack wakes up after the set time and sends the data to the set service. Afterwards, the TempTrack goes back to sleep and waits for the new service.

{% content-ref url="enable-deepsleep.md" %}
[enable-deepsleep.md](enable-deepsleep.md)
{% endcontent-ref %}
