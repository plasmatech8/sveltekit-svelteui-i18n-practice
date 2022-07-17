# sveltekit-svelteui-i18n-practice

- [sveltekit-svelteui-i18n-practice](#sveltekit-svelteui-i18n-practice)
  - [01. Initialise Sveltekit App](#01-initialise-sveltekit-app)
  - [02. Install SvelteUI](#02-install-svelteui)

## 01. Initialise Sveltekit App

Initialise app:
```bash
npm init svelte@next my-app
# ✔ Where should we create your project?
# ✔ Directory not empty. Continue? … yes
# ✔ Which Svelte app template? › Skeleton project
# ✔ Add type checking with TypeScript? › Yes, using TypeScript syntax
# ✔ Add ESLint for code linting? … No / Yes
# ✔ Add Prettier for code formatting? … No / Yes
# ✔ Add Playwright for browser testing? … No / Yes
npm install
```

VS Code configuration:
* [settings.json](.vscode/settings.json)
* [extensions.json](.vscode/extensions.json)

## 02. Install SvelteUI

Following: https://www.svelteui.org/installation

Install packages:
```bash
npm i dayjs @svelteuidev/motion @svelteuidev/dates @svelteuidev/core @svelteuidev/composables
```