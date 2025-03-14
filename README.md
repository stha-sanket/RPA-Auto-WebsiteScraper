# eBay Laptop Scraper

## Description

This Robocorp script scrapes laptop listings from eBay, extracting the product name, price, and product link, and saves the data into a CSV file.

## Prerequisites

*   **Python 3.7+**
*   **Robocorp Framework**: `get via extension`
*   **Required Libraries**:
    *   `rpaframework`
    *   `rpaframework-browser`
    *   `lxml`
*   Install these libraries using `pip install lxml` other libraries will be included in the extension

## Setup and Installation Extension
![Requirement Extension](https://github.com/stha-sanket/RPA-Auto-WebsiteScraper/blob/main/requirement-extension.png?raw=true)
Download these extention on vs-code

## Usage

1.  **Run the Robot:**

    After downloading the extension you can see a Run Task above `@task` decorator

## Code Explanation

*   **Robocorp Framework:** Provides the structure for defining and running tasks.
*   **Browser Library:** Controls the web browser (Chromium) for navigating the eBay website and extracting data.
*   **`lxml`:** Parses the HTML content of the eBay page to efficiently extract data using XPath expressions.
*   **CSV Library (built-in):** Used to write the scraped data to a CSV file.

## Task Breakdown

*   `robot_spare_bin_python()`: The main task function that orchestrates the entire scraping process.
    *   Configures browser settings (slow motion for easier debugging).
    *   Opens the CSV file for writing.
    *   Calls the `scrape_ebay_laptops` function to perform the scraping.
*   `scrape_ebay_laptops(url, writer)`: Scrapes laptop information from the given eBay URL.
    *   Navigates to the specified URL.
    *   Gets the page content.
    *   Uses `lxml` to parse the HTML content and extract data using XPath expressions.
    *   Iterates through each product listing, extracting the title, price, and link.
    *   Writes the extracted data to the CSV file.

## Output

The script produces the following output file:

*   `ebay_laptops.csv`: A CSV file containing the scraped laptop data, including the product name, price, and link.  It will overwrite the file if it exists.
