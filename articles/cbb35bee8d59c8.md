---
title: "10分で動かすローカルLLM（Mac×Dify×Ollama×DeepSeek編）"
emoji: "🐷"
type: "tech" # tech: 技術記事 / idea: アイデア
topics:
  - "mac"
  - "dify"
  - "ollama"
  - "deepseek"
published: false
---


## はじめに

ただのフロントエンドエンジニアがDifyとOllamaを用いてDeepSeekをローカルLLMとして動かした備忘録です。

## 実行環境

- Mac mini M4チップ 32GBメモリ
- macOS Sequoia 15.3.1

## 事前準備

1. [Dify](https://github.com/langgenius/dify)のインストールと起動
1. [Ollama](https://github.com/ollama/ollama)のインストールと起動

:::message
インストール方法は[以前の記事](https://zenn.dev/s_hirano_ist/articles/d60bcfedef2314)を参考にしてください。
Difyを<http://localhost:80>、Ollamaを<http://localhost:11434>でアクセスできる想定で記述します。
:::

## ローカルLLM導入手順

1. 「最初から作成」をクリック
1. 「チャットボット」を選択し、に任意の名前・アイコン・説明を追加する
1. 「設定に移動」をクリックし、モデルプロバイダーで「Ollama」を選択する
    :::message
    デフォルトでは、LLMプロバイダーキーが設定されておらず、警告文が表示されます。
    :::
1. 下記を設定し、保存ボタンを押す
    1. Model Name: deepseek-r1:32b
    :::message
    他のモデルを動かしている場合は、適宜変更してください。
    :::
    1. Base URL: <http://host.docker.internal:11434>
    :::message
    DifyをDockerコンテナ内、Ollamaをネイティブアプリとして動かしているため、`host.docker.internal`を利用する。
    :::
1. 画面をリロード
    :::message
    選択されたLLMのモデルがOpenAIの場合は、一度アプリを削除し、再度作成すると直る場合がある。
    :::

## 実行結果

右側に出てくるチャットボットで実行を確認。

## 感想

GUIで簡単にチャットボットが作成できるのは驚きだった。

次回はRAGをつくってみようと思う。
