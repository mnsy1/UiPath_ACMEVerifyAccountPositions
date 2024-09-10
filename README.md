# ACME System Automation with UiPath

This UiPath project automates a workflow that interacts with both the ACME System1 website and ACME System3 desktop application. It utilizes three custom libraries to streamline the process of extracting and updating work items from ACME System1 and searching for related data within ACME System3. 

The workflow follows a sequence of operations that includes logging into both systems, extracting work items, gathering detailed account movements, and updating the status of each work item on the ACME System1 website.

## Libraries Used

This project uses the following custom libraries:
1. [**Google Search Library**](https://github.com/mnsy1/UiPath_Google): Handles the process of launching Google Chrome, searching for the ACME System1 website, and navigating to it.
2. [**ACME System1 Website Library**](https://github.com/mnsy1/UiPath_ACMESystem1): Automates interactions with the ACME System1 website (web automation).
3. [**ACME System3 Desktop Application Library**](https://github.com/mnsy1/UiPath_ACMESystem3Application): Automates operations within the ACME System3 desktop application (desktop automation).

## Process Workflow

### 1. Open ACME System1 Website
- Launches Google Chrome and opens the Google search page.
- Types "ACME System" in the search box and clicks the first search result to navigate to the ACME System1 website.

### 2. Login to ACME System1 Account
- Ensures the user is logged out before proceeding.
- Navigates to the login page.
- Logs into the ACME System1 website using the provided email and password.

### 3. Get Work Items
- Navigates to the Work Items page within ACME System1.
- Extracts all work items across multiple pages for processing.

### 4. Launch ACME System3 Desktop Application
- Opens the ACME System3 desktop application.
- Logs into the application using the provided email and password.
- Navigates to the "Search by ID" window in the desktop application.

### 5. Process Each Work Item
For each work item retrieved from ACME System1:
- Navigates to the specific work item page on the ACME System1 website.
- Extracts key information from the work item: User ID, Account Amount, and Account Number.

### 6. Search for Work Item in ACME System3
- In ACME System3, searches for each work item by ID using the "Search by ID" window.
- Opens the client details window.
- Opens the client accounts window.
- Navigates to the account movements window.
- Displays all account movements for the client and extracts the movement details.

### 7. Close Unwanted Windows
- Closes all unnecessary windows in ACME System3 and returns to the "Search by ID" window to prepare for the next search.

### 8. Update Work Item in ACME System1
- After extracting the necessary information from ACME System3, navigates back to the ACME System1 website.
- Opens the update work item page.
- Sets the comment and updates the status of the work item based on the extracted information.
- Closes the update work item page.

### 9. Repeat Process for Remaining Work Items
- The process loops through all remaining work items, repeating steps 5 to 8 for each item.

## Conclusion

This project leverages the power of UiPath automation across both web and desktop platforms to efficiently handle a complex workflow. It automates logging into multiple systems, extracting detailed client data, updating work items, and ensuring that all operations are completed without manual intervention. 

By utilizing the three custom libraries for Google Search, ACME System1, and ACME System3, the project achieves a high degree of automation, saving time and reducing the risk of human error.

## Prerequisites
- UiPath Studio (latest version)
- Installed ACME System3 desktop application
- Google Chrome browser
- Valid ACME System1 and ACME System3 account credentials
