---
title: "Sengled E1ACA4ABE38A control via MQTT"
description: "Integrate your Sengled E1ACA4ABE38A via Zigbee2mqtt with whatever smart home
 infrastructure you are using without the vendors bridge or gateway."
---

*To contribute to this page, edit the following
[file](https://github.com/Koenkk/zigbee2mqtt.io/blob/master/docs/devices/E1ACA4ABE38A.md)*

# Sengled E1ACA4ABE38A

| Model | E1ACA4ABE38A  |
| Vendor  | Sengled  |
| Description | Element downlight smart LED bulb |
| Supports | on/off, brightness |
| Picture | ![Sengled E1ACA4ABE38A](../images/devices/E1ACA4ABE38A.jpg) |

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


