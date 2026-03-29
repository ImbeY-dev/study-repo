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
