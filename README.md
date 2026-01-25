PlayWright UI and API Automation Framework
<img src="https://github.com/your-org/PlayWright-UI-Automation/actions/workflows/playwright.yml/badge.svg" alt="Playwright Tests">

<img src="https://img.shields.io/badge/License-ISC-blue.svg" alt="License">

A robust, enterprise-grade automation framework built with Playwright for end-to-end testing of UI and API components. Designed for scalability, maintainability, and CI/CD integration, this framework supports cross-browser testing, API authentication, and comprehensive reporting.

Table of Contents
Features
Prerequisites
Installation
Configuration
Usage
Project Structure
Testing
CI/CD
Contributing
Troubleshooting
License
Features
UI Automation: Page Object Model (POM) for maintainable UI tests with Playwright.
API Automation: OAuth2 client credentials flow with token management and storage.
Cross-Browser Support: Tests run on Chromium, Firefox, and WebKit.
Environment Management: Multi-environment support (DEV, SIT, UAT) with dotenv.
Logging & Reporting: Centralized logging utility and HTML/test reports.
Code Quality: ESLint, Prettier, and Husky for consistent code standards.
Containerization: Docker support for isolated test execution.
Parallel Execution: Optimized for CI with retries and parallel workers.
Enterprise Practices: Input validation, error handling, retries, and comprehensive documentation.
Prerequisites
Node.js: Version 18.x or higher (LTS recommended).
npm: Version 8.x or higher.
Git: For cloning the repository.
Docker (optional): For containerized execution.
Environment Variables: Access to API credentials (e.g., CLIENT_ID, CLIENT_SECRET).
Installation
Clone the Repository:

Install Dependencies:

Install Playwright Browsers:

Set Up Environment:

Copy and configure environment files in environments (e.g., DEV.env).
Ensure required variables like API_BASE_URL, CLIENT_ID, CLIENT_SECRET are set.
Verify Setup:

Configuration
Environment Files
Located in environments.
Supported environments: DEV.env, SIT.env, UAT.env.
Set NODE_ENV to switch (e.g., NODE_ENV=SIT npm test).
Playwright Config
Main config: playwright.config.ts.
Key settings:
Test directory: tests
Timeouts: 50s for tests, 10s for assertions.
Retries: 2 on CI.
Reporters: List and HTML.
Projects: Chromium, Firefox, WebKit.
API Authentication
OAuth2 setup in oauth.setup.ts.
Tokens stored in user.json for reuse.
Usage
Running Tests
All Tests:
Specific Test File:
With Environment:
Headed Mode (for debugging):
Generate Report:
API Tests
Located in api.
Example: paypal.spec.ts.
UI Tests
Located in ui.
Example: user.validations.spec.ts.
Uses fixtures in app.fixtures.ts for setup/teardown.
Docker Execution
Project Structure
Testing
Unit Tests: Add tests for utilities (e.g., Logger) using Jest or similar.
Integration Tests: Ensure API and UI components interact correctly.
Flakiness Handling: Use retries, waits, and assertions for stability.
Data Management: Use dynamic data generation to avoid conflicts.
CI/CD
GitHub Actions: Workflow in playwright.yml runs tests on push/PR.
Pre-commit Hooks: Husky ensures linting and formatting via .lintstagedrc.
Parallelism: Configured for efficient CI execution.
Artifacts: Upload reports and traces on failure.
Contributing
Fork the repository.
Create a feature branch: git checkout -b feature/your-feature.
Follow code standards: Run npm run lint:fix before committing.
Add tests for new features.
Submit a PR with a clear description.
Code Standards
Linting: ESLint with TypeScript and Prettier.
Commits: Conventional commits (enforced by Husky).
Reviews: All PRs require review.
Troubleshooting
Test Failures: Check index.html for traces and screenshots.
Environment Issues: Verify .env files and NODE_ENV.
Browser Issues: Reinstall browsers with npx playwright install --force.
API Errors: Check user.json and token validity.
Performance: Reduce workers or increase timeouts if needed.
For more help, open an issue or check the Playwright Docs.

License
This project is licensed under the ISC License. See LICENSE for details.
