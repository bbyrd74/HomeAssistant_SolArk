# SolArk Cloud – Home Assistant Integration (v4.0.2, STROG/protocol-2 aware)

Custom Home Assistant integration for SolArk Cloud using the OAuth2 API at
https://ecsprod-api-new.solarkcloud.com behind https://www.mysolark.com.

## Highlights

- OAuth login with legacy fallback for older endpoints.
- Polling interval configurable in config flow and options.
- Advanced file logging to `custom_components/solark/solark_debug.log`.
- Diagnostics support from the Home Assistant UI.
- Computed real-time values for STROG / protocol-2 inverters:
  - PV power (aggregate and per-string 1–12).
  - Load power.
  - Grid power (net), per-phase meters, optional import/export if exposed.
  - Battery power, DC bus voltage, and charge current.
  - Battery SOC from curCap / batteryCap.
- Energy today/total and detailed battery & limit parameters exposed as sensors.

Install via HACS as a custom repository, restart HA, then add the **SolArk Cloud**
integration from Settings → Devices & Services.
