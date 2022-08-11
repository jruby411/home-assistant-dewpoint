# Dew Point Sensor

A custom sensor to calculate the
[dew point](https://en.wikipedia.org/wiki/Dew_point) from temperature and
humidity. It is adapted from Home Assistant's
[Mold Indicator](https://www.home-assistant.io/integrations/mold_indicator/)
sensor allowing to use dew points without the need of external references.
This sensor was merged with the dew point sensor created from the fork of
[dewpoint](https://github.com/elwing00/home-assistant-dewpoint)

## Example

To use the Dew Point sensor in your installation, add the following to your
`configuration.yaml` file:

```yaml
# For Best Results put all sensors in one file.
# Example configuration.yaml entry
sensor: !include sensors.yaml

# Example sensors.yaml
- platform: dewpoint
  sensors:
    dewpoint_outside:
      temperature: sensor.temperature_out
      rel_hum: sensor.humidity_out
    dewpoint_office:
      temperature: sensor.temp_inside
      rel_hum: sensor.humidity_inside
```
