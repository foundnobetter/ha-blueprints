# HA Blueprints for AWTRIX displays

<p align="center">
  <img src="AwtrixNG/solarpowerNG_screen.png" width="420" alt="Solar Power Monitor on an Ulanzi TC001 with AWTRIX NG">
</p>

Home Assistant blueprints that show **solar production**, **battery level** and **grid power flow** on an Ulanzi TC001 (or another AWTRIX display).

## Which variant do I need?

| | AWTRIX NG | AWTRIX 3 / SVITRIX |
|---|---|---|
| Folder | [`AwtrixNG`](AwtrixNG/) | [`Awtrix3`](Awtrix3/) |
| Recommended for | new installations | existing AWTRIX 3 / SVITRIX setups |
| Icons | AWTRIX Hub (named icons) | LaMetric icon IDs |
| MQTT topic | `<prefix>/cmd/apps/pushed/<app>` | `<prefix>/custom/<app>` |
| Install guide | [AwtrixNG/README.md](AwtrixNG/README.md) | [Awtrix3/README.md](Awtrix3/README.md) |

The two variants do the same job but are **not interchangeable**: topics, payload and icons differ. Pick the folder that matches the firmware on your display.

## Blueprints

| Blueprint | Shows | AWTRIX NG | AWTRIX 3 / SVITRIX |
|---|---|---|---|
| Solar Power Monitor | current production in W / kW | <img src="AwtrixNG/solarpowerNG_screen.png" width="220"> | <img src="Awtrix3/solarpower_screen.png" width="220"> |
| Solar Battery Status | battery charge in % with progress bar | <img src="AwtrixNG/solarbatteryNG_screen.png" width="220"> | <img src="Awtrix3/solarbattery_screen.png" width="220"> |
| Grid Power Flow Monitor | import / export power | <img src="AwtrixNG/gridpowerNG_screen.png" width="220"> | <img src="Awtrix3/gridpower_screen.png" width="220"> |

## Repository layout

```
Awtrix3/     solarpower.yaml, solarbattery.yaml, gridpower.yaml, screenshots, README.md
AwtrixNG/    solarpowerNG.yaml, solarbatteryNG.yaml, gridpowerNG.yaml, screenshots, README.md
README.md
```

## Credits

Solar Power Monitor is based on the AWTRIX Flows blueprint [Solar Energy Production](https://flows.blueforcer.de/flow/qRWNolZn5X4w) by hupfis and highball.

## Deutsche Kurzfassung

Home-Assistant-Blueprints für den Ulanzi TC001 und kompatible AWTRIX-Displays: Solarproduktion, Batterieladestand und Netzbezug/-einspeisung.

- **AWTRIX NG** (empfohlen für Neuinstallationen): Ordner [`AwtrixNG`](AwtrixNG/), Icons aus dem AWTRIX Hub.
- **AWTRIX 3 / SVITRIX**: Ordner [`Awtrix3`](Awtrix3/), Icons über LaMetric-IDs.

Die Varianten sind nicht austauschbar (andere MQTT-Topics, Payloads und Icons). Installationsanleitung und Import-Buttons stehen jeweils in der README des Ordners.