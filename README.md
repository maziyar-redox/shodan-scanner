# Shodan Scanner

A Python script to query Shodan.io for IP addresses and ports matching specific search criteria.

## Features

- Query Shodan.io with custom search terms
- Control the number of result pages to fetch
- Save results to a text file
- Shows estimated query cost before execution

## Requirements

- Python 3.x
- Shodan Python library (`shodan`)
- A valid Shodan.io API key

## Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/shodan-scanner.git
cd shodan-scanner
```

2. Clone this repository:
```bash
pip install -r requirements.txt
```

## Usage
```bash
usage: shodan_scanner.py [-h] -s SEARCH -o OUTPUT -p PAGES

optional arguments:
-h, --help            show this help message and exit
-s SEARCH, --search SEARCH
						search query (default: tornado)
-o OUTPUT, --output OUTPUT
						output filename (default: out.txt)
-p PAGES, --pages PAGES
						Page size (default: 1)
```

### Example
```bash
python3 src/shodan_scanner.py -s "apache" -o results.txt -p 2
```

This will:

- Search Shodan for "apache"

- Fetch 2 pages of results (approximately 200 results)

- Save the IP addresses and ports to results.txt

## Output format
The script outputs results in the format:

```bash
IP_ADDRESS:PORT
```

Example:
```bash
45.33.12.156:80
23.239.11.30:443
```

## Notes

- Shodan API calls are throttled to 1 request per second

- Each page of results costs 1 Shodan Query Credit

- The script will prompt for confirmation before executing queries that cost credits

## License

[MIT License]("https://choosealicense.com/licenses/mit/")

