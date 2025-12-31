# Google Scholar Data Collection Tool (2025+)
A Selenium bot that automatically collects article information (title, authors, abstract, link) from Google Scholar while minimizing CAPTCHA risk.
Important: This scraper is specifically designed and optimized for the English interface of Google Scholar (hl=en).
It applies the "Since 2025" filter and "Sort by date" (newest first) directly via URL parameters (as_ylo=2025 and scisbd=1) for maximum stability and reliability — no longer relying on clicking sidebar links that may change.

## Features
- Behaves like a human: Random wait times, scrolling, and clickability checks
- Hides bot traces: User-Agent rotation, disabling AutomationControlled, no-sandbox, etc.
- CAPTCHA detection: Automatically pauses if a CAPTCHA or "unusual traffic" page appears and prompts the user for manual resolution
- Filtering and sorting: Directly loads articles from 2025 and later, sorted by date (newest first) using URL parameters
- Navigation between pages: Automatically scans multiple pages using the "Next" button
- Excel output: Nicely formatted, readable table (adjusted column widths, bold headers, text wrapping enabled)
- Error tolerance: Retries up to 3 times if a button is not found, closes the browser on critical errors

## Usage
1. Install the required libraries:
```bash
pip install selenium webdriver-manager pandas openpyxl
```
2. Edit the following variables in the script:
- QUERY: Your desired search term (e.g., "machine learning ethics")
- MAX_PAGES: Number of result pages to scrape (each page has ~10 articles)
- EXCEL_FILE: Output filename (default: eeg_2025_results.xlsx)

## Run the script:
```bash
python Selenium_GoogleScholarEn_Scraper.py
```

## How It Works (Updated Flow)
- Opens the English Google Scholar homepage
- Directly navigates to a filtered search URL:
- https://scholar.google.com/scholar?hl=en&q=[your-query]&as_ylo=2025&scisbd=1
- This instantly applies both the 2025+ year filter and date sorting without clicking any menu items
- Scrapes articles from the specified number of pages
- Saves formatted results to Excel

## Outputs
- Real-time console progress messages
- A beautifully formatted Excel file containing all collected articles (Order, Title, Authors, Abstract, Link)

## Warnings
- Google frequently updates its anti-bot measures. This tool works reliably as of 2026, but heavy or rapid use may still trigger CAPTCHAs.
- Use responsibly for academic and personal research only. Respect Google's Terms of Service.

## LICENSE
Copyright (c) 2025–2026 Ümmügülsüm Aran
MIT License - See the [LICENSE](LICENSE) file for details.
