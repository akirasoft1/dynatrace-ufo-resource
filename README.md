Dynatrace UFO resource for Concourse
====================================

Allows setting status LEDs on [Dynatrace UFO](https://github.com/Dynatrace/ufo-esp32) via Concourse  
Used within the [PivotalDevOpsPipeline demo](https://github.com/akirasoft/PivotalDevOpsTutorial)

Resource Type Configuration
---------------------------

```yaml
resource_types:
- name: dynatrace-ufo-resource
  type: docker-image
  source:
    repository: mvilliger/dynatrace-ufo-resource
```

Source Configuration
--------------------

```yaml
- name: ufo
  type: dynatrace-ufo-resource
  source:
    UFO_IP: 192.0.2.1
```

Behavior
--------

### `out`: Sets notification LEDs

Sets notification LEDs per the configured parameters.

#### Parameters

Required:

- `UFO_ROW`: Either top or bottom, case sensitive
- `UFO_COLOR`: RGB hex code for LED color. ex. 00ff00 for green, ff0000 for red

A sample pipeline utilizing this resource can be found in the [PivotalDevOpsPipeline repo.](https://github.com/akirasoft/PivotalDevOpsTutorial)
More documentation on the capabilities of the Dynatrace UFO can be found [here.](https://github.com/Dynatrace/ufo-esp32)

