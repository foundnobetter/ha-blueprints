# HA Blueprints

Collection of Home Assistant automation blueprints for AWTRIX / SVITRIX displays.

## Included Blueprints

- `solarpower.yaml`
  - Solar Power Monitor for current solar production.
  - Displays watts or kilowatts with color-coded icons.
  - Supports optional night filtering and hide-at-zero behavior.
  - Optional display loop position via `pos`.
  ![solarpower_screen](image-1.png)

- `solarbattery.yaml`
  - Solar Battery Status for PV battery charge level.
  - Shows percentage with colored icons and progress bar.
  - Optional display loop position via `pos`.
  ![solarbattery_screen](image.png)

## Import Links

- `solarpower.yaml`:
  [![Import Solar Power Monitor](https://img.shields.io/badge/Import-Solar%20Power-blue?style=flat-square)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Ffoundnobetter%2Fha-blueprints%2Fmain%2Fsolarpower.yaml)
- `solarbattery.yaml`:
  [![Import Solar Battery Status](https://img.shields.io/badge/Import-Solar%20Battery-blue?style=flat-square)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Ffoundnobetter%2Fha-blueprints%2Fmain%2Fsolarbattery.yaml)

Use these buttons to open the Home Assistant blueprint import page directly.

## Requirements

- Home Assistant with automation-blueprint support.
- AWTRIX / SVITRIX device(s) connected via MQTT.
- MQTT integration and home assistant device discovery.
- Required icons installed on the device(s).

### Required icons

- `solarpower.yaml`:
  - 54156 (solar-green)
  - 50557 (solar-white-dyn)
  - 50556 (solar-static)
  - 54876 (Solar Power Night Light)

- `solarbattery.yaml`:
  - 6358 (battery full)
  - 6356 (battery medium)
  - 6354 (battery empty)

## Usage

1. Copy the blueprint files to your Home Assistant `blueprints/automation/` folder.
2. Reload blueprints in Home Assistant.
3. Create an automation from the blueprint.
4. Select the AWTRIX / SVITRIX device and appropriate sensor.
5. Adjust thresholds and optional display position as needed.

---

# Deutsche Zusammenfassung

Sammlung von Home Assistant Blueprints für AWTRIX / SVITRIX Displays.

- `solarpower.yaml`: Zeigt die aktuelle Solarproduktion als Watt / Kilowatt an.
- `solarbattery.yaml`: Zeigt den Ladezustand der PV-Batterie in Prozent an.

Voraussetzungen:
- Home Assistant mit MQTT
- AWTRIX / SVITRIX Gerät
- Benötigte Icons auf dem Display installiert
