# HA Blueprints

Collection of Home Assistant automation blueprints for Ulanzi TC001 and compatible AWTRIX LED displays.

## Compatibility

This repository contains blueprints for two different AWTRIX generations. The blueprints offer the same core functionality but use different MQTT topics/payloads and icon workflows.

- **AWTRIX 3 / SVITRIX (legacy)** — original blueprints and screenshots in this README are for this variant. Icons are typically installed manually or referenced by numeric IDs.
- **AWTRIX NG** — newer firmware with Home Assistant discovery and a different pushed-app payload. Icons for AWTRIX NG are usually provided via the AWTRIX Hub (icon names like `bat00`..`bat100`, `solar_hoch`, `solar_mittel`, `solar_niedrig`, `solar_nacht`).

> Hinweis: Die vorhandenen Screenshots stammen von der AWTRIX 3 / SVITRIX-Variante. AWTRIX NG nutzt die gleichen Funktionen, aber andere Icons (über den AWTRIX Hub).

## Included Blueprints (AWTRIX 3 / SVITRIX)

### Solar Power Monitor (`solarpower.yaml`)
Displays current solar power production on your display in watts or kilowatts with color-coded icons.
- 🟢 Green: High production (above high threshold)
- 🟡 Yellow: Medium production (between high and low threshold)
- 🟠 Orange: Low production (below low threshold but above 0W)
- ⚪ Gray: No production (0W or night time)

Features: Optional night-time filtering, hide-at-zero behavior, display position control.

![solarpower_screen](solarpower_screen.png)

### Solar Battery Status (`solarbattery.yaml`)
Displays your PV battery charge level in percent with color-coded icons and progress bar.
- 🟢 Green: High charge (above high threshold)
- 🟡 Yellow: Medium charge (between high and low threshold)
- 🔴 Red: Low charge (below low threshold)

Optional: Power sensor for progress bar charging/discharging indication (green for charging, orange for discharging, white for idle). Without power sensor, progress bar uses battery state color.

![solarbattery_screen](solarbattery_screen.png)

### Grid Power Flow Monitor (`gridpower.yaml`)
Displays current grid import/export power with a tolerance-based neutral zone.
- 🟢 Green: Export / Feed-in to grid
- ⚪ White: Neutral range around 0 W
- 🟠 Orange: Import / Draw from grid

Display toggles based on power flow within tolerance threshold.

![gridpower](gridpower.png)

## Included Blueprints (AWTRIX NG)

The NG variants are provided as separate files with the `NG` suffix (for example `solarpowerNG.yaml`, `solarbatteryNG.yaml`). They use the AWTRIX NG pushed-app MQTT topic and payload structure and expect icon names that are typically distributed via the AWTRIX Hub.

- `solarpowerNG.yaml`: shows production (W / kW) with NG-specific icon names and payload fields (`icon`, `text`, `textColor`, `lifetimeMs`). Can send an empty payload `{}` to remove the app (e.g., at night).
- `solarbatteryNG.yaml`: shows battery SOC, progress bar and colors with NG-specific icon names like `bat00`..`bat100`, and uses `progress` / `progressColor` fields.

AWTRIX NG icons: upload via AWTRIX Hub or the display web UI. Icon IDs are case-sensitive and must match the names expected by the blueprints.

Recommendation: AWTRIX NG is the preferred firmware for new installations — it offers Home Assistant discovery, a modern API and active development. See the AWTRIX NG repository: https://github.com/Blueforcer/awtrix-ng

Note: The AWTRIX NG variant for the Grid Power Monitor (`gridpowerNG.yaml`) is not available yet and will be added soon.

## Import Links

