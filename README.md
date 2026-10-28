# Playwright TypeScript Test Automation Suite

An end-to-end (E2E) UI test automation framework built with **[Playwright](https://playwright.dev/)** and **[TypeScript](https://www.typescriptlang.org/)**, implementing the **Page Object Model (POM)** design pattern. Tests target the **[SauceDemo (Swag Labs)](https://www.saucedemo.com/)** e-commerce application.

---

##  Key Features

- **Page Object Model (POM):** Clean separation of test specifications, page actions, and locators.
- **Strongly Typed:** Complete TypeScript setup with custom types and enums.
- **Centralized Locators:** Selectors managed in a dedicated JSON registry (`utils/selectors.json`).
- **Data-Driven Testing:** User credentials and test fixtures organized in `data/credentials.json`.
- **Comprehensive Test Coverage:**
  - **Authentication:** Standard, problem, performance-glitch users, and negative validation tests.
  - **Product Sorting:** Price (low-to-high, high-to-low) and Name (A-Z, Z-A) with utility validation algorithms.
  - **Cart Operations:** Adding single and multiple items, verifying cart count badge, navigating to cart, and removing items.
- **Built-in Reporting:** HTML reports, JSON summary output, and automated failure screenshots/video capture.

---

## 📁 Project Structure

```text
├── data/
│   └── credentials.json       # User test data and credentials
├── page/
│   ├── Cart.page.ts           # Cart page actions & locators
│   ├── Login.page.ts          # Login page actions & locators
│   ├── Product.page.ts        # Single product page object
│   └── Products.page.ts       # Products catalog & navigation
├── test/
│   ├── Cart.test.spec.ts      # Shopping cart test suite (@cart)
│   ├── Login.test.spec.ts     # Authentication test suite (@login)
│   └── Sorting.test.spec.ts   # Product sorting test suite (@sorting)
├── utils/
│   ├── enums/
│   │   └── select.enum.ts     # Select dropdown enum definitions
│   ├── selectors.json         # Centralized UI selector definitions
│   └── utility-methods.ts     # Array comparison & sorting verification helpers
├── playwright.config.ts       # Playwright global configuration
├── package.json               # Project dependencies and test scripts
└── tsconfig.json / index.d.ts # TypeScript definitions
```

---

## 🛠️ Prerequisites

- **Node.js**: `v16+` or higher recommended ([Download Node.js](https://nodejs.org/))
- **npm** (included with Node.js)

---

## 🚀 Getting Started

### 1. Install Dependencies

Install project packages:

```bash
npm install
```

### 2. Install Playwright Browsers

Download the required browser binaries (Chromium, Firefox, WebKit):

```bash
npx playwright install
```

---

## 🧪 Running Tests

### Run All Tests
Executes the full test suite across all workers:
```bash
npm run play:test
```

### Run Tests by Feature Tag

- **Login Feature (`@login`):**
  ```bash
  npm run test-l
  ```

- **Sorting Feature (`@sorting`):**
  ```bash
  npm run test-s
  ```

- **Cart Feature (`@cart`):**
  ```bash
  npm run test-c
  ```

### Run Tests in Debug Mode
Opens Playwright Inspector to step through tests:
```bash
npm run play:debug
```

### View Test Execution Report
Opens the interactive HTML report generated from the last run:
```bash
npm run report
```

---

## ⚙️ Configuration

Test configuration is managed in [`playwright.config.ts`](playwright.config.ts):
- **Base URL:** `https://www.saucedemo.com/`
- **Headless Mode:** Set in `use.headless` (toggle `true` or `false`)
- **Artifacts:** Screenshots and video recording on failure/run
- **Reporters:** `dot`, `json` (`jsonReports/jsonReport.json`), and interactive `html`

---

## 📄 License

This project is licensed under the [ISC License](LICENSE).
