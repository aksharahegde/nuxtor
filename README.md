<p align="center">
    <img width="150" src="./src/assets/logo.svg" alt="logo">
</p>
<h1 align="center">NUXTOR</h1>
<p align="center">
A spiritual successor of <a href="https://github.com/NicolaSpadari/vitauri">ViTauri</a>, made with <a href="https://nuxt.com">Nuxt 3</a> and <a href="https://tauri.app">Tauri 2</a>
<br>
Build super fast desktop applications!
</p>

>**⚠️ `nuxtor` is still a WIP**

<br />

<img src="https://img.shields.io/github/license/NicolaSpadari/nuxtor" />

<br />

<div align="center">
<img src="./screenshot.png">
</div>

<p align="center">Powered by Nuxt 3</p>

<br />

## Technologies run-down

- Nuxt 3
- Tauri 2
- UnoCSS
- Typescript
- ESLint
- Auto imports (for Tauri api too!)

## Functionalities

- Run shell commands from the app
- Send custom notifications to the client
- Display OS related informations
- Support catch-all route

## Setup

  - This project enforces [pnpm](https://pnpm.io). In order to use another package manager you need to update `package.json` and `tauri.config.js`
  - Before running this app, you need to configure your environment with Rust. Take a look at the [Tauri docs](https://v2.tauri.app/start/prerequisites).
  - The frontend runs on the usual port `3000` of Nuxt, the Tauri server uses the port `3001`. This settings are customizable in the `nuxt.config.ts` and `tauri.config.js`.
  - Once ready, follow these commands:

  ```sh
  # use this template
  $ npx degit NicolaSpadari/nuxtor my-nuxtor-app

  # go into the folder
  $ cd my-nuxtor-app

  # install dependencies
  $ pnpm install

  # start the project
  $ pnpm run tauri:dev
  ```

  This will run the Nuxt frontend and will launch the Tauri window.

## Build

  ```sh
  $ pnpm run tauri:build
  ```

This command will generate the Nuxt static output and bundle the project under `src-tauri/target`.

## Notes

- As the documentation shows, the Nuxt SSr must be disabled in order for Tauri to act as the backend. Still, all Nuxt capabilities are still here.
- Tauri v2 is still in beta. Some things might not work, or present some bugs.
- Tauri v2 brings some big refactors, such as packages names and permission management. New permissions have to be granted under `src-tauri/capabilities/main.json`
- Tauri js functions are auto imported as-is with the help of a custom module. If another Tauri plugin is added, then the module has to be updated to support auto imports under `src/modules/tauri.ts`

## License

MIT License © 2024-PRESENT [NicolaSpadari](https://github.com/NicolaSpadari)