- `solarpower.yaml`:
  [![Import Solar Power Monitor](https://img.shields.io/badge/Import-Solar%20Power-blue?style=flat-square)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Ffoundnobetter%2Fha-blueprints%2Fmain%2Fsolarpower.yaml)
- `solarbattery.yaml`:
  [![Import Solar Battery Status](https://img.shields.io/badge/Import-Solar%20Battery-blue?style=flat-square)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Ffoundnobetter%2Fha-blueprints%2Fmain%2Fsolarbattery.yaml)
- `gridpower.yaml`:
  [![Import Grid Power Flow Monitor](https://img.shields.io/badge/Import-Grid%20Power-blue?style=flat-square)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Ffoundnobetter%2Fha-blueprints%2Fmain%2Fgridpower.yaml)
- `solarpowerNG.yaml`:
  [![Import Solar Power Monitor NG](https://img.shields.io/badge/Import-Solar%20Power%20(NG)-blue?style=flat-square)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Ffoundnobetter%2Fha-blueprints%2Fmain%2FsolarpowerNG.yaml)
- `solarbatteryNG.yaml`:
  [![Import Solar Battery Status NG](https://img.shields.io/badge/Import-Solar%20Battery%20(NG)-blue?style=flat-square)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Ffoundnobetter%2Fha-blueprints%2Fmain%2FsolarbatteryNG.yaml)

Use these buttons to open the Home Assistant blueprint import page directly.

## Requirements

- Home Assistant with automation-blueprint support
- Ulanzi TC001 or compatible device with AWTRIX / SVITRIX or AWTRIX NG firmware
- MQTT integration and Home Assistant device discovery

### Icons & Notes

- AWTRIX 3 / SVITRIX: icons referenced in the original blueprints (numeric IDs or uploaded GIFs). Screenshots in this README reflect this variant.
- AWTRIX NG: icons are typically named (e.g. `bat00`..`bat100`, `solar_hoch`, `solar_mittel`, `solar_niedrig`, `solar_nacht`) and are best installed via the AWTRIX Hub or the display web UI. Icon IDs are case-sensitive.

## Setup & Usage

1. Use import buttons above or copy blueprint files to `blueprints/automation/` folder.
2. Reload blueprints in Home Assistant.
3. Create automation from blueprint.
4. Select the correct device type (AWTRIX 3 / SVITRIX or AWTRIX NG) and the appropriate sensors.
5. Adjust thresholds, icon names (for NG) and optional display position as needed.

---

# Deutsche Zusammenfassung

Sammlung von Home Assistant Blueprints für Ulanzi TC001 und kompatible AWTRIX LED-Displays.

## Kompatibilität

Die Blueprints sind in zwei Bereiche gegliedert: **AWTRIX 3 / SVITRIX (legacy)** und **AWTRIX NG**. Die Funktionalität ist weitgehend identisch, jedoch unterscheiden sich MQTT-Topics/Payloads und Icon-Workflows.

- Screenshots in diesem README zeigen die AWTRIX 3 / SVITRIX-Variante.
- AWTRIX NG verwendet andere Icon-Namen, die über den AWTRIX Hub verteilt werden können.

Bevorzugt: AWTRIX NG wird für neue Installationen empfohlen — moderne API, Home Assistant Discovery und aktive Entwicklung. Repo: https://github.com/Blueforcer/awtrix-ng

Hinweis: Die AWTRIX NG-Variante für den Grid Power Monitor (`gridpowerNG.yaml`) fehlt derzeit noch und wird demnächst ergänzt.

## Enthaltene Blueprints (AWTRIX 3 / SVITRIX)

### Solar Power Monitor (`solarpower.yaml`)
Zeigt die aktuelle Solarproduktion in Watt oder Kilowatt mit farbcodierten Icons an.
- 🟢 Grün: Hohe Produktion (über Schwellenwert High)
- 🟡 Gelb: Mittlere Produktion (zwischen High und Low)
- 🟠 Orange: Niedrige Produktion (unter Low, aber über 0W)
- ⚪ Grau: Keine Produktion (0W oder Nacht)

Optionale Funktionen: Nachtzeitfilterung, Ausblendung bei 0W, Anzeigeposition im Display-Loop.

### Solar Battery Status (`solarbattery.yaml`)
Zeigt den Ladezustand der PV-Batterie in Prozent mit farbcodierten Icons und Fortschrittsbalken an.
- 🟢 Grün: Hoher Ladezustand (über Schwellenwert High)
- 🟡 Gelb: Mittlerer Ladezustand (zwischen High und Low)
- 🔴 Rot: Niedriger Ladezustand (unter Schwellenwert Low)

Optionale Stromsensor-Unterstützung für Lade/Entlade-Indikatoren.

### Grid Power Flow Monitor (`gridpower.yaml`)
Zeigt den aktuellen Netzstrom (Import/Export) mit toleranzbasierter Neutralzone an.
- 🟢 Grün: Einspeisung ins Netz (Export)
- ⚪ Weiß: Neutralzone um 0W
- 🟠 Orange: Bezug aus dem Netz (Import)

## Anforderungen

- Home Assistant mit Blueprint-Unterstützung
- Ulanzi TC001 oder kompatibles Gerät mit AWTRIX / SVITRIX oder AWTRIX NG Firmware
- MQTT-Integration und Home Assistant Device Discovery

## Einrichtung & Verwendung

1. Import-Buttons oben verwenden oder Blueprint-Dateien manuell in den `blueprints/automation/` Ordner kopieren.
2. Blueprints in Home Assistant neu laden.
3. Automation aus dem Blueprint erstellen.
4. Gerätetyp (AWTRIX 3 / SVITRIX oder AWTRIX NG) und passende Sensor(en) wählen.
5. Schwellenwerte, Icon-Namen (bei NG) und Anzeigeposition anpassen.

