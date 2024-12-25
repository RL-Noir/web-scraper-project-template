![Cover Image](wst_cover.webp)

# Web Scraper Project Template

## Overview

This repository provides a clean and modular template for structuring web scraper projects. It is designed as a starting point to help developers organize their codebase, manage data, and scale their scrapers efficiently.

## Project Structure

```
web_scraper_project/
├── data/
│   ├── raw/                # Raw scraped data
│   ├── cleaned/            # Cleaned or transformed data
├── logs/                   # Logs of scraping activity/errors
├── notebooks/              # Jupyter notebooks for exploratory analysis
├── src/
│   ├── __init__.py         # Recognizes the folder as a Python module
│   ├── parsers/            # Parsing logic organized by data type
│   │   ├── __init__.py     # For parsers module recognition
│   │   ├── html_parser.py  # Functions to parse HTML and extract data
│   │   ├── api_parser.py   # Functions to parse API responses
│   ├── scrapers/           # Contains website-specific scraping modules
│   │   ├── __init__.py     # For scraper module recognition
│   │   ├── website1.py     # Scraper logic for Website 1
│   │   ├── website2.py     # Scraper logic for Website 2
│   ├── config.py           # Configuration for URLs, headers, and settings
│   ├── exceptions.py       # Custom exception classes
│   ├── storage.py          # Functions for saving data (e.g., to CSV, database)
│   ├── utils.py            # Reusable utilities for tasks like handling retries, formatting strings, or managing HTTP requests
├── tests/
│   ├── test_parsers/       # Tests for parsing modules
│   │   ├── test_html_parser.py # Tests for HTML parsing
│   │   ├── test_api_parser.py  # Tests for API parsing
│   ├── test_scrapers/      # Tests for scraper modules
│   │   ├── test_website1.py # Tests for Website 1 scraper
│   │   ├── test_website2.py # Tests for Website 2 scraper
├── .env                    # Environment variables (e.g., API keys)
├── .gitignore              # Specifies files and folders to exclude from version control
├── LICENSE                 # License file for the project
├── main.py                 # Entry point for running the scrapers
├── README.md               # Project overview and instructions
└── requirements.txt        # List of Python dependencies

```

### Key Directories

- **data/**: Stores raw and cleaned data outputs.
- **logs/**: Stores logs of scraping activity and errors.
- **notebooks/**: Jupyter notebooks for exploratory analysis and debugging.
- **src/**: Source code for the scraper logic and helper modules.
  - `parsers/`: Functions for data parsing (HTML, JSON, etc.).
  - `scrapers/`: Website-specific scraping logic.
  - `config.py`: Centralized settings for the scraper.
  - `exceptions.py`: Custom exceptions for error management.
  - `storage.py`: Functions to store data in various formats.
  - `utils.py`: Reusable utilities for tasks like handling retries, formatting strings, or managing HTTP requests.
- **tests/**: Unit tests for validating the scraper and parsing components.

### Notable Files

- **config.py**: Contains URLs, headers, rate limits, and other customizable settings.
- **LICENSE**: Default license file included for the template. Users should review and update this to suit their project's requirements.
- **.env**: Stores sensitive information (e.g., API keys, database URLs) securely. If an `.env` file does not exist, create one based on this example:
  ```env
  API_KEY=your_api_key_here
  DATABASE_URL=your_database_url_here
  ```
- **main.py**: The entry point for running the scraper. Extend this file to customize the scraper's workflow.

## Version Control Best Practices

This template includes a `.gitignore` file configured to:

- Exclude sensitive files like `.env` to protect environment variables.
- Ignore large files and temporary files to keep the repository clean.
- Preserve folder structures (e.g., `data/`, `logs/`) while ignoring their contents.

Review the `.gitignore` file and customize it as needed for your project.

## Usage

### Setup

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```
2. Set up a virtual environment and install dependencies:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```
3. Create an `.env` file for sensitive configurations (e.g., API keys):

   Duplicate `.env.example` and rename it as `.env`

   ```env
   API_KEY=your_api_key_here
   DATABASE_URL=your_database_url_here
   ```

### Running the Scraper

1. Activate the virtual environment:
   ```bash
   source venv/bin/activate
   ```
2. Run the scraper:
   ```bash
   python main.py
   ```

## Data Cleaning Workflows

Data cleaning workflows can either:

1. **Be integrated into the ****`parsers/`**** directory**: This approach is ideal for simpler projects with minimal cleaning requirements, where parsing and cleaning can be handled together for efficiency. For example, you can include functions to clean extracted text or transform data formats directly in the parsing logic.

2. **Be separated into a ****`data_cleaning.py`**** module in the ****`src/`**** directory**: This is recommended for more complex projects requiring reusable and modular cleaning logic. For instance, you might centralize tasks like handling missing data, deduplication, or advanced transformations in a dedicated module for better scalability and maintainability.

Choose the approach that best suits your project's complexity and needs.

## Adaptation

This structure is intended as a flexible template. Feel free to:

- Add or remove modules based on your project's needs.
- Expand the `parsers/` and `scrapers/` directories for new websites or data types.
- Organize the `tests/` directory to match any changes in the source code structure.
- Customize the `README.md` to reflect your specific project's goals, features, and usage instructions.
- Integrate additional tools like Docker or CI/CD pipelines for deployment.
- Install dependencies relevant to your specific project requirements.

## Contributions

We encourage you to fork this template and modify it to suit your needs. Contributions are welcome! Feel free to submit pull requests or open issues for suggestions or improvements.

## License

This template is licensed under the **MIT License**. It is designed as a structural template to organize web scraper projects and does not include functional code or operational scraping logic. When using this template, users should update the license to reflect their specific project's requirements and ensure compliance. For details, see the [LICENSE file](./LICENSE).
