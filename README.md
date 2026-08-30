# BAS.MY Open Data: Ridership Statistics

This project provides open, machine-readable ridership statistics for the BAS.MY bus services in various Malaysian cities.

## Disclaimer

This is an independent, community-driven project and is **not** an official open data initiative by the Agensi Pengangkutan Awam Darat (APAD). While the data is sourced from official publications, this project is not affiliated with or endorsed by APAD.

## Data Files

The ridership data is available in two formats:

*   **JSON**: Machine-readable data, ideal for software integration and analysis. Located in the [`json/`](json/) directory.
    *   [`json/yearly_ridership.json`](json/yearly_ridership.json): Contains the total number of passengers, aggregated by year and by month.
    *   [`json/daily_average_ridership.json`](json/daily_average_ridership.json): Contains the average number of daily passengers, aggregated by year and by month.
*   **Markdown**: The original, human-readable source files. Located in the [`markdown/`](markdown/) directory.
    *   [`markdown/mybas-statistics-jumlahpenumpangtahunan.md`](markdown/mybas-statistics-jumlahpenumpangtahunan.md)
    *   [`markdown/mybas-statistics-puratapenumpangharian.md`](markdown/mybas-statistics-puratapenumpangharian.md)

## Data Manifest

To assist AI agents in discovering and understanding the data files in this repository, a manifest file is provided in the root directory:

*   [`manifest.json`](manifest.json): A machine-readable JSON file that lists all data files, their paths, and a brief description of their contents.

This file is intended to be used by AI agents to programmatically locate and interpret the data, making it easier to integrate with this repository.

## Accessing Data via MCP

For AI agents and other automated systems, the data in this repository can be accessed programmatically using a Model Context Protocol (MCP) server for GitHub.

I recommend using the **GitHub MCP server by Smithery.ai**:
*   **Server URL:** [`https://smithery.ai/server/@smithery-ai/github`](https://smithery.ai/server/@smithery-ai/github)

You can use this server's tools (e.g., `get_file_contents`) to read the JSON files directly from the repository.

*   **Owner:** `hithereiamaliff`
*   **Repo:** `basmy-opendata`

## Data Coverage

*   **Yearly totals**: 2019 through the current year.
*   **Monthly breakdowns**: 2024, 2025, and 2026 (January through June, ongoing).
*   **Partial-year entries** are marked with an asterisk in the `year` field (e.g. `"2026*"`) when the year is still in progress. Consumers should treat `year` as `number | string` rather than strictly numeric.
*   Check `last_updated` at the top of each JSON file for the latest refresh date.

## Covered Networks

The ridership statistics currently include data for the following BAS.MY service areas:

*   Ipoh
*   Johor Bahru
*   Kangar
*   Kota Bharu *(since Jul 2025)*
*   Kota Setar *(since Jun 2025)*
*   Kuala Terengganu
*   Kuantan *(since Dec 2025)*
*   Melaka *(since May 2024)*
*   Seremban

### Excluded Networks

Please note that the following BAS.MY networks are **not** included in the current dataset yet, but may be added in the future statistic counts:

*   Kuching
*   Kota Kinabalu

## JSON Schema

The data in the JSON files follows a consistent schema, detailed below:

```json
{
  "last_updated": "YYYY-MM-DD",
  "source": "Agensi Pengangkutan Awam Darat (APAD)",
  "statistic_type": "total_passengers" | "average_daily_passengers",
  "data": {
    "yearly": [
      {
        "year": 2019,
        "locations": {
          "Ipoh": 1955306,
          "Kangar": 349562
          // ... other locations; missing/not-yet-operational cities use null
        },
        "total": 5386684
      },
      {
        "year": "2026*",
        "locations": {
          "Ipoh": 657901,
          "Kangar": 92821
          // ... other locations
        },
        "total": 10779719
      }
    ],
    "monthly_YYYY": [
      {
        "month": "Jan-YY",
        "locations": {
          "Ipoh": 60449
          // ... other locations
        },
        "total": 869485
      }
    ]
  }
}
```

> **Note:** `year` is `number | string` — partial/in-progress years are suffixed with `*` (e.g. `"2026*"`). `locations` values are `number | null` (null when the network was not yet operating or not reported for that period).

## Acknowledgements

The data presented in this project is sourced from the official infographics and statistics published by the **Agensi Pengangkutan Awam Darat (APAD)**. The original source material can be found on their official website:

*   [APAD - Info Grafik & Statistik](https://www.apad.gov.my/index.php/sumber-maklumat1/info-grafik-statistik#section-id-1604565158282)

We extend our gratitude to APAD for making this data publicly available.

## License

This project is licensed under the MIT License. See the [`LICENSE`](LICENSE) file for details.