# Arbitrage_Bettor

A Python script designed to identify sports betting arbitrage opportunities using real-time odds data fetched from The Odds API (v4).

## Description

This project fetches upcoming sports event odds from multiple bookmakers via The Odds API. It then analyzes this data to find arbitrage situations – scenarios where betting on all possible outcomes across different bookmakers guarantees a small, risk-free profit, regardless of the event's result. The script calculates the optimal bet amounts for identified opportunities and outputs the results into a formatted Excel spreadsheet.

## Features

* Fetches odds data from The Odds API (v4).
* Compares odds across different bookmakers for specified markets (default: H2H).
* Identifies potential arbitrage opportunities.
* Calculates required bet amounts for each outcome to capitalize on the arbitrage.
* Outputs results to a formatted Excel file (`upcoming_events_bets.xlsx`) for easy review.

## Configuration

1.  **API Key:** You need to first obtain an API key from [The Odds API](https://the-odds-api.com).
2.  **Set API Key:** Open the script and locate the following line near the top:
    ```python
    API_KEY = 'YOUR_API_KEY_HERE'
    ```
    Replace `'YOUR_API_KEY_HERE'` with your actual API key.
3. **Google Drive:** This notebook automatically saves a file of upcoming in your drive assuming you give it permission when it runs. You can remove the two lines that do this in the third block of code. Note that regardless of this decision, this notebook will save a file of upcoming bets locally as a .xlsx file and update every time you run the notebook.
4.  **Parameters (Optional):** You can adjust variables like `SPORT`, `REGIONS`, `MARKETS`, and `BET_SIZE` near the top of the script to change the scope of the search.

## Usage

1.  Ensure you have configured your API key in the script.
2.  Run the Python script or execute the cells in the Jupyter Notebook.
    ```bash
    python your_script_name.py
    ```
    (Or run the notebook cells sequentially)
3.  The script will:
    * Request data from the API.
    * Process the events to find arbitrage opportunities.
    * If opportunities are found, create `bets.xlsx` (raw data) and `upcoming_events_bets.xlsx` (formatted output).
    * Print status messages to the console.

## Output

* **`bets.xlsx`**: An Excel file containing the raw pandas DataFrame of the identified arbitrage opportunities before formatting.
* **`upcoming_events_bets.xlsx`**: The final, formatted Excel file. This sheet is styled with colors, borders, and specific number formats to highlight the arbitrage details, including the event, expected profit, and the specific odds and bet amounts required for each outcome.
