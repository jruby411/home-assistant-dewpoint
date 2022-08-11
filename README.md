[![License][license-shield]](LICENSE)
[![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg)](https://github.com/hacs/integration)

# Dew Point Calculator for Home Assistant
[Home Assistant](https://www.home-assistant.io/) custom component to calculate dew point using temperature and humidity sensors based on
code from [ha-dewpoint](https://github.com/alf-scotland/ha-dewpoint) and a fork from [dewpoint](https://github.com/elwing00/home-assistant-dewpoint).

This sensor should work fine in the containerized version of Home Assistant. The psychrolib dependency has been removed.

## Installation
Use [HACS](https://hacs.xyz/) with this custom repository or copy `custom_components/` to your HA configuration.

## Example configuration.yaml
```yaml
sensor:
  - platform: dewpoint
    sensors:
      dewpoint_outside:
        temperature: sensor.temperature_outside
        rel_hum: sensor.humidity_outside
      dewpoint_office:
        temperature: sensor.temperature_office
        rel_hum: sensor.humidity_office
      ...
```

## Configuration options
Key | Type | Required | Description
-- | -- | -- | --
`sensors` | `list` | `True` | List of dew point sensors to generate

### Configuration options for `sensors` list

Key | Type | Required | Default | Description
-- | -- | -- | -- | --
`friendly_name` | `string` | `False` | `sensor name` | Friendly name for the new sensor entity
`temperature` | `entity_id` | `True` | `none` | Entity from which to get the dry-bulb temperature
`rel_hum` | `entity_id` | `True` | `none` | Entity from which to get the relative humidity

***

[license-shield]: https://img.shields.io/github/license/jruby411/home-assistant-dewpoint.svg?style=flat
