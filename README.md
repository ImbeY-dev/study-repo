# study-repo

このリポジトリは、WSL（Ubuntu）と VS Code を使った開発環境構築、および React 学習のためのリポジトリです。  
ここでは、環境構築の手順と作業ログをまとめています。

---

## 1. WSL のセットアップ

1. 管理者権限の PowerShell で WSL をインストール
```
wsl --install
```
2. Ubuntu を初期設定  
3. 開発用ディレクトリを作成  
```
mkdir ~/dev
cd dev
```
---

## 2. VS Code と WSL の連携

1. Ubuntu のターミナルで VS Code を起動 
```
code .
```
2. VS Code 左下に **WSL: Ubuntu** と表示されることを確認  
3. 拡張機能 **Remote - WSL** をインストール  
4. 日本語化のために **Japanese Language Pack** をインストール

---

## 3. Git の設定（WSL 内）

1. Git のインストール確認 
```
git --version
```
2. Ubuntuのパッケージ情報の最新化＆gitのダウンロード
```
sudo apt update
sudo apt install git
```
3. GitHub アカウント情報を設定 
```
git config --global user.name "（Githubアカウント名）"
git config --global user.email "（GitHubメールアドレス）"
```
---

## 4. GitHub リポジトリの作成

GitHub 上で `study-repo` を作成し、以下を設定：

- README：追加  
- .gitignore：Node（React 用）  
- ライセンス：任意（今回はなし）

---

## 5. リポジトリのクローン

WSL の `~/dev` に移動してリポジトリのクローン
```
cd ~/dev
git clone https://github.com/ImbeY-dev/study-repo.git
cd study-repo
code .
```
---

## 6. React（Vite + TypeScript）プロジェクトの作成

study-repo の中に React プロジェクトを作成しました。

### 1. Vite プロジェクトの作成

以下のコマンドを実行し、framework として **React**、variant として **TypeScript** を選択しました。
```
npm create vite@latest my-app --template react-ts
```

### 2. プロジェクトフォルダへ移動
```
cd my-app
```

### 3. 依存パッケージのインストール
```
npm install
```

### 4. 開発サーバーの起動
```
npm run dev
```

表示された URL（例：`http://localhost:5173`）にアクセスすると、  
Vite + React + TypeScript の初期画面が表示されます。

---

---

## 7. GitHub への push（変更の反映）

React プロジェクトを追加したため、変更内容を GitHub に反映しました。

### 1. 変更内容の確認
```
git status
```

変更されたファイル（例：README.md や my-app フォルダ）が表示されます。

### 2. 変更をステージング（Git に登録）
```
git add .
```

### 3. コミット（変更にメッセージをつけて保存）
```
git commit -m "Add React project (Vite + TypeScript)"
```

メッセージは任意で OK。

### 4. GitHub へ push（反映）
```
git push
```

GitHub の study-repo に変更が反映されます。

---

## 8. VS Code のおすすめ拡張機能（備考）

React / TypeScript / WSL 開発を快適にするために、以下の拡張機能を導入しました。

### 🔹 GitHub Copilot
AI によるコード補完を行う拡張機能。  
コードの提案、関数の補完、コメントからのコード生成などが可能で、学習効率が大幅に向上します。

### 🔹 ESLint
JavaScript / TypeScript のコード品質を保つための静的解析ツール。  
コードの書き方を統一し、エラーを事前に防ぐことができます。

### 🔹 Prettier – Code formatter
コードを自動整形するための拡張機能。  
保存時に自動でフォーマットされ、コードの読みやすさと統一性が向上します。  
ESLint と併用することで、より安定したコード品質を保つことができます。

### 🔹 GitLens

Git の履歴や変更点を視覚的に確認できる強力な拡張機能。  
誰が・いつ・どの行を変更したかが一目でわかり、コードレビューや学習に役立ちます。

主な機能：
- 行ごとの blame 表示
- コミット履歴の可視化
- ファイルごとの変更差分の確認
- GitHub との連携強化

---
