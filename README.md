# 卒業制作用 React テンプレート
## 目次
- [使用技術](#technology)
- [環境構築の手順](#setup)
- [ディレクトリ構成](#directory)

<h2 id="technology">使用技術</h2>

### Build Tool
- Vite

### Frontend
- TypeScript
- React

<h2 id="setup">環境構築の手順</h2>

### 1. パッケージのインストール

```
cd frontend
```
```
npm install
```

### 3. ローカル環境の立ち上げ

```
npm run dev
```

- http://localhost:8080/ にアクセスできれば問題なし

<h2 id="directory">ディレクトリ構成</h2>

```
zeroplus-template/
│
├── backend/
│
└── frontend/
    ├── public/
    │   └── favicon.svg
    ├── src/
    │   ├── assets/
    │   ├── components/
    │   ├── css/
    │   │   ├── reset.css
    │   │   └── style.css
    │   ├── App.tsx
    │   ├── index.html
    │   └── main.tsx
    ├── .gitignore
    ├── index.html
    ├── package-lock.json
    ├── package.json
    ├── README.md
    ├── tsconfig.app.json
    ├── tsconfig.json
    ├── tsconfig.node.json
    └── vite.config.js
```
