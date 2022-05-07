# ToDo App (todo-quasar)

A Quasar Project

## Install the dependencies

```bash
yarn
# or
npm install
```

### Start the app in development mode (hot-code reloading, error reporting, etc.)

```bash
quasar dev
```

### Lint the files

```bash
yarn lint
# or
npm run lint
```

### Format the files

```bash
yarn format
# or
npm run format
```

### Build the app for production

```bash
quasar build
```

### Customize the configuration

See [Configuring quasar.config.js](https://v2.quasar.dev/quasar-cli-vite/quasar-config-js).

### プロジェクト作成

```shell
# install
yarn global add @quasar/cli
# create project
yarn create quasar

√ What would you like to build? » App with Quasar CLI, let's go!
√ Project folder: ... todo-quasar
√ Pick Quasar version: » Quasar v2 (Vue 3 | latest and greatest)
√ Pick script type: » Typescript
√ Pick Quasar App CLI variant: » Quasar App CLI with Vite (BETA stage)
√ Package name: ... todo-quasar
√ Project product name: (must start with letter if building mobile apps) ... ToDo App
√ Project description: ... A Quasar Project
√ Author: ...
√ Pick a Vue component style: » Composition API
√ Pick your CSS preprocessor: » Sass with SCSS syntax
√ Check the features needed for your project: » ESLint
√ Pick an ESLint preset: » Prettier

√ Install project dependencies? (recommended) » Yes, use yarn
```

### チュートリアル内容

- script の追加

  - dev (quasar dev)
  - build (quasar build)
  - build pwa (quasar build -m pwa)

- pages

  - Todo ページ、Help ページ作成

- MainLayout

  - ツールバーに背景画像差し込み（q-toolbar）
  - サイドメニュー差し替え（q-drawer）
  - メニューリンク差し替え（q-list）
  - router-view を keep-alive に（？）

- Todo ページ
  - チェックボックス
  - チェックオンで取り消し線、削除ボタンの追加
  - 確認ダイアログの表示

- quasar.config.js
  - プラグイン追加
    - ダイアログ、通知
