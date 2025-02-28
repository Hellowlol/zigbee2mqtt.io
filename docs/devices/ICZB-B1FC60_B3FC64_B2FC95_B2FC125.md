---
title: "iCasa ICZB-B1FC60/B3FC64/B2FC95/B2FC125 control via MQTT"
description: "Integrate your iCasa ICZB-B1FC60/B3FC64/B2FC95/B2FC125 via Zigbee2mqtt with whatever smart home
 infrastructure you are using without the vendors bridge or gateway."
---

*To contribute to this page, edit the following
[file](https://github.com/Koenkk/zigbee2mqtt.io/blob/master/docs/devices/ICZB-B1FC60_B3FC64_B2FC95_B2FC125.md)*

# iCasa ICZB-B1FC60/B3FC64/B2FC95/B2FC125

| Model | ICZB-B1FC60/B3FC64/B2FC95/B2FC125  |
| Vendor  | iCasa  |
| Description | Zigbee 3.0 Filament Lamp 60/64/95/125 mm, 806 lumen, dimmable, clear |
| Supports | on/off, brightness, color temperature |
| Picture | ![iCasa ICZB-B1FC60/B3FC64/B2FC95/B2FC125](../images/devices/ICZB-B1FC60-B3FC64-B2FC95-B2FC125.jpg) |

## Notes


### Device type specific configuration
*[How to use device type specific configuration](../information/configuration.md)*


* `transition`: Controls the transition time (in seconds) of brightness,
color temperature (if applicable) and color (if applicable) changes. Defaults to `0` (no transition).
Note that this value is overridden if a `transition` value is present in the MQTT command payload.


## Manual Home Assistant configuration
Although Home Assistant integration through [MQTT discovery](../integration/home_assistant) is preferred,
manual integration is possible with the following configuration:


{% raw %}
```yaml
light:
  - platform: "mqtt"
    state_topic: "zigbee2mqtt/<FRIENDLY_NAME>"
    availability_topic: "zigbee2mqtt/bridge/state"
    brightness: true
    color_temp: true
    schema: "json"
    command_topic: "zigbee2mqtt/<FRIENDLY_NAME>/set"

sensor:
  - platform: "mqtt"
    state_topic: "zigbee2mqtt/<FRIENDLY_NAME>"
    availability_topic: "zigbee2mqtt/bridge/state"
    unit_of_measurement: "-"
    value_template: "{{ value_json.linkquality }}"
```
{% endraw %}


