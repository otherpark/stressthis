# Browser/UI monkey & E2E stress

Random/structured interaction to surface UI crashes.

**Reach for this when:** a browser or mobile UI is present.

_11 tools. ⚠️ = copyleft/commercial - install from upstream, never copy its source into your project._

| Tool | What it does | When to use | Install | License |
|---|---|---|---|---|
| [gremlins.js](https://github.com/marmelab/gremlins.js) | The canonical web monkey-testing library. Unleashes a 'horde' of gremlins that click... | Single-page / JS-heavy web app (React/Vue/Angular/Backbone). Triggers unhandled JS exceptions, broken event... | `npm i -D gremlins.js` | `MIT` |
| [Playwright](https://github.com/microsoft/playwright) | Cross-browser (Chromium/Firefox/WebKit) automation and E2E test framework with... | Any modern web app needing reproducible cross-browser stress runs. Use to script long randomized navigation... | `npm i -D @playwright/test` | `Apache-2.0` |
| [Puppeteer](https://github.com/puppeteer/puppeteer) | High-level Node.js library to drive Chrome/Chromium (and Firefox via WebDriver BiDi)... | Chromium-focused web app or service. Use to script headless random-click/random-input monkey loops and... | `npm i puppeteer` | `Apache-2.0` |
| [Cypress](https://github.com/cypress-io/cypress) | In-browser E2E and component test runner with time-travel debugging, automatic waiting,... | Web app already using or willing to adopt a Cypress harness. Use to mix deterministic flows with monkey... | `npm i -D cypress` | `MIT` |
| [Selenium (WebDriver)](https://github.com/SeleniumHQ/selenium) | The long-standing W3C WebDriver browser-automation suite with bindings for many... | Polyglot teams (Java/Python/Ruby/C#/JS) or projects needing the widest browser+OS matrix via Selenium Grid.... | `pip install selenium` | `Apache-2.0` |
| [WebdriverIO](https://github.com/webdriverio/webdriverio) | Next-gen Node.js automation framework over WebDriver, WebDriver BiDi, and Appium for web... | Web or mobile project wanting one framework spanning browser (BiDi) and native apps (via Appium). Use to... | `npm init wdio@latest` | `MIT` |
| [fast-check](https://github.com/dubzzz/fast-check) | Property-based testing framework for JS/TS (QuickCheck-style) with automatic input... | App with a definable command/state model (UI flows, reducers, state machines, component interactions). Use... | `npm i -D fast-check` | `MIT` |
| [Android UI/Application Exerciser Monkey](https://android.googlesource.com/platform/development/+/master/cmds/monkey) | The original on-device monkey: a command-line tool shipped in the Android SDK that fires... | Any Android app/APK. Use for repeatable (seeded) UI stress to find crashes, unhandled exceptions, and ANRs... | `bundled with toolchain` | `Apache-2.0` |
| [Fastbot_Android](https://github.com/bytedance/Fastbot_Android) | ByteDance's model-based Android UI fuzzer that extends the original Monkey with... | Large/complex Android app where dumb Monkey gets stuck on shallow screens. Use for deeper, model-guided... | `see repo` | `LicenseRef-Fastbot-Revised-License` ⚠️ |
| [Appium](https://github.com/appium/appium) | Cross-platform UI automation server built on the W3C WebDriver protocol, driving... | Mobile or cross-platform app (iOS/Android/desktop) needing scripted stress beyond Android's built-in Monkey,... | `npm i -g appium` | `Apache-2.0` |
| [Detox](https://github.com/wix/Detox) | Gray-box E2E testing framework for React Native (and native) mobile apps that... | React Native / native mobile app where flaky timing hides real crashes. Use to run long... | `npm i -D detox` | `MIT` |

All testing is **authorized targets only** - see [`../AGENTS.md`](../AGENTS.md).
