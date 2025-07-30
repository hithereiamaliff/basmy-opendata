# BAS.MY Open Data Project

This project is dedicated to transforming publicly available information about the BAS.MY bus services in various Malaysian cities into the standardized, machine-readable **General Transit Feed Specification (GTFS)** format.

## Project Goal

The primary objective is to create high-quality, open GTFS datasets for BAS.MY services, covering the networks in **Kota Setar, Kangar, Ipoh, Kuala Terengganu, Kuching, Melaka, Seremban, and Kota Bharu**. By converting unstructured data (like PDFs and images) into a structured format, we aim to make this transit information accessible for use in applications such as Google Maps, transit apps, and for analysis by researchers and urban planners.

This initiative uses the existing GTFS data for Prasarana's Rapid Penang service, located in the [`prasarana-gtfs`](prasarana-gtfs) directory, as a reference and quality benchmark.

NOTE: BAS.MY Johor Bahru is **excluded** as Causeway Link, the main operator, already hosted their GTFS data on [data.gov.my](https://developer.data.gov.my/realtime-api/gtfs-static).

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
    *   **Phase 1 & 2.1 (Data Extraction):** Complete. Foundational files created and stops list extracted to [`basmy-kangar/stops_to_geocode.md`](basmy-kangar/stops_to_geocode.md).
    *   **Phase 2.2 (Geocoding):** **Paused.** Blocked pending availability of geocoding MCP servers.

### 3. BAS.MY Ipoh

*   **Source Data:** Files within the [`basmy-ipoh/`](basmy-ipoh/) directory.
*   **GTFS Output:** [`basmy-ipoh/gtfs_basmy_ipoh/`](basmy-ipoh/gtfs_basmy_ipoh/)
*   **Status:**
    *   **Phase 1 & 2.1 (Data Extraction):** Complete. Foundational files created and stops list extracted to [`basmy-ipoh/stops_to_geocode.md`](basmy-ipoh/stops_to_geocode.md).
    *   **Phase 2.2 (Geocoding):** **Paused.** Blocked pending availability of geocoding MCP servers.

### 4. BAS.MY Kuala Terengganu

*   **Source Data:** Files within the [`basmy-kualaterengganu/`](basmy-kualaterengganu/) directory.
*   **GTFS Output:** [`basmy-kualaterengganu/gtfs_basmy_kualaterengganu/`](basmy-kualaterengganu/gtfs_basmy_kualaterengganu/)
*   **Status:**
    *   **Phase 1 & 2.1 (Data Extraction):** Complete. Foundational files created and stops list extracted to [`basmy-kualaterengganu/stops_to_geocode.md`](basmy-kualaterengganu/stops_to_geocode.md).
    *   **Phase 2.2 (Geocoding):** **Paused.** Blocked pending availability of geocoding MCP servers.

### 5. BAS.MY Kuching

*   **Source Data:** Files within the [`basmy-kuching/`](basmy-kuching/) directory.
*   **GTFS Output:** [`basmy-kuching/gtfs_basmy_kuching/`](basmy-kuching/gtfs_basmy_kuching/)
*   **Status:**
    *   **Phase 1 (Foundation):** Complete. `agency.txt` and `routes.txt` have been created.
    *   **Phase 2.1 (Data Extraction):** Complete. A list of all unique stops and landmarks has been extracted into [`basmy-kuching/stops_to_geocode.md`](basmy-kuching/stops_to_geocode.md).
    *   **Phase 2.2 (Geocoding):** **Paused.** Blocked pending availability of geocoding MCP servers.

### 6. BAS.MY Melaka

*   **Source Data:** Files within the [`basmy-melaka/`](basmy-melaka/) directory.
*   **GTFS Output:** [`basmy-melaka/gtfs_basmy_melaka/`](basmy-melaka/gtfs_basmy_melaka/)
*   **Status:**
    *   **Phase 1 & 2.1 (Data Extraction):** Complete. Foundational files created and stops list extracted to [`basmy-melaka/stops_to_geocode.md`](basmy-melaka/stops_to_geocode.md).
    *   **Phase 2.2 (Geocoding):** **Paused.** Blocked pending availability of geocoding MCP servers.

### 7. BAS.MY Seremban

*   **Source Data:** Files within the [`basmy-seremban/`](basmy-seremban/) directory.
*   **GTFS Output:** [`basmy-seremban/gtfs_basmy_seremban/`](basmy-seremban/gtfs_basmy_seremban/)
*   **Status:**
    *   **Phase 1 & 2.1 (Data Extraction):** Complete. Foundational files created and stops list extracted to [`basmy-seremban/stops_to_geocode.md`](basmy-seremban/stops_to_geocode.md).
    *   **Phase 2.2 (Geocoding):** **Paused.** Blocked pending availability of geocoding MCP servers.

### 8. BAS.MY Kota Bharu

*   **Source Data:** Files within the [`basmy-kotabharu/`](basmy-kotabharu/) directory.
*   **GTFS Output:** [`basmy-kotabharu/gtfs_basmy_kotabharu/`](basmy-kotabharu/gtfs_basmy_kotabharu/)
*   **Status:**
    *   **Phase 1 & 2.1 (Data Extraction):** Complete. Foundational files created and stops list extracted to [`basmy-kotabharu/stops_to_geocode.md`](basmy-kotabharu/stops_to_geocode.md).
    *   **Phase 2.2 (Geocoding):** **Paused.** Blocked pending availability of geocoding MCP servers.

## Next Steps

1.  **For All Cities:** Deploy MCP servers for Google Maps and GrabMaps APIs.
2.  Execute the automated geocoding workflow to process the stop lists for all cities.
3.  Proceed with defining trips, schedules, and stop times to complete the GTFS datasets.