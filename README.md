# D-Money API Integration Testing

This project contains a Postman collection for testing D-Money API workflows. The collection covers both successful and invalid-input scenarios, and Newman can run it from the command line and create an HTML test report.

## Quick Start: How to Run

1. Start the D-Money API. By default, the collection expects it at `http://localhost:5000/`.
2. Open PowerShell in the project folder and run:

   ```powershell
   npm install
   node report.js
   ```

3. Open `Reports/report.html` in a browser to view the generated test report.

For detailed setup and Postman instructions, see [How to Run](#how-to-run).

## What is D-Money?

D-Money is a digital financial service for managing accounts and carrying out financial transactions.
The API workflows tested here include user registration and authentication, account operations, deposits, transfers, cashouts, and merchant payments.

## Technology Used

- **Postman** — create, inspect, and manually run API requests and their tests.
- **Postman Collection** — organize the integration scenarios by workflow, including positive and negative test cases.
- **Newman** — run the Postman collection from the command line or a Node.js script.
- **newman-reporter-htmlextra** — generate a detailed, browser-readable HTML test report.
- **Node.js and npm** — install project dependencies and run the Newman script.

## What the Collection Tests

The collection is named **D-Money Api-Integration Testing** and includes scenarios for:

- User registration for customers, agents, and merchants, including invalid registration data.
- Admin login, account activation, and user search.
- Customer, agent, and system-account authentication, including invalid credentials and OTP verification.
- System and agent deposits.
- Customer-to-customer transfers.
- Customer cashouts and merchant payments.
- Related validation scenarios such as zero, negative, or excessive amounts, insufficient balances, and invalid recipients.

Some scenarios depend on accounts, tokens, or balances created or updated by earlier requests. Run the full collection in its intended order, and use a test environment with disposable test data.

## Prerequisites

- Node.js and npm installed.
- The D-Money API running and reachable from the machine that runs the tests.
- Test accounts and data configured as required by the collection.

The collection's default `BaseUrl` is `http://localhost:5000/`. Start the API on that address before running the collection. If the API uses a different address, update the `BaseUrl` collection variable in Postman and save/export the collection so the Newman script uses the correct URL.

## How to Run

### Run the collection with Newman and create the HTML report

1. Open a terminal in the project folder:

   ```powershell
   cd "C:\Users\kawse\OneDrive\Desktop\SQA\D-Money Api-Integration Testing"
   ```

2. Install the project dependencies:

   ```powershell
   npm install
   ```

   This installs Newman and the `htmlextra` reporter declared in `package.json`.

3. Start the D-Money API and confirm that it is available at the collection's `BaseUrl` (`http://localhost:5000/` by default).

4. Run the collection:

   ```powershell
   node report.js
   ```

5. When the run completes, open `Reports/report.html` in a browser to review the results.

The script runs the collection once and exports the HTML report to `Reports/report.html`. A successful run prints `collection run complete!` in the terminal. If the run reports an error, check the API availability, collection URL, test data, and credentials/tokens before trying again.

### Run or inspect requests in Postman

1. Open Postman and import `collection/D-Money_Api-Integration_Testing.json`.
2. Check the `BaseUrl` collection variable and change it if your API is not running on the default address.
3. Ensure the required test accounts and collection variables are configured for your environment.
4. Run the full collection in its existing order, or run individual requests while debugging.

## Project Files

- `collection/D-Money_Api-Integration_Testing.json` — Postman collection and test scenarios.
- `report.js` — Newman runner and HTML report configuration.
- `Reports/report.html` — generated HTML report after running the script.
- `package.json` — Node.js dependencies.

## Notes

- The test cases can create accounts and change balances. Run them only against an authorized test instance, not a production service.
- The generated report is overwritten at `Reports/report.html` on a subsequent run.
- The `npm test` script is currently a placeholder; use `node report.js` to run the collection.

## API Documentation
https://documenter.getpostman.com/view/59281963/2sBYHYuHr8

## D-Money Api-Integration Testing_(Test Cases)
https://docs.google.com/spreadsheets/d/1PswbMmadvYgaZBR4kJS3uZervF1ncsXipi2g_HatpnI/edit?usp=drive_link

## Attachments
<img width="696" height="697" alt="Screenshot 2026-11-07 193917" src="https://github.com/user-attachments/assets/1e83bcee-b725-4a32-b3f9-ed15fff1a43c" />
<img width="697" height="781" alt="Screenshot 2026-11-07 193951" src="https://github.com/user-attachments/assets/0b05ba70-c8ad-41dd-be7c-f76a5e7bcc42" />


