# Playwright 102 Assessment - TypeScript

A TypeScript Playwright test automation project running on LambdaTest HyperExecute cloud grid.

## Project Structure

```
playwright-102-typescript/
├── tests/
│   └── scenarios.spec.ts           # 3 test scenarios (TypeScript)
├── playwright.config.ts            # Playwright configuration
├── tsconfig.json                   # TypeScript configuration
├── package.json                    # NPM dependencies
├── hyperexecute.yaml               # HyperExecute config (matrix, secrets, artifacts, caching)
├── .github/
│   └── workflows/
│       └── hyperexecute.yml        # GitHub Actions CI pipeline
├── .gitignore                      # Git exclusions
└── README.md                       # This file
```

## Test Scenarios

### 1. Simple Form Demo
- Navigate to TestMu AI Selenium Playground
- Click "Simple Form Demo"
- Verify URL contains "simple-form-demo"
- Fill message input field
- Submit form
- Validate success message with 4 fallback strategies

### 2. Drag & Drop Sliders
- Navigate to "Drag & Drop Sliders"
- Locate slider elements
- Drag slider to 70% position
- Verify slider moved with 7 detection strategies

### 3. Full Form Submission
- Fill all form fields (name, email, password, company, address, city, state, zip)
- Uses environment variables and secrets for test data
- Submit form
- Validate success message

## Setup

### Prerequisites
- **Node.js** 18+ - [Download](https://nodejs.org/)
- **npm** (comes with Node.js)

### Installation

```bash
npm install
```

## Running Tests Locally

```bash
# Headless (default)
npm test

# Specific browser
npm run test:chromium
npm run test:firefox

# Interactive (headed)
npm run test:headed

# Debug mode
npm run test:debug
```

## HyperExecute Cloud Execution

### Matrix Strategy
Tests run in parallel across **4 browser/OS combinations**:

| OS      | Browser  |
|---------|----------|
| Windows | Chromium |
| Windows | Firefox  |
| Linux   | Chromium |
| Linux   | Firefox  |

### HyperExecute Features Used

| Feature | Description |
|---------|-------------|
| **Artifacts Management** | Collects `playwright-report/` and `test-results/` from all environments into downloadable artifacts on the dashboard |
| **Secret Management** | `TEST_EMAIL` and `TEST_PASSWORD` are stored in the HyperExecute Secrets vault and injected at runtime |
| **Environment Variables** | Non-sensitive config (`TEST_WEBSITE`, `TEST_NAME`, `TEST_COMPANY`, etc.) injected via the `env` block |
| **Pre Steps & Dependency Caching** | `npm install` runs before tests; `node_modules` is cached across runs using `cacheKey` |
| **Post Steps** | Confirmation echo after test execution |
| **GitHub Actions** | CI pipeline triggers HyperExecute on push/PR to main branch |

### Prerequisites for HyperExecute
1. A [LambdaTest](https://www.lambdatest.com/) account
2. Add secrets in the **HyperExecute Dashboard → Secrets Management**:
   - `TEST_EMAIL`
   - `TEST_PASSWORD`

### Run via CLI

```powershell
# Download HyperExecute CLI (Windows)
Invoke-WebRequest -Uri "https://downloads.lambdatest.com/hyperexecute/windows/hyperexecute.exe" -OutFile "hyperexecute.exe"

# Execute tests
.\hyperexecute.exe --user <LT_USERNAME> --key <LT_ACCESS_KEY> --config hyperexecute.yaml
```

### Run via GitHub Actions
1. Add repository secrets in **Settings → Secrets and variables → Actions**:
   - `LT_USERNAME`
   - `LT_ACCESS_KEY`
2. Push to `main`/`master` or open a PR — the workflow triggers automatically.

## Resources

- [Playwright TypeScript Guide](https://playwright.dev/docs/intro)
- [HyperExecute Documentation](https://www.lambdatest.com/support/docs/hyperexecute-cli/)
- [HyperExecute YAML Reference](https://www.lambdatest.com/support/docs/deep-dive-into-hyperexecute-yaml/)
- [HyperExecute Secrets Management](https://www.lambdatest.com/support/docs/hyperexecute-environment-variable-setup/)
- [Node.js Documentation](https://nodejs.org/docs/)
