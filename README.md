# ⚡ React + TypeScript + Vite

This template provides a **minimal yet powerful** setup to get **React** working seamlessly with **Vite**, featuring **HMR (Hot Module Replacement)** and **ESLint rules** for a better development experience.

## 🚀 Features
- **Blazing Fast ⚡** - Powered by Vite's ultra-fast bundling.
- **TypeScript Support 🛠️** - Strongly typed codebase for better maintainability.
- **HMR (Hot Module Replacement) 🔥** - Instant updates without full page reloads.
- **ESLint with Type-Aware Rules ✅** - Enforced best practices and clean code.
- **SWC Support 🏎️** - Supercharged JavaScript & TypeScript compilation.

## 📦 Official Plugins
- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) - Uses [Babel](https://babeljs.io/) for **Fast Refresh**.
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) - Uses [SWC](https://swc.rs/) for **Fast Refresh**.

## 🔧 Expanding the ESLint Configuration
If you're developing a **production application**, we recommend enhancing the ESLint configuration to **enable type-aware lint rules**.

### 1️⃣ Update `parserOptions`
Modify the top-level `parserOptions` property like this:

```js
export default tseslint.config({
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

### 2️⃣ Use Type-Checked ESLint Rules
Replace:
```js
tseslint.configs.recommended
```
with:
```js
tseslint.configs.recommendedTypeChecked
```
or:
```js
tseslint.configs.strictTypeChecked
```
Optionally, you can add:
```js
...tseslint.configs.stylisticTypeChecked
```
for a more stylistic approach.

### 3️⃣ Install & Configure `eslint-plugin-react`
Ensure you have [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) installed, then update your ESLint config:

```js
// eslint.config.js
import react from 'eslint-plugin-react'

export default tseslint.config({
  // Set the React version
  settings: { react: { version: '18.3' } },
  plugins: {
    // Add the React plugin
    react,
  },
  rules: {
    // other rules...
    // Enable recommended rules
    ...react.configs.recommended.rules,
    ...react.configs['jsx-runtime'].rules,
  },
})
```

## 🎯 Getting Started
1️⃣ **Clone the repo:**
```sh
git clone https://github.com/yourusername/your-repo.git
cd your-repo
```

2️⃣ **Install dependencies:**
```sh
npm install
```

3️⃣ **Run the development server:**
```sh
npm run dev
```

4️⃣ **Build for production:**
```sh
npm run build
```

## 🛠 Recommended Tools
- **VS Code** + ESLint & Prettier extensions for better DX.
- **React DevTools** for debugging React components efficiently.
- **Vite Plugins** for enhanced performance and features.

🚀 **Happy Coding!** 🎉

