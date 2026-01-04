# Go App Development Environment

VS Code Dev Container を利用した Go & AWS Amplify 開発環境です。

## 前提条件 (Prerequisites)
以下のツールをインストールしてください。
- [Docker Desktop](https://www.docker.com/products/docker-desktop/) (起動しておくこと)
- [Visual Studio Code](https://code.visualstudio.com/)
- VS Code Extension: [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## セットアップ手順 (Setup)

1. **リポジトリのクローン**
   ```bash
   git clone <このリポジトリのURL>
   cd go-app-dev-env

2. 環境変数の設定 (重要) .devcontainer フォルダ内に .env ファイルを作成し、ご自身のAPIキーを設定してください。

   .devcontainer/.env 作成例:

   # AWS Credentials (IAM User: Developers)
    AWS_ACCESS_KEY_ID=AKIAxxxxxxxxxxxx
    AWS_SECRET_ACCESS_KEY=xxxxxxxxxxxxxxxxxxxxxxxxxxxx
    AWS_DEFAULT_REGION=ap-northeast-1

   # AI Tools (Optional)
    ANTHROPIC_API_KEY=sk-ant-xxxx
    GEMINI_API_KEY=xxxx

3. コンテナの起動
    - VS Code でこのフォルダを開きます。
    - 左下の緑色のアイコンをクリックし、"Reopen in Container" を選択します。
    - 初回はビルドに数分かかります。

4. 動作確認 ターミナルが開いたら、以下を確認してください。

    go version
    aws sts get-caller-identity
    claude --version

## 開発フロー
- Go: main.go を編集し、go run . で実行。
- Amplify: amplify init でプロジェクト初期化。

---

### これで全て完了です