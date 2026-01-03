# .devcontainer/Dockerfile

# ベースイメージ: Go 1.23 (最新安定版)
FROM mcr.microsoft.com/devcontainers/go:1-1.23-bookworm

# --- 1. Node.js & Amplify CLI のインストール ---
# AmplifyにはNode.jsが必要です (LTS v20系を選択)
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - \
    && apt-get install -y nodejs

# Amplify CLI のインストール
RUN npm install -g @aws-amplify/cli

# --- 2. AIツールのインストール ---
# Claude Code (Anthropic公式CLI)
RUN npm install -g @anthropic-ai/claude-code

# Gemini API利用のためのPythonライブラリ (CLIツールとして利用するスクリプト用)
RUN apt-get update && apt-get install -y python3-pip \
    && pip3 install google-generativeai --break-system-packages

# --- 3. その他便利ツール ---
# 開発効率化のための追加パッケージがあればここに記述