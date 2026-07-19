# Vessel & Truck Tracking

A browser-based logistics control-centre prototype for monitoring vessel arrivals at Chennai Container Terminal, cargo manifests, containers, truck assignments, and simulated AIS/GPS positions.

## Start the application

1. Download or clone this repository.
2. Open `index.html` in a modern web browser.
3. Open the master-data pages once to load their browser-local sample data.
4. In **Vessel Tracking**, search for a vessel to filter the satellite map to that vessel and its linked container trucks.

Satellite imagery is loaded from an online map service, so an internet connection is required for the basemap.

## Modules

| File | Purpose |
|---|---|
| `index.html` | Home dashboard, vessel tracking, satellite map, and linked truck display |
| `vessel-master-form.html` | Vessel reference records and vessel lifecycle details |
| `port-master.html` | Indian port reference records |
| `container-master.html` | Container identity, equipment, ownership, and logistics status |
| `truck-master.html` | Fleet, driver, and truck-status reference records |
| `cargo-manifest.html` | Vessel cargo manifests with linked containers |
| `container-truck-mapping.html` | Container-to-truck operational assignments |

## Sample data

- Five vessel manifests, each with 20 containers.
- 200 valid-format sample container records.
- 200 sample truck records.
- 200 container-to-truck assignments.
- Simulated AIS tracks for five vessels approaching Chennai Container Terminal.
- Simulated current truck GPS data for Chennai-area road locations.

Supporting data files:

- `chennai-sample-ais-data.xlsx`
- `truck-current-tracking-data.xlsx`
- `logistics-control-centre-logical-design.docx`

## Tracking relationship

```text
Vessel -> Cargo Manifest -> Container -> Container-Truck Mapping -> Truck GPS Position
```

When a vessel is selected in the home-page tracker, the application finds its cargo manifest, reads the listed container numbers, retrieves linked truck assignments, and displays those trucks on the map.

## Important limitation

This is a prototype. AIS, truck GPS, manifest, container, and mapping data are simulated and stored in browser local storage. A production version should integrate authenticated AIS, telematics/GPS, carrier/EDI, and terminal-operating-system APIs with a server-side database and access controls.
