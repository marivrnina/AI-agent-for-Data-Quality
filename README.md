# AI-Powered Data Quality Agent

An automated data quality tool that scans a dataset, identifies issues, and generates a scored, visual report using the Anthropic API.

## Overview
This project analyzes a fintech transactions dataset for common data quality problems — missing values, duplicates, inconsistent formats, and type mismatches — then uses Claude to help interpret and explain the issues found. The output is a self-contained, interactive HTML dashboard showing a quality score, column-by-column breakdown, and prioritized cleaning actions.

## Data
- Source: fintech_transactions_messy.csv (transaction-level fintech data)
- Size: 355 rows, 13 columns
- Notes: dataset was intentionally messy — includes missing values, inconsistent currencies/formats, and flagged transactions, used to test the quality-checking pipeline

## Tools and technologies
- Python (pandas)
- Anthropic API (Claude) — used to interpret data quality issues in plain language
- HTML/CSS/JS — for the generated interactive report

## Methodology
1. Load the dataset and profile it: shape, column types, missing values per column
2. Query Claude for context on common data quality issues relevant to fintech data
3. Score each column for severity (critical, moderate, minor, passed) based on missing data and inconsistencies
4. Generate visual summaries (charts, distribution breakdowns) of the issues found
5. Compile everything into a single interactive HTML dashboard with a column-level drill-down and a prioritized action list

## Results
The tool outputs `data_quality_dashboard.html` — an interactive report showing:
- An overall data quality score
- Duplicate row and missing value counts
- A column-by-column severity breakdown
- A ranked list of priority cleaning actions with suggested code snippets

## How to run this project
1. Clone the repository: `git clone [url]`
2. Install dependencies: `pip install anthropic pandas`
3. Set your Anthropic API key as an environment variable (do not hardcode it):
   `export ANTHROPIC_API_KEY="your-key-here"`
4. Run the notebook: `Data_quality_agent.ipynb`
5. Open the generated `data_quality_dashboard.html` in a browser
