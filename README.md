# Company Shares Outstanding Dashboard

This is a single-file responsive HTML application built with Tailwind CSS that displays the maximum and minimum shares outstanding for a given company, based on data from the SEC EDGAR API.

## Features

*   Displays the entity name, maximum shares outstanding, and minimum shares outstanding.
*   Data is filtered for fiscal years after 2020.
*   Responsive design using Tailwind CSS.
*   Dynamically loads data for different companies based on a CIK provided in the URL.

## How to Use

1.  **Open `index.html` in your web browser.**
    *   By default, it will display data for **Bristol Myers Squibb (CIK 0000014272)**.

2.  **View Data for a Different Company:**
    *   Append `?CIK=<YOUR_CIK_NUMBER>` to the URL in your browser's address bar.
    *   **Example:** `file:///path/to/your/index.html?CIK=0001018724` (for Apple Inc.)
    *   The page will automatically fetch and update the data without a full page reload.

## Data Source

The application fetches data directly from the [SEC EDGAR API](https://www.sec.gov/developer).
Specifically, it queries the `EntityCommonStockSharesOutstanding` concept for the specified CIK.

**Important Note on CORS and Proxies:**
When fetching data from `data.sec.gov` for a CIK other than the default from a client-side browser, you might encounter Cross-Origin Resource Sharing (CORS) issues. For local development or production environments, you may need to:
*   **Set up a simple CORS proxy:** A small backend service that fetches data from `data.sec.gov` and serves it to your `index.html`.
*   **Use a service like AIPipe:** If you have an AIPipe account or similar, you could route your requests through their service on the backend.
*   **Browser extensions:** While not recommended for production, browser extensions can disable CORS for testing.

## Technologies Used

*   **HTML5:** Structure of the web page.
*   **Tailwind CSS:** For styling and responsive design.
*   **JavaScript (ES6+):** For fetching data, processing, and updating the UI.

## Local Development

No specific build steps are required. Simply open `index.html` in your browser.

## Contributing

Feel free to fork this repository, open issues, or submit pull requests.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
