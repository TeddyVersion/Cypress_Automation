Odoo ERP Customization - End-to-End Cypress Automation


This repository contains the end-to-end test automation scripts for Odoo ERP customizations using Cypress. The tests are designed to automate the custom workflows and features of the Odoo system.

Table of Contents
Project Overview
Prerequisites
Setup and Installation
Test Structure
Running the Tests
Writing New Tests
Reporting
Contributing
License

Project Overview

This project automates the testing of custom workflows, modules, and features implemented within an Odoo ERP system. Using Cypress for end-to-end testing, we ensure that critical business processes are validated automatically to catch any regressions or issues in the ERP customizations.

The automation covers:

Custom modules
User interactions with custom forms
Role-based access and permissions
Workflow validations for sales, inventory, accounting, etc.
Prerequisites
To run the Cypress automation suite, you need the following tools installed on your local machine:

Node.js (v14 or later)
Cypress (v10 or later)
Git (for version control)
Odoo instance (either local or cloud-hosted)
Setup and Installation
Clone the repository:

bash
Copy code
git clone https://github.com/TeddyVersion/Cypress_Automation.git
cd Cypress_Automation
Install the dependencies:

bash
Copy code
npm install
Ensure the Odoo instance is running and accessible with the required credentials and environment variables set.

Update the cypress.env.json file to include necessary environment variables like base URL and login credentials:

json
Copy code
{
  "baseUrl": "http://localhost:8069",
  "username": "admin",
  "password": "admin"
}


Test Structure


The tests are organized as follows:

bash
Copy code
Cypress_Automation/
├── cypress/
│   ├── integration/      # Contains the actual test cases
│   │   ├── login.spec.js # Sample test case for login
│   │   ├── sales.spec.js # Sample test case for sales workflow
│   ├── fixtures/         # Test data used in tests
│   ├── plugins/          # Cypress plugins
│   ├── support/          # Custom commands and utilities
│
├── cypress.env.json      # Environment variables for Cypress
├── cypress.json          # Cypress configuration
├── package.json          # Node dependencies and scripts


Key Files:


login.spec.js: Verifies the login functionality for Odoo users.
sales.spec.js: Tests the sales workflow in Odoo, including product listing and order management.
Running the Tests
You can run the Cypress tests using one of the following commands:

To run the tests in the interactive Cypress Test Runner:


bash
Copy code
npx cypress open
To run the tests headlessly:
bash
Copy code
npx cypress run
Running specific tests:
To run a specific test file, use the --spec flag:


bash
Copy code
npx cypress run --spec "cypress/integration/login.spec.js"
Writing New Tests
To write new tests for other custom Odoo workflows:


Create a new .spec.js file under cypress/integration.
Use Cypress commands like cy.visit(), cy.get(), and cy.contains() to interact with the Odoo UI.
Make assertions using cy.should() or cy.expect().
Refer to the official Cypress Documentation for more advanced features and tips.

Reporting
Cypress provides detailed reports for test execution. You can view the results of the test run directly in the terminal or in the interactive test runner.

For CI/CD integrations, refer to the Cypress documentation on recording test results.

Contributing
If you would like to contribute to this project:

Fork the repository.
Create a new feature branch (git checkout -b feature/new-feature).
Make your changes and commit them (git commit -m "Add new feature").
Push your branch (git push origin feature/new-feature).
Submit a pull request.
