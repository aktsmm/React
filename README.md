# 初期コミット
+ https://www.udemy.com/course/react-product-development/learn/lecture/49016287#overview

## NARUTO 図鑑
### ① Chocolatey が未導入ならまず導入（管理者 PowerShell）
Set-ExecutionPolicy Bypass -Scope Process -Force; `
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.SecurityProtocolType]::Tls12; `
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

### ② Node.js（LTS版）を Chocolatey 経由でインストール
choco install nodejs-lts -y

### ③ 確認：Node.js と npm が使えるか
node -v
npm -v

### ④ npx を使って React アプリを作成
npm list -g yarn
npm install -g yarn
npx create-react-app@latest naruto-app


cd D:\03_github\React\01_Naruto_book\naruto-app2

# 起動
  cd naruto-app
  npm start


## メモ

| フレームワーク | 初期化コマンド                              | 解説                                     |
| ------- | ------------------------------------ | -------------------------------------- |
| React   | `npx create-react-app@latest my-app` | シンプルな SPA（Single Page Application）向け構成 |
| Next.js | `npx create-next-app@latest my-app`  | SSR/SSG 対応、フルスタック可能な構成                 |

| 項目                          | React（CRA）                    | Next.js（CNA）                         |
| --------------------------- | ----------------------------- | ------------------------------------ |
| ライブラリ or フレームワーク            | ライブラリ（構成は自分で選ぶ）               | フレームワーク（構成済）                         |
| ルーティング                      | ❌ 自前で `react-router-dom` を導入  | ✅ ファイルベース（`/app` or `/pages`）        |
| SSR（Server Side Rendering）  | ❌ 非対応                         | ✅ `getServerSideProps` などで対応可能       |
| SSG（Static Site Generation） | ❌ 非対応                         | ✅ `getStaticProps` で対応可能             |
| CSR（Client Side Rendering）  | ✅ 対応                          | ✅ 対応                                 |
| APIルート（バックエンド）              | ❌ 別途 Express などで構築            | ✅ `/pages/api` または `/app/api`        |
| SEO対策                       | ❌ 遅延レンダリングで弱い                 | ✅ SSRで強力に対応                          |
| デプロイしやすさ                    | ✅ Vercel, Netlify など対応        | ✅ 特にVercelと親和性が高い                    |
| 静的エクスポート対応                  | ❌                             | ✅ `next export` で可能                  |
| TypeScript対応                | ✅ `--template typescript` で対応 | ✅ 対話形式で選択可能                          |
| モダン機能（App Router等）          | ❌                             | ✅ App Router, Layouts, Suspense など対応 |

| 使用シーン例                 | おすすめフレームワーク |
| ---------------------- | ----------- |
| React単体の学習やプロトタイプ      | React（CRA）  |
| SEO対応したブログやLPサイト       | Next.js     |
| フロント＋軽量バックエンド（API）含む構成 | Next.js     |
| チーム開発や構成を楽にしたい         | Next.js     |

| 項目               | React                          | Express                              |
| ---------------- | ------------------------------ | ------------------------------------ |
| **種類**           | JavaScriptライブラリ（UI構築用）         | Node.js フレームワーク（Webサーバー構築用）          |
| **主な役割**         | フロントエンド（ユーザー画面）                | バックエンド（API、ルーティングなど）                 |
| **実行環境**         | ブラウザ上（クライアントサイド）               | Node.js上（サーバーサイド）                    |
| **使われる場面**       | SPA（Single Page Application）構築 | REST APIやWebアプリのサーバー構築               |
| **ルーティング**       | `react-router-dom`などでUI遷移      | `app.get()`, `app.post()`などでAPIルート制御 |
| **開発サーバー**       | `npm start` → ポート3000          | `node app.js` → 任意のポート（例: 5000）      |
| **HTML/CSSとの関係** | コンポーネント内で直接使用                  | 直接扱わない（テンプレートエンジン利用可）                |
| **代表的な使い方**      | UI構築、状態管理（hooks, Redux）など      | API提供、データベース操作など                     |
| **テンプレートエンジン**   | JSX（JavaScript XML）            | EJS、Pug、Handlebarsなど                 |
