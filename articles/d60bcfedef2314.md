---
title: "10分で動かすDify（Mac×Docker×Dify）"
emoji: "🐷"
type: "tech" # tech: 技術記事 / idea: アイデア
topics:
  - "mac"
  - "dify"
published: true
---

## はじめに

ただのフロントエンドエンジニアがDifyをMacで動かした備忘録です。
なお、各手順は公式READMEを参考にしております。

## 実行環境

- Mac mini M4チップ 32GBメモリ
- macOS Sequoia 15.3.1

## 環境構築

1. 事前準備

   1. [Docker Desktop](https://www.docker.com/ja-jp/)のインストールと起動

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

   :::message
   ローディングが終わらない場合は、ブラウザをリロードすると次に進める場合があります。
   :::

## 感想

想像以上に簡単にセットアップできて驚きです。Dockerはやはり神だ。

次回はDifyとOllamaを用いてローカルLLMを動かしたいと思います。
