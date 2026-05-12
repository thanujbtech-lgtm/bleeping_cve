# Bleeping Computer CVE Intelligence Collector

Automated CVE scraper from Bleeping Computer RSS feed and articles.

## Overview

Bleeping CVE automatically collects and tracks Common Vulnerabilities and Exposures (CVEs) mentioned in Bleeping Computer articles. The tool runs on a scheduled cron job every hour, parsing RSS feeds and scraping article content to extract CVE identifiers.

## How It Works

1. Fetches latest articles from Bleeping Computer RSS feed
2. Extracts CVE identifiers from article content using regex pattern matching
3. Avoids duplicate entries (same CVE + same date + same link)
4. Stores data in Excel spreadsheet with CVE, date, and article link
5. Runs automatically every hour via cron job

## Setup

### Requirements
- Python 3.x

### Installation

```bash
git clone https://github.com/thanujbtech-lgtm/bleeping_cve.git
cd bleeping_cve
pip install -r requirements.txt
```

### Configure Cron Job

Run the script every hour:

```bash
crontab -e
```

Add this line:

```
0 * * * * cd /path/to/bleeping_cve && python bleeping.py
```

Or use a cron service like [cronjob.org](https://cronjob.org)

## Data Storage

Results are saved in `data.xlsx`:

| CVE | DATE | LINK |
|-----|------|------|
| CVE-2024-XXXXX | 2026-05-12 | https://bleepingcomputer.com/... |

## Technologies

- **cloudscraper** - Bypass Cloudflare protection
- **feedparser** - Parse RSS feeds
- **BeautifulSoup** - Extract CVEs from HTML
- **openpyxl** - Excel file management

## About

Developed by **Kasi Reddy Thanuj Kumar Reddy**
- Security Analyst
- Penetration Tester
- Application Security Specialist

## Contact

📧 [thanuj.kasireddy@gmail.com](mailto:thanuj.kasireddy@gmail.com)

## License

This project is provided as-is for security research and analysis purposes.
