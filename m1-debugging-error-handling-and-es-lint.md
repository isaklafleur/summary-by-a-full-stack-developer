# Debugging & [ES Lint](https://eslint.org/)

---

Chrome DevTools is a set of authoring, debugging, and profiling tools built into Google Chrome.

## Open [DevTools](https://developers.google.com/web/tools/chrome-devtools/) in Chrome {#open}

* Select **More Tools **&gt; **Developer Tools **from Chrome's Main Menu.
* Right-click a page element and select **Inspect**.
* Press Command + Option + I \(Mac\) or Control + Shift + I \(Windows, Linux\).

## [Device Mode](https://developers.google.com/web/tools/chrome-devtools/device-mode/)![](https://developers.google.com/web/tools/chrome-devtools/device-mode/imgs/device-mode-initial-view.png)

## [Elements panel](https://developers.google.com/web/tools/chrome-devtools/css/)![](/assets/Screen Shot 2017-11-21 at 11.55.17.png)

## [Console panel](https://developers.google.com/web/tools/chrome-devtools/console/)![](https://developers.google.com/web/tools/chrome-devtools/console/images/console-panel.png)

## [Sources panel](https://developers.google.com/web/tools/chrome-devtools/javascript)

![](/assets/Screen Shot 2017-11-21 at 11.57.35.png)

### [Network panel](https://developers.google.com/web/tools/chrome-devtools/network-performance/) {#network}

![](/assets/Screen Shot 2017-11-21 at 12.00.08.png)

---

## ES Lint

ESLint is an open source JavaScript linting utility originally created by Nicholas C. Zakas in June 2013. Code [linting](http://en.wikipedia.org/wiki/Lint_%28software%29) is a type of static analysis that is frequently used to find problematic patterns or code that doesn’t adhere to certain style guidelines. There are code linters for most programming languages, and compilers sometimes incorporate linting into the compilation process.

## Setup ES Lint on Visual Studio Code

1.Install ESLint Extension

![](/assets/Screen Shot 2017-11-21 at 12.05.18.png)

1. Install eslint globally on your machine: `npm install -g eslint`

2. Install eslint localy in your project folder: `npm install eslint --save-dev`

3. Run `eslint --init` in your project folder.

4. Follow the below steps:

![](/assets/Screen Shot 2017-11-21 at 12.12.49.png)

![](/assets/Screen Shot 2017-11-21 at 12.13.00.png)

![](/assets/Screen Shot 2017-11-21 at 12.13.13.png)

![](/assets/Screen Shot 2017-11-21 at 12.13.39.png)

![](/assets/Screen Shot 2017-11-21 at 12.16.48.png)

1. If you followed the steps you should have the above setup.

2. replace the content in the `.eslintrc.json` file with this snippet.

```js
{
  "extends": "standard",
  "env": {
    "browser": true,
    "node": true
  },
  "globals": {
    "google": false,
    "axios": false,
    "document": false,
    "window": false
  },
  "rules": {
    "space-before-function-paren": [
      "error",
      "never"
    ],
    "quotes": [
      "error",
      "double"
    ],
    "semi": [
      2,
      "always"
    ],
    "comma-dangle": [
      "error",
      "never"
    ],
    "space-in-parens": [
      "error",
      "never"
    ],
    "no-console": [
      "error",
      {
        "allow": [
          "warn",
          "error"
        ]
      }
    ],
    "no-var": "error",
    "prefer-const": "error"
  }
}
```

1. Update your Visual Studio Code User Settings `Code -> Preferences -> Settings`. Change `"eslint.autoFixOnSave": false,` to `"eslint.autoFixOnSave": true,`. With this change the javascript files with be updated automatic when you save the file.

For more ES Lint rules, go to [ES Lint Rules section](https://eslint.org/docs/rules/).

