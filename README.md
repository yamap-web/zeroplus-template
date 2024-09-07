# ZeroPlus Webアプリケーションコース 卒業制作用テンプレート
## 目次
- [使用技術](#使用技術)
- [環境構築の手順](#環境構築の手順)
- [npm-scripts](#npm-scriptsfrontendpackagejson)
- [ディレクトリ構成](#ディレクトリ構成)

## 使用技術
### Build Tool
- Vite
### Frontend
- TypeScript
- React

## 環境構築の手順
### 1. パッケージのインストール
```shell
cd frontend
```
```shell
npm install
```
### 2. ローカル環境の立ち上げ
```shell
npm run dev
```
- http://localhost:8080/ にアクセスできれば問題ありません。

## npm-scripts（`frontend/package.json`）
### `dev`
- 開発サーバーの立ち上げ
### `build`
- 「**ビルド (build)**」（ソースコードから実際に動かすプログラムを生成）を実行
### `preview`
- ビルドしたアプリケーションのプレビューを確認

## ディレクトリ構成
```
zeroplus-template/
├── backend/
│   └── .gitignore
├── frontend/
│   ├── public/
│   │   └── favicon.svg
│   ├── src/
│   │   ├── components/
│   │   ├── css/
│   │   │   ├── reset.css
│   │   │   └── style.css
│   │   ├── App.tsx
│   │   └── main.tsx
│   ├── .env.example
│   ├── .gitignore
│   ├── index.html
│   ├── package-lock.json
│   ├── package.json
│   ├── tsconfig.app.json
│   ├── tsconfig.json
│   ├── tsconfig.node.json
│   └── vite.config.ts
└── README.md
```
### `README.md`（このファイル）
- プロジェクトの概要やセットアップ方法などを記載しておくドキュメントファイル
### `.gitignore`（frontend/backend 共通）
- Gitにコミットしないファイルやディレクトリを指定します。
- 例えば、ビルドした成果物（`dist`ファイル）や環境設定ファイル（`.env`）などが含まれます。
### `.env`
- 「**環境変数**」（実行する環境によって異なる変数）を定義します。
- 例えば、サーバーサイドアプリケーション（Expressなどで`backend`ディレクトリに作成）のURLは、開発環境の場合に`localhost:3000`でも、本番環境では実際にドメインを有するアドレスになります。
- 他にも、GitHubに公開したくないデータベースのパスワードなども環境変数として設定します。
### `.env.example`と、Viteにおける環境変数の使い方
- `.env`ファイルはGitにコミットしないように`.gitignore`ファイルで設定されています。そのため、こちらのexampleファイルに`.env`ファイルに記述すべき環境変数の例を記述しております。
- `.env.example`ファイルを複製し、`.env`ファイルとして作成しましょう。
    ```shell
    cp .env.example .env
    ```
- `frontend`ディレクトリはビルドツールに`Vite`を使用しています。Viteを使用する場合、環境変数は`VITE_`から始まる命名を行いましょう。
    ```shell
    VITE_SERVER_URL="http://localhost:3000"
    ```
- 設定した環境変数は`import.meta.env.環境変数`と記述することで呼び出すことが可能です。
    ```javascript
    const API_URL = import.meta.env.VITE_SERVER_URL;
    ```
- Viteでの環境変数の扱い方について詳しくは [公式ドキュメント](https://ja.vitejs.dev/guide/env-and-mode)をご覧ください。
### `public/`
- 画像ファイルなどの静的アセットを格納するディレクトリ
- 現在は`favicon.svg`ファイルが入っています
### `src/`
- CSS, TypeScriptのソースコードを格納するディレクトリ
    ### `components/`
    - Reactのコンポーネントファイルを格納するディレクトリ
    - 空のディレクトリはGitで管理できないため、`.gitkeep`というファイルを配置しています。ディレクトリ内に新しくファイルを作成したときにこちらは削除してください。
    ### `css/`
    - CSSファイルを格納するディレクトリ
        #### `reset.css`
        - ブラウザのデフォルトスタイルをリセットするためのCSSファイル
        #### `style.css`
        - プロジェクト全体のスタイルを定義するCSSファイル
    ### `App.tsx`
    - Reactアプリケーションのメインコンポーネント
    ### `main.tsx`
    - ReactアプリケーションのエントリーポイントとなるTypeScriptファイル
### `index.html`
- クライアントサイドアプリケーションのエントリーポイントとなるHTMLファイル
### `package-lock.json`
- プロジェクトの依存関係の正確なバージョンを記録するファイル
### `package.json`
- プロジェクトの依存関係やスクリプト、メタデータを定義するファイル
- `"name": "zeroplus-template"`となっているので、編集する必要あり
### `tsconfig.app.json`
- TypeScriptコンパイラの設定ファイル（アプリケーション用）
### `tsconfig.json`
- TypeScriptコンパイラの設定ファイル（全体用）
### `tsconfig.node.json`
- TypeScriptコンパイラの設定ファイル（`vite.config.ts`用）
### `vite.config.ts`
- Viteの設定ファイル