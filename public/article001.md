---
title: 【Electron + Vite + Vue】音楽再生アプリ「Muwviz」を作成しました
tags:
  - Electron
  - Vue.js
  - vite
  - TypeScript
  - 個人開発
private: false
updated_at: ''
id: null
organization_url_name: null
slide: false
ignorePublish: false
---

## はじめに

ビジュアライザーを眺めながら音楽を聴けるアプリが欲しいなと思い、
Electron、バックエンド／フロントエンドの勉強を兼ねて作成してみました。

音楽を耳と目で楽しめるアプリ『Muwviz』です。

<img align=left width="160px" alt="ロゴ" src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/370744/2f669688-1608-3520-5666-c14d0f3593d5.png" />

![muwviz_screenshot.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/370744/8a10334e-4621-7685-f345-22e148b9488d.png)

## 成果物

- リポジトリ（GitHub）

https://github.com/antimacho612/Muwviz

- ダウンロード（GitHub Releases）

お使いのPCに合った最新版のインストーラをダウンロードし、インストールしてください。

https://github.com/antimacho612/Muwviz/releases

## 機能・特徴

- PC内の音楽ファイル（`.aac`, `.mp3`, `.ogg`, `.wav`, `.flac`, `.webm`, `.m4a`）を再生します
  - シャッフル再生（アーティスト単位、アルバム単位など）
  - リピート再生（全曲、一曲）
- 楽曲再生時、リアルタイムで楽曲を解析し、ビジュアライザーを表示します
- ビジュアライザーのカスタマイズが可能です
- ビジュアライザーの設定をプリセットとして保存できます
- 音楽ファイルに登録されている詳細情報・歌詞（メタデータ）を参照できます
- 外観（テーマ、メインカラー、フォント）のカスタマイズが可能です
- 楽曲のリアルタイム検索（曲名、アーティスト名、アルバム名）が可能です

使い方としては、一般的な音楽再生アプリと同様で、PC内にある音楽ファイルをアプリに読み込ませる（スキャンさせる）ことでライブラリに追加され、以降、再生や検索、詳細情報の確認ができるようになります。

ビジュアライザーの表示には、`audiomotion-analyzer` ライブラリを使用させていただきました。

https://audiomotion.dev/#/

## 使用技術・ライブラリ

- ネイティブアプリ化
  - `Electron`（`electron-vite`）
    - メインプロセス／レンダラープロセス両方のホットリロードに対応
- バックエンド（メインプロセス）
  - `Node.js`
  - `TypeScript`
  - `music-metadata`
    - 音楽ファイルからメタデータを取得するために使用
  - `jimp`
    - アートワークを保存するために使用
- フロントエンド（レンダラープロセス）
  - `Vite`（`electron-vite`）
  - `Vue3`, `TypeScript`, `Sass`
    - ニューモーフィズムデザインを採用
    - 必要なコンポーネント数があまり多くないことと、デザインを統一させるために、UIフレームワークは使用せずほぼ自作
  - `audiomotion-analyzer`
    - リアルタイムスペクトラムアナライザー
    - ビジュアライザーの表示に使用
  - `waveform-data`
    - 再生中の楽曲の波形データを取得するために使用
  - `d3`
    - waveform-dataで取得した波形データを描写するために使用（画面下部）
- その他
  - `electron-log`
    - ロガー, メインプロセス／レンダラープロセス共通で使用
  - `electron-updater`
    - 自動アップデートに対応するため使用

## 最後に

最後まで読んでいただきありがとうございます。
今後余裕があれば、具体的な実装についての記事も書こうかと思っています。

もし興味があれば、ダウンロードお願いします！
※フィードバックいただけると大変うれしいです！
