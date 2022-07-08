[![License][license-shield]](LICENSE)

# Dew Point Calculator for Home Assistant
[Home Assistant](https://www.home-assistant.io/) custom component to calculate dew point using temperature and humidity sensors based on [PsychroLib](https://github.com/psychrometrics/psychrolib).

This repository was [forked](https://github.com/ehn/home-assistant-dewpoint) for updates.

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

[license-shield]: https://img.shields.io/github/license/ehn/home-assistant-dewpoint.svg?style=for-the-badge
