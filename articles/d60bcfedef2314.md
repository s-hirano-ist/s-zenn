---
title: "30分でmacとdockerでローカルLLM環境構築メモ"
emoji: "🐷"
type: "tech" # tech: 技術記事 / idea: アイデア
topics:
  - "mac"
  - "llm"
  - "dify"
  - "deepseek"
published: false
---

各手順は公式READMEを参考に実行しております。

## 実行環境

- Mac mini M4チップ 32GBメモリ
- macOS Sequoia 15.3.1

## 環境構築

1. 事前準備

   1. [Docker Desktop](https://www.docker.com/ja-jp/)のインストールト起動

1. [Dify](https://github.com/langgenius/dify)の環境構築

   ```bash
   git clone https://github.com/langgenius/dify.git
   cd dify
   cd docker
   cp .env.example .env
   docker compose up -d
   ```

1. [Dify](https://github.com/langgenius/dify)の初期セットアップ

[http://localhost/install](http://localhost/install)にアクセスし、会員登録

1. [Ollama](https://github.com/ollama/ollama)の環境構築

   ```bash
   docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama
   ```

1. [Ollama](https://github.com/ollama/ollama)の実行

   ```bash
   docker exec -it ollama ollama run deepseek-r1
   ```
