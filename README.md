# Pokémon API Automation Project

This project demonstrates shell scripting for API automation, data extraction, error handling, and parallel processing using the [PokéAPI](https://pokeapi.co/).

## Tasks Overview

### 0. Fetch Data for a Single Pokémon
- **Script:** `apiAutomation-0x00`
- Fetches data for Pikachu from the PokéAPI and saves it to `data.json`.
- Logs errors to `errors.txt` if the request fails.

### 1. Extract and Format Pokémon Data
- **Script:** `data_extraction_automation-0x01`
- Extracts name, height, weight, and type from `data.json` using `jq`, `awk`, and `sed`.
- Outputs a human-readable summary.

### 2. Fetch Data for Multiple Pokémon
- **Script:** `batchProcessing-0x02`
- Loops through a list of Pokémon, fetches their data, and saves each to `pokemon_data/<name>.json`.
- Implements retry logic and logs failures to `fetch_errors.log`.

### 3. Generate a CSV Report
- **Script:** `summaryData-0x03`
- Reads all JSON files in `pokemon_data/`, extracts name, height, and weight, and writes them to `pokemon_report.csv`.
- Calculates and displays average height and weight using `awk`.

### 4. Parallel Data Fetching
- **Script:** `batchProcessing-0x04`
- Fetches data for multiple Pokémon in parallel using background processes.
- Waits for all fetches to complete before finishing.

## Requirements

- `bash`
- `curl`
- `jq`
- `awk`
- `sed`

Install dependencies on Ubuntu:
```sh
sudo apt-get update
sudo apt-get install dos2unix
sudo apt-get install curl jq
```

## Usage

Make scripts executable:
```sh
dos2unix <script_name>
chmod +x <script_name>
```

Run a script:
```sh
./<script_name>
```

## Directory Structure

```
Advanced_shell/
├── apiAutomation-0x00
├── data_extraction_automation-0x01
├── batchProcessing-0x02
├── summaryData-0x03
├── batchProcessing-0x04
├── pokemon_data/
├── pokemon_data_parallel/
├── pokemon_report.csv
└── fetch_errors.log
```

## Notes

- Ensure you have an active internet connection for API requests.
- Handle API rate limits by adjusting sleep intervals if needed.
