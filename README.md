# README

## About

Wails2 based on bun, svelte5 and shadcn.

- Prerequisite
  - jq @1.7.1
  - bun @1.2.3
  - wails @2.10.1
  - task @3.42.0

- Usage
  - create a project folder
  ```sh
  md mytest
  cd mytest
  ```
  - Init. wails with template local folder
  ```sh
  wails init -d . -n myapp -t https://github.com/ericwu-glife/wails2_sv5_bun
  ```
  This creates the directory "mytest" with default files:

  ```shell title=mytest/
    .
    |-- .vscode
    |-- frontend
    |   |-- .vscode
    |   |-- public
    |   |   `-- vite.svg
    |   |-- src
    |   |   |-- assets  
    |   |   |   |-- fonts
    |   |   |   `-- images
    |   |   |       `-- logo-universal.png
    |   |   |-- lib
    |   |   |-- app.css
    |   |   |-- App.svelte
    |   |   |-- main.ts
    |   |   |-- style.css
    |   |   |-- vite-env.d.ts
    |   |   `-- main.js
    |   |-- wailsjs
    |   |   |-- go
    |   |   `-- runtime
    |   |-- .gitignore
    |   |-- bun.lock
    |   |-- components.json
    |   |-- index.html
    |   |-- package-lock.json
    |   |-- package.json
    |   |-- package.json.md5
    |   |-- postcss.config.js
    |   |-- README.md
    |   |-- svelte.config.js
    |   |-- tailwind.config.ts
    |   |-- tsconfig.app.json
    |   |-- tsconfig.json
    |   |-- tsconfig.node.json
    |   `-- vite.config.ts
    |-- scripts
    |   |-- build*.sh
    |   `-- install-wails-cli.sh
    |-- app.go
    |-- go.mod
    |-- go.sum
    |-- main.go
    |-- NEXTSTEPS.md
    |-- README.md
    |-- Taskfile.yml
    `-- wails.json
    ```

## Add shadcn-svelte components
Go into the `frontend` directory and run command
```sh
bun x shadcn-svelte@next add {{component_name}}
```  

## Live Development

To run in live development mode, run `wails dev` in the project directory. In another terminal, go into the `frontend`
directory and run `bun --bun run dev`. The frontend dev server will run on http://localhost:34115. Connect to this in your
browser and connect to your application.

## Building

To build a redistributable, production mode package, use `wails build`.
