# PDF Financial Statement Parser

## Overview

This project provides a collection of Python scripts within Jupyter Notebooks designed to automatically parse and extract transaction data from PDF bank statements. The primary goal is to convert unstructured financial data from various institutions into a structured, machine-readable format like a pandas DataFrame or CSV file. This enables easier data analysis, bookkeeping, and integration with other financial software.

## Features

-   **Multi-Institution Support**: Parsers for statements from several different financial institutions.
-   **Data Extraction**: Accurately extracts key transaction details, including dates, descriptions, debits, credits, and running balances.
-   **Structured Output**: Converts raw PDF text into a clean, organized pandas DataFrame.
-   **Flexible and Adaptable**: The notebooks can be easily modified to handle new statement layouts or to extract additional data fields.

## Project Structure

```
.
├── Financial_Institution_1_Statement_Reader.ipynb
├── Financial_Institution_2_Statement_Reader.ipynb
├── Financial_Institution_3_Statement_Reader.ipynb
├── requirements.txt
└── sample_statements/
    ├── fi_1_statement.pdf
    ├── fi_2_statement.pdf
    └── fi_3_statement.pdf
```

-   **`*.ipynb`**: Jupyter Notebooks, each containing the logic to parse a statement from a specific financial institution.
-   **`requirements.txt`**: A list of all Python dependencies needed to run the notebooks.
-   **`sample_statements/`**: A directory containing example PDF statements that are compatible with the parsers.

## Local Installation and Usage

To run this project on your local machine, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone <your-repository-url>
    cd <repository-folder>
    ```

2.  **Set up a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3.  **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Launch Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```

5.  Open one of the `*_Statement_Reader.ipynb` notebooks and run the cells to see the parser in action. You can modify the `pdf_path` variable to point to your own statement files.

## How to Use with Google Colab

You can easily run these notebooks in the cloud using Google Colab. This is a great option if you don't want to set up a local Python environment.

1.  **Upload Files to Google Drive**:
    -   Create a new folder in your Google Drive (e.g., `FinancialStatementParser`).
    -   Upload the notebook you want to use (e.g., `Financial_Institution_1_Statement_Reader.ipynb`), the `requirements.txt` file, and the sample PDF statements to this folder.

2.  **Open the Notebook in Colab**:
    -   In your Google Drive, navigate to the folder you created.
    -   Right-click the `.ipynb` file and select **Open with > Google Colaboratory**.

3.  **Mount Your Google Drive**:
    -   The first code cell in your notebook should be used to mount your Google Drive. This gives Colab access to your uploaded files.
    ```python
    from google.colab import drive
    drive.mount('/content/drive')
    ```
    -   Run this cell and follow the authentication prompts.

4.  **Install Dependencies**:
    -   Next, install the project's dependencies from your uploaded `requirements.txt` file. Make sure to adjust the path to where you saved the file in your Drive.
    ```bash
    !pip install -r /content/drive/MyDrive/FinancialStatementParser/requirements.txt
    ```

5.  **Update File Paths**:
    -   In the notebook, find the line where the PDF file path is defined. You must update this path to point to the statement's location in your Google Drive.
    -   For example, change:
        `pdf_path = 'sample_statements/fi_1_statement.pdf'`
    -   To:
        `pdf_path = '/content/drive/MyDrive/FinancialStatementParser/sample_statements/fi_1_statement.pdf'`

6.  **Run the Parser**:
    -   Execute all the cells in the notebook sequentially to process the PDF and view the extracted data in a structured DataFrame.

## Potential Customers

This project is valuable for a wide range of users and organizations that need to digitize and process financial documents:

-   **Financial Technology (Fintech) Companies**: Developers of personal finance management (PFM) apps, budgeting tools, or automated bookkeeping platforms can use this as a core component for importing user data from PDF statements.
-   **Lenders and Credit Institutions**: Underwriting and risk assessment teams can automate the analysis of a loan applicant's financial history, verifying income and spending patterns more efficiently.
-   **Accounting and Bookkeeping Firms**: Professionals can significantly reduce manual data entry time and minimize human error when processing client bank statements for tax preparation or financial reporting.
-   **Small Business Owners and Freelancers**: Entrepreneurs can use this tool to easily track expenses, manage cash flow, and prepare financial records without relying on manual spreadsheets.
-   **Data Analysts and Individuals**: Anyone looking to perform a deep-dive analysis on their personal spending habits or create custom financial dashboards can use these scripts to get their data into an analyzable format.

## Contributing

Contributions are welcome! If you would like to add a parser for a new financial institution, improve an existing one, or enhance the project in any way, please feel free to fork the repository and submit a pull request.

## License

This project is open-source. Please see the `LICENSE` file for more details. (Note: You may want to add a license file like MIT or Apache 2.0).