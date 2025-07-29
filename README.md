# BAS.MY Open Data Project

This project is dedicated to transforming publicly available information about the BAS.MY bus services in various Malaysian cities into the standardized, machine-readable **General Transit Feed Specification (GTFS)** format.

## Project Goal

The primary objective is to create high-quality, open GTFS datasets for BAS.MY services, starting with the networks in **Kota Setar** and **Kangar**. By converting unstructured data (like PDFs and images) into a structured format, we aim to make this transit information accessible for use in applications such as Google Maps, transit apps, and for analysis by researchers and urban planners.

This initiative uses the existing GTFS data for Prasarana's Rapid Penang service, located in the [`prasarana-gtfs`](prasarana-gtfs) directory, as a reference and quality benchmark.

## Current Status & Methodology

The project is being executed in a phased approach for each city's network.

### 1. BAS.MY Kota Setar

*   **Source Data:** [`basmy-kotasetar/map-basmykotasetar.pdf`](basmy-kotasetar/map-basmykotasetar.pdf) and [`basmy-kotasetar/K10.png`](basmy-kotasetar/K10.png)
*   **GTFS Output:** [`basmy-kotasetar/gtfs_basmy_kotasetar/`](basmy-kotasetar/gtfs_basmy_kotasetar/)
*   **Status:**
    *   **Phase 1 (Foundation):** Complete. `agency.txt` and `routes.txt` have been created.
    *   **Phase 2 (Data Extraction):** Complete. A list of all unique stops and landmarks has been extracted into [`basmy-kotasetar/stops_to_geocode.md`](basmy-kotasetar/stops_to_geocode.md).
    *   **Phase 2 (Geocoding):** **Paused.** This step is currently blocked pending the setup of MCP (Model Context Protocol) servers for the Google Maps and GrabMaps APIs, which will be used to programmatically find the latitude and longitude of each stop.

### 2. BAS.MY Kangar

*   **Source Data:** Files within the [`basmy-kangar/`](basmy-kangar/) directory, primarily `20250516_BASMY_Kangar_Master Map.pdf`.
*   **GTFS Output:** [`basmy-kangar/gtfs_basmy_kangar/`](basmy-kangar/gtfs_basmy_kangar/)
*   **Status:**
    *   **Phase 1 (Foundation):** Complete. `agency.txt` and `routes.txt` have been created.
    *   **Phase 2 (Data Extraction):** Complete. A list of all unique stops and landmarks has been extracted into [`basmy-kangar/stops_to_geocode.md`](basmy-kangar/stops_to_geocode.md).
    *   **Phase 2 (Geocoding):** **Paused.** This step is also blocked pending the availability of the geocoding MCP servers.

## Next Steps

1.  Deploy MCP servers for Google Maps and GrabMaps APIs.
2.  Execute the automated geocoding workflow to process the stop lists for both cities.
3.  Proceed with defining trips, schedules, and stop times to complete the GTFS datasets.