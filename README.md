# Apartment Scraping Project

This project scrapes apartment listings from [house.kg](https://www.house.kg), extracting key details about apartments, such as the number of rooms, area, floor, address, and price (in both USD and KGS). The data is saved in a CSV file for easy analysis and reference.

## Project Overview

This script is designed to:
- Scrape multiple pages of apartment listings.
- Extract key information about each apartment.
- Store the data in a structured format (CSV) for further analysis.

## Installation

### Prerequisites

Ensure you have the following Python packages installed:
- `requests`: For sending HTTP requests to the website.
- `beautifulsoup4`: For parsing HTML content.
- `pandas`: For organizing and saving data in a DataFrame format.

You can install them using pip:
```bash
pip install requests beautifulsoup4 pandas
```

## Usage

To run the script, simply execute it in your Python environment. The script will:
1. Loop through multiple pages of apartment listings (up to 100 pages).
2. Send HTTP requests to each page.
3. Parse and extract relevant apartment information.
4. Save the data into `Apartments.csv`.

### Example

Run the following command:
```bash
python apartment_scraping.py
```

### Output
The output will be saved as `Apartments.csv` with the following columns:
- **Количество комнат**: Number of rooms.
- **Площадь**: Area in square meters.
- **Этаж**: Floor number.
- **Адрес**: Address of the apartment.
- **Цена в usd**: Price in USD.
- **Цена в kgs**: Price in KGS.

## Code Explanation

1. **Request Loop**: Loops over 100 pages of listings, retrieving the HTML content for each page.
2. **Parsing Data**: For each page, the script uses `BeautifulSoup` to find each apartment's information block and extracts:
   - Number of rooms
   - Area
   - Floor level
   - Address
   - Price in USD and KGS
3. **Data Storage**: Data is stored in a Pandas DataFrame, then saved to `Apartments.csv`.

## Notes

- **Rate Limiting**: A 1-second delay is added between requests to avoid overloading the server.
- **Page Limit**: Currently set to scrape 100 pages but can be modified as needed.

