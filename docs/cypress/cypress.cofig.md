# **Cypress Configuration (`cypress.config.js`) – Complete Guide**

Cypress uses a configuration file (`cypress.config.js` or `cypress.config.ts`) to control test execution, set global defaults, and customize behavior. Below is an **extensive, in-depth guide** covering **all possible options** with examples.

---

## **📌 Basic Cypress Config Structure**
A typical `cypress.config.js` file looks like this:

```javascript
const { defineConfig } = require("cypress");

module.exports = defineConfig({
  e2e: {
    baseUrl: "http://localhost:3000",
    specPattern: "cypress/e2e/**/*.cy.{js,jsx,ts,tsx}",
    supportFile: "cypress/support/e2e.js",
    fixturesFolder: "cypress/fixtures",
    downloadsFolder: "cypress/downloads",
    screenshotsFolder: "cypress/screenshots",
    videosFolder: "cypress/videos",
    video: true,
    screenshotOnRunFailure: true,
    retries: 2,
    defaultCommandTimeout: 6000,
    pageLoadTimeout: 60000,
    viewportWidth: 1280,
    viewportHeight: 720,
    chromeWebSecurity: false,
    env: {
      API_URL: "https://api.example.com",
    },
    setupNodeEvents(on, config) {
      // Custom event listeners
      return config;
    },
  },
});
```

---

## **📌 Configuration Options Breakdown**

### **🔹 1. General Configuration**
| Option                     | Description | Default |
|----------------------------|-------------|---------|
| `baseUrl`                  | Default URL for `cy.visit()` | `null` |
| `viewportWidth`            | Default browser viewport width | `1000` |
| `viewportHeight`           | Default browser viewport height | `660` |
| `defaultCommandTimeout`    | Timeout for Cypress commands (in ms) | `4000` |
| `pageLoadTimeout`          | Timeout for full page load (in ms) | `60000` |
| `waitForAnimations`        | Whether Cypress should wait for animations to finish before interacting | `true` |
| `chromeWebSecurity`        | Enable or disable Chrome security features (CORS, same-origin policy) | `true` |
| `screenshotOnRunFailure`   | Take screenshots when a test fails | `true` |
| `video`                   | Enable or disable video recording | `true` |
| `videoCompression`         | Compression level for recorded test videos (0-51, lower is better quality) | `32` |

### **Example:**
```javascript
e2e: {
  baseUrl: "http://localhost:8080",
  viewportWidth: 1440,
  viewportHeight: 900,
  defaultCommandTimeout: 8000,
  pageLoadTimeout: 100000,
}
```

---

### **🔹 2. File Structure & Path Configuration**
| Option             | Description | Default |
|--------------------|-------------|---------|
| `specPattern`     | File pattern for test files | `"cypress/e2e/**/*.cy.{js,ts}"` |
| `supportFile`     | Path to Cypress support file | `"cypress/support/e2e.js"` |
| `fixturesFolder`  | Folder containing fixture data | `"cypress/fixtures"` |
| `downloadsFolder` | Folder where downloaded files are stored | `"cypress/downloads"` |
| `screenshotsFolder` | Folder for test failure screenshots | `"cypress/screenshots"` |
| `videosFolder` | Folder for recorded videos | `"cypress/videos"` |

### **Example:**
```javascript
e2e: {
  supportFile: "cypress/support/index.js",
  specPattern: "cypress/integration/tests/**/*.cy.js",
  fixturesFolder: "cypress/mock-data",
}
```

---

### **🔹 3. Test Execution & Retry Configurations**
| Option           | Description | Default |
|-----------------|-------------|---------|
| `retries`       | Number of times a failed test is retried | `0` |
| `numTestsKeptInMemory` | Max tests stored in memory at a time | `50` |
| `scrollBehavior` | How Cypress scrolls elements into view (`center`, `top`, `bottom`, `nearest`) | `"top"` |

**Example for Retry Logic:**
```javascript
e2e: {
  retries: {
    runMode: 3,   // Retries failed tests 3 times when running `cypress run`
    openMode: 1,  // Retries once when using `cypress open`
  }
}
```

---

### **🔹 4. Browser & Security Configurations**
| Option                 | Description | Default |
|------------------------|-------------|---------|
| `chromeWebSecurity`    | Disable Chrome's same-origin policy (useful for handling CORS issues) | `true` |
| `modifyObstructiveCode` | Cypress removes certain JavaScript security features on pages | `true` |
| `experimentalSessionSupport` | Keep session state between tests | `false` |

**Example:**
```javascript
e2e: {
  chromeWebSecurity: false, // Bypass CORS issues
  modifyObstructiveCode: false, // Disable Cypress modifying JS code
}
```

---

### **🔹 5. Environment Variables (`env`)**
Cypress allows defining **custom environment variables**.

**Configuration:**
```javascript
env: {
  API_URL: "https://api.example.com",
  USERNAME: "test_user",
  PASSWORD: "securepassword",
}
```

**Accessing in Tests:**
```javascript
cy.request(Cypress.env("API_URL") + "/login", {
  username: Cypress.env("USERNAME"),
  password: Cypress.env("PASSWORD"),
});
```

---

### **🔹 6. Node Event Listeners (`setupNodeEvents`)**
Cypress allows listening to events like **test failures**, **request interceptions**, and **browser launches**.

**Example:**
```javascript
setupNodeEvents(on, config) {
  on("before:browser:launch", (browser, launchOptions) => {
    if (browser.name === "chrome") {
      launchOptions.args.push("--disable-gpu");
    }
    return launchOptions;
  });

  on("task", {
    log(message) {
      console.log(message);
      return null;
    },
  });

  return config;
}
```

---

## **📌 Example Configuration for Different Use Cases**
### **🔹 API Testing Configuration**
```javascript
module.exports = {
  e2e: {
    baseUrl: "https://api.example.com",
    requestTimeout: 10000,
    defaultCommandTimeout: 8000,
    supportFile: false, // No UI-based test support needed
  },
};
```

---

### **🔹 Running Tests in CI/CD (GitHub Actions, Jenkins, etc.)**
```javascript
module.exports = defineConfig({
  e2e: {
    baseUrl: "http://localhost:4000",
    video: false, // Disable videos to save CI storage
    retries: {
      runMode: 3,
      openMode: 1,
    },
    setupNodeEvents(on, config) {
      on("task", {
        log(message) {
          console.log(message);
          return null;
        },
      });
    },
  },
});
```

**Run tests in CI:**
```sh
npx cypress run --browser chrome --headless
```

---

## **📌 Overriding Config Options at Runtime**
Cypress allows **overriding configuration options** using CLI flags:

```sh
npx cypress run --config baseUrl="https://staging.example.com"
```

Example for running a **single test file**:
```sh
npx cypress run --spec "cypress/e2e/login.cy.js"
```

---

## **📌 Final Thoughts**
This guide covers **all Cypress configuration options** in depth. You can customize `cypress.config.js` based on your needs, whether for UI testing, API testing, or CI/CD execution.

Would you like help with a **specific** setup for your project? 🚀