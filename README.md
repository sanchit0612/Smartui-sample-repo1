# SmartUI Storybook Sample (TypeScript)

This project demonstrates how to use LambdaTest SmartUI for visual regression testing with a React + Storybook project written in TypeScript.

---

## Prerequisites
- **Node.js**: Version 14.15.0 or higher
- **npm**: Version 6 or higher
- **Storybook**: Version 6.4.0 or higher (already set up in this project)
- **LambdaTest SmartUI account**: [Sign up here](https://accounts.lambdatest.com/register) if you don't have one

---

## Step-by-Step Guide

### 1. Clone the Repository
Clone this project or copy the codebase to your local machine.

```

cd smartui-storybook-sample
```

### 2. Install Dependencies
Install all required npm packages for React, Storybook, TypeScript, and SmartUI:

```
npm install
```

### 3. Install SmartUI Storybook CLI (Globally)
Install the LambdaTest SmartUI CLI globally so you can run visual regression tests:

```
npm install -g @lambdatest/smartui-storybook
```

### 4. Enable Storybook Feature Flag
Make sure your `.storybook/main.js` contains the following to enable stories JSON (required by SmartUI):

```js
module.exports = {
  features: {
    buildStoriesJson: true,
  },
};
```

### 5. Set Your LambdaTest SmartUI Project Token (Windows CMD)
Set your project token in your terminal session. Use the token provided for your project:

```
set PROJECT_TOKEN=***************************************************8
```

> **Note:** You must run this command in the same terminal session where you will run SmartUI commands.

### 6. Create SmartUI Config File
Generate a `.smartui.json` config file (if you don't have one):

```
smartui config create .smartui.json
```

Edit `.smartui.json` as needed. Example:
```json
{
  "storybook": {
    "browsers": ["chrome", "firefox", "safari", "edge"],
    "viewports": [[1920, 1080]],
    "waitForTimeout": 0,
    "include": [],
    "exclude": []
  }
}
```

You can add custom viewports and story-level settings as described in the LambdaTest documentation.

### 7. Build Storybook Static Site
Create a static build of your Storybook stories:

```
npm run build-storybook
```
- This will generate a `storybook-static` directory with all your stories as static HTML/JS.

### 8. Run SmartUI Visual Regression Tests
Run the SmartUI CLI to upload your static Storybook build for visual testing:

```
smartui storybook ./storybook-static --config .smartui.json
```
- This will capture all your stories and run them on LambdaTest SmartUI for visual regression.

---

## Command Explanations

- **npm install**: Installs all project dependencies.
- **npm install -g @lambdatest/smartui-storybook**: Installs the SmartUI CLI globally so you can use the `smartui` command.
- **set PROJECT_TOKEN=...**: Sets your LambdaTest project token for authentication (required for SmartUI CLI).
- **smartui config create .smartui.json**: Generates a default SmartUI config file for your project.
- **npm run build-storybook**: Builds a static version of your Storybook stories in the `storybook-static` directory.
- **smartui storybook ./storybook-static --config .smartui.json**: Uploads your static Storybook build to LambdaTest SmartUI for visual regression testing.

---

## Troubleshooting
- Ensure your Node.js and npm versions meet the prerequisites.
- If you see errors about missing `index.html` in `storybook-static`, make sure you ran `npm run build-storybook` successfully.
- If you see authentication errors, double-check your `PROJECT_TOKEN` value and that it is set in your terminal session.
- For more configuration options, see the [LambdaTest SmartUI documentation](https://www.lambdatest.com/support/docs/smart-ui-visual-testing/).

---


IN CASE OF BELOW ERROR

D:\downloads\storybook\smartui-storybook-sample>smartui storybook ./storybook-static --config .smartui.json
SmartUI Storybook CLI v1.1.23


[smartui] Project Token Validated
[smartui] Build with commit '84b0dc8' on branch 'master' already exists.
[smartui] Use option --force-rebuild to forcefully push a new build.


use this flag  --> 

 --force-rebuild

**Happy visual testing with LambdaTest SmartUI!** 