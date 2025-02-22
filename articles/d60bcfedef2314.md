---
title: "10分で動かすDify（Mac×Docker×Dify編）"
emoji: "🐷"
type: "tech" # tech: 技術記事 / idea: アイデア
topics:
  - "mac"
  - "dify"
published: true
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

   ![](/images/dify/setup-1.png)

   ![](/images/dify/setup-2.png)

## 感想

想像以上に簡単にセットアップできて驚きです。Dockerはやはり神だ。

![](/images/dify/setup-3.png)

次回はDifyとOllamaを用いてローカルLLMを動かしたいと思います。
