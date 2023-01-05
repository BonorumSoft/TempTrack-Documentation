# Access to the user interface

Diesen Anleitung ist auch auf Deutsch verfügbar: [Link](https://anleitung.hydrom.io)

{% hint style="success" %}
**Precondition:**

1. The Hydrom must be powered on\
   How to switch on the Hydrom can be found here:\
   [turn-on-the-hydrom.md](turn-on-the-hydrom.md "mention")
2.  The Hydrom must be in configuration mode\
    In normal operation, no user interface is loaded in order not to waste the battery charge. Therefore, the Hydrom must be put into configuration mode.

    You can detect if the Hydrom is in Deepsleep when the green LED is on as described here: [#1-status-led-of-the-hydrom-logic](indicator-leds.md#1-status-led-of-the-hydrom-logic "mention")

    If the Hydrom is in Deepsleep, it can be woken up according to the instructions on this page:\
    [wakeup-the-hydrom.md](wakeup-the-hydrom.md "mention")
{% endhint %}

## Connect to the Hydrom via browser

{% hint style="warning" %}
The Hydrom unfortunately only supports Wifi with a frequency of 2.5 GHz, so it is not able to receive 5 GHz Wifi.
{% endhint %}

{% tabs %}
{% tab title="Accesspoint Mode" %}
1. Connect to the network of the Hydrom by selecting the Wifi "hydrom\_XXXXX".
2. Access the WebUI in any browser at reach the following address [http://192.168.2.1](http://192.168.2.1)
{% endtab %}

{% tab title="Client Mode" %}
Access the WebUI in any browser at reach the following address [http://hydrom001/](http://hydrom001)

![Scan me to Access the WebFrontend](.gitbook/assets/Folie45.png)

If the name of the hydrom was changed, the hydrom must be reached under the newly selected name.

{% hint style="warning" %}
It may be that your network infrastructure prohibits setting custom names. Then you have to use the alternative way mentioned below
{% endhint %}

Another way for more advanced users is the following:

1. Connect to your router
2. find out which IP the Hydrom has been assigned.
3. open in the browser the address: http://\<IP-Adress>
{% endtab %}
{% endtabs %}
