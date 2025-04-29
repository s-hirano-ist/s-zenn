---
title: "10分で動かすローカルLLMとRAG（Mac×Docker×Dify）"
emoji: "🐷"
type: "tech" # tech: 技術記事 / idea: アイデア
topics:
  - "docker"
  - "mac"
  - "llm"
  - "ollama"
  - "rag"
published: false
---

## はじめに

ただのフロントエンドエンジニアがDeepSeekをMacで動かした備忘録です。
[以前の記事](https://zenn.dev/s_hirano_ist/articles/cbb35bee8d59c8)の続編となります。
Difyのナレッジ機能を用いて、RAGのようなシステムを作っていきます。

## 実行環境

- Mac mini M4チップ 32GBメモリ
- macOS Sequoia 15.3.1

## 事前準備

1. [Dify](https://github.com/langgenius/dify)のインストールと起動
1. チャットボットを作成済みで、ローカルLLMが動く状態までセットアップ
1. 「インデックス方法」は推奨のものにするために、下記コマンドを実行し、[以前の投稿](https://zenn.dev/s_hirano_ist/articles/cbb35bee8d59c8#%E3%83%AD%E3%83%BC%E3%82%AB%E3%83%ABllm%E5%B0%8E%E5%85%A5%E6%89%8B%E9%A0%86)と同じ方法でEmbedding model（埋め込みモデル）を取り込む

    ```bash
    ollama pull nomic-embed-text
    ```

## ナレッジの設定手順

1. 「ナレッジを作成」ボタンを押す
1. 事前に準備したファイルをテキストファイルをアップロード
    :::message
    今回は検証のため、[自分が雑にまとめている記事](https://s-hirano.com/summary)をいれてみます。
    どのようなフォーマットがよいかについては今後検証して解を見つけていこうと考えております。
    :::
1. 一旦検証のため、デフォルト状態で「保存して処理」ボタンを押す
    :::message
    「インデックス方法」が推奨値の「高品質」になっているかは要確認（埋め込みモデルの登録があるか否かによってデフォルト値が変わるらしい）
    :::
1. インデックス化のため、少し時間を待つ
1. チャットボットのコンテキストで「追加」を押し、先ほど作成したナレッジを選択する

## 感想

全然ナレッジがヒットしなかったです。
日本語に適した埋め込みモデルを利用していないのが問題かもしれません。
次は、HuggingFaceからLLMとEmbedding Modelを取得して、そちらで性能向上してみます。
