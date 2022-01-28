# Input select tile card (homekit style)
Input select homekit tile lovelace card.
Can be used in combination with my homekit style card: https://github.com/DBuit/Homekit-panel-card


## Configuration

### Installation instructions

**HACS installation:**
Go to the hacs store and use the repo url `REPO URL HERE` and add this as a custom repository under settings.

Add the following to your ui-lovelace.yaml:
```yaml
resources:
  url: /community_plugin/plugin/input-select-tile-card.js
  type: module
```

**Manual installation:**
Copy the .js file from the dist directory to your www directory and add the following to your ui-lovelace.yaml file:

```yaml
resources:
  url: /local/input-select-tile-card.js
  type: module
```

### Main Options

| Name | Type | Default | Supported options | Description |
| -------------- | ----------- | ------------ | ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `entity` | string | **Required** | `climate.nest` | The entity of the input select it should use |
| `name` | string | **Required** | `test` | The name of the tile |
| `icon` | string | **Required** | `mdi:icon` | An icon to show on the tile |
| `activeState` | string | **Required** | `state` | The state of the input select the tile should show as active |


Example configuration in lovelace-ui.yaml in combination with **Homekit panel card**:
```
  - title: "Home"
    panel: true
    cards:
      - type: "custom:homekit-card"
        entities:
          - title: Luxaflex
            entities:
              - card: custom:input-select-tile-card
                cardOptions:
                  name: Radio538
                  entity: input_select.radio_station
                  activeState: Radio538
```
