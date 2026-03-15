# Playwright 102 Assessment - TypeScript Version

A separate, independent TypeScript Playwright test automation project for testmu HyperExecute.

## Project Structure

```
playwright-102-typescript/
├── tests/
│   └── scenarios.spec.ts          # 3 test scenarios (TypeScript)
├── playwright.config.ts            # Playwright configuration
├── tsconfig.json                   # TypeScript configuration
├── package.json                    # NPM dependencies
├── hyperexecute.yaml              # testmu HyperExecute config
├── .gitignore                     # Git exclusions
└── README.md                       # This file
```

## Test Scenarios

### 1. Simple Form Demo
- Navigate to testmu Selenium Playground
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
- Use environment variables for test data
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

## Running Tests

### Headless (CI/testmu)
```bash
npm test
```

### Interactive (Headed)
```bash
npm run test:headed
```

### Debug Mode
```bash
npm run test:debug
```

## testmu HyperExecute Execution

### Configuration
- **Framework**: Playwright (JavaScript)
- **Language**: TypeScript (compiled to JavaScript)
- **OS**: Windows (`runson: win`)
- **Parallelism**: 2 threads
- **Node Version**: Latest

### Run on testmu

```powershell
# Download HyperExecute CLI if not already installed
Invoke-WebRequest -Uri "https://downloads.lambdatest.com/hyperexecute/windows/hyperexecute.exe" -OutFile "hyperexecute.exe"

# Execute tests
.\hyperexecute.exe --user your-username --key your-access-key --config hyperexecute.yaml --verbose
```

## Independent Repository

This is a **completely separate project** from the C# version:
- ✅ Separate git repository
- ✅ Independent npm dependencies
- ✅ No shared configuration
- ✅ Can be cloned/deployed independently

## Resources

- [Playwright TypeScript Guide](https://playwright.dev/docs/intro)
- [HyperExecute Documentation](https://www.lambdatest.com/support/docs/hyperexecute-cli/)
- [Node.js Documentation](https://nodejs.org/docs/)
