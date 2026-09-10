# Setting up the workshop

## Home Assistant installation

- Install Home Assistant on a virtual machine useing the  [offical guide](https://www.home-assistant.io/installation/windows ). Using [Virtual Box](https://www.virtualbox.org/) worked well for me.

- Make the Home Assistant password and username are "TinkerLab"


## Mosquitto broker

[Install MQTT](https://www.home-assistant.io/integrations/mqtt/) onto Home Assistant. Click the add integration button and choose mosquito within Home Assistant.  Check "Start on boot".

Go to http://homeassistant.local:8123/.

Go to Settings ➡️ Apps➡️ Mosquitto broker ➡️ Log. Try project this on half the white board so people can see MQTT events.

## Installing auto-entities

Go to Settings ➡️ Apps ➡️ Install app.
Then click the 3 dots in  the top right corner, then "Repositories" and then "add".

Enter this link https://github.com/hacs/addons and click "add".

Go back to  Settings ➡️ Apps ➡️ Install app. Search "get HACS". click and install the result.

Click "Start".
Click "logs" and wait for it to finish isntalling  then restart home assistant.

Then follow these steps: https://www.hacs.xyz/docs/use/configuration/basic/

Finally install auto-entriries with this link https://my.home-assistant.io/redirect/hacs_repository/?owner=thomasloven&repository=lovelace-auto-entities and restart home assistant.




## Wi-Fi

In Home Assistant go Settings ➡️ System ➡️ Network ➡️ IPv4. **Make sure the IP address is projected on the board or visible somewhere.**
