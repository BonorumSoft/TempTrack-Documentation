# Access to the user interface



{% hint style="success" %}
**Precondition:**

1. The TempTrack must be powered on\
   How to switch on the TempTrack can be found here:\
   [turn-on-the-TempTrack.md](turn-on-the-TempTrack.md "mention")
2.  The TempTrack must be in configuration mode\
    In normal operation, no user interface is loaded in order not to waste the battery charge. Therefore, the TempTrack must be put into configuration mode.

    You can detect if the TempTrack is in Deepsleep when the green LED is on as described here: [#1-status-led-of-the-TempTrack-logic](indicator-leds.md#1-status-led-of-the-TempTrack-logic "mention")

    If the TempTrack is in Deepsleep, it can be woken up according to the instructions on this page:\
    [wakeup-the-TempTrack.md](wakeup-the-TempTrack.md "mention")
{% endhint %}

## Connect to the TempTrack via browser

{% hint style="warning" %}
The TempTrack unfortunately only supports Wifi with a frequency of 2.5 GHz, so it is not able to receive 5 GHz Wifi.
{% endhint %}

{% tabs %}
{% tab title="Accesspoint Mode" %}
1. Connect to the network of the TempTrack by selecting the Wifi "TempTrack\_XXXXX".
2. Access the WebUI in any browser at reach the following address [http://192.168.2.1](http://192.168.2.1)
{% endtab %}

{% tab title="Client Mode" %}
Access the WebUI in any browser at reach the following address [http://TempTrack001/](http://TempTrack001)

![Scan me to Access the WebFrontend](.gitbook/assets/Folie45.png)

If the name of the TempTrack was changed, the TempTrack must be reached under the newly selected name.

{% hint style="warning" %}
It may be that your network infrastructure prohibits setting custom names. Then you have to use the alternative way mentioned below
{% endhint %}

Another way for more advanced users is the following:

1. Connect to your router
2. find out which IP the TempTrack has been assigned.
3. open in the browser the address: http://\<IP-Adress>
{% endtab %}
{% endtabs %}
