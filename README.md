# sveltekit-svelteui-practice

- [sveltekit-svelteui-i18n-practice](#sveltekit-svelteui-i18n-practice)
  - [01. Initialise Sveltekit App](#01-initialise-sveltekit-app)
  - [02. Install SvelteUI](#02-install-svelteui)
  - [03. Install TailwindCSS](#03-install-tailwindcss)

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

## 03. Install TailwindCSS

Note: https://www.svelteui.org/faq#how-do-i-integrate-tailwindcss-with-svelteui

Install package:
```bash
npm install -D tailwindcss
npx tailwindcss init
```

Created [tailwind.config.cjs](tailwind.config.cjs):
```cjs
/** @type {import('tailwindcss').Config} */
module.exports = {
	content: ['./src/**/*.{html,js,svelte,ts}'],
	theme: {
		extend: {}
	},
	important: true,
	plugins: []
};
```

Created [app.css](src/app.css):
```css
/* Write your global styles here, in PostCSS syntax */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Created [postcss.config.cjs](tailwind.config.cjs):
```cjs
const tailwindcss = require('tailwindcss');
// const autoprefixer = require('autoprefixer');

const config = {
	plugins: [
		//Some plugins, like tailwindcss/nesting, need to run before Tailwind,
		tailwindcss()
		//But others, like autoprefixer, need to run after,
		// autoprefixer
	]
};

module.exports = config;
```
