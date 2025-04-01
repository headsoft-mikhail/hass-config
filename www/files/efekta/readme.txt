To add EFEKTA Smart Air Box to zigbee2mqtt:
1) copy EFEKTA_Smart_AQ_Box_R2.js to /config/zigbee2mqtt/external_converters
2) open /config/zigbee2mqtt/configuretion.yaml and add to the root:
external_converters:
  - external_converters/EFEKTA_Smart_AQ_Box_R2.js
3) restart zigbee2mqtt
4) enable visibility in zigbee2mqtt UI
5) hold button on the device 5 sec
6) give a device human-readable name, select option to change HA entity name too 
Done!

Device description:
https://telegra.ph/Datchik-kachestva-vozduha-EFEKTA-Smart-Air-Quality-Box--Zigbee-30-08-23

EFEKTA_Smart_AQ_Box_R2.js:
https://github.com/smartboxchannel/EFEKTA-Smart-Air-Quality-Box/tree/main/Z2M_Converter