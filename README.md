# IADB (IDB) Job Scraper

A Python script that extracts current job opportunities from the Inter-American Development Bank (IADB/IDB) careers website and generates an RSS feed.

## Features

✓ Scrapes job listings from IADB careers website
✓ Extracts job title, location, and posting date (when available)
✓ Handles JavaScript-rendered content with Selenium
✓ Saves data in RSS 2.0 format as `iadb_jobs.xml`
✓ Removes duplicate listings

## Prerequisites

- Python 3.7 or higher
- Google Chrome Browser

## Installation

1. Navigate to the project directory:
```bash
cd iadb-scraper
```

2. Install required packages:
```bash
py -m pip install -r requirements.txt
```

## Usage

Run the scraper:

```bash
py iadb_scraper.py
```

The script will:
1. Launch Chrome in headless mode
2. Load the IADB jobs page and wait for JavaScript rendering
3. Extract job information
4. Remove duplicates
5. Generate `iadb_jobs.xml` RSS feed

## Output

The RSS feed `iadb_jobs.xml` contains:

- **Job Title** - Full position title
- **Link** - URL to detailed job description
- **Location** - Job location
- **Posting Date** - When the job was posted (if available)

## Technical Details

### Architecture

- **Selenium WebDriver**: Renders JavaScript content
- **BeautifulSoup**: Parses HTML structure
- **ChromeDriver**: Automatically managed by webdriver-manager

### Platform

IADB uses the SAP SuccessFactors platform, which requires JavaScript rendering to load job listings dynamically.

## Notes

- The script uses Chrome in headless mode (runs invisibly)
- First run will automatically download ChromeDriver
- Wait time: 7 seconds for initial page load + dynamic content rendering

## Source

**IADB Jobs Website:** https://jobs.iadb.org/

## License

This script is for informational purposes only. Please respect IADB's terms of service.
