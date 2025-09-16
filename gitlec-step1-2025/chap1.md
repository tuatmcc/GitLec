---
title: 【ハンズオン】手を動かして学ぶ Git 入門編(2025年版) 第 1 章
date: 2025-09-
author: sugawa197203
---

難易度: ★☆☆☆☆ 入門レベル

# 1. はじめに

* この記事は MCC Git 講習会 2025 の資料です.
* 入門編では Git ？ なんにそれおいしいの？って人や Git と Github の違いがわからない人の Git の知識を 0 から 1 にするための講習会です.
* コマンドはできる限りコピペではなく手打ちすることをおすすめします.

## 1.1. 環境構築

ここでは, git のインストールと, GitHub のアカウント作成と, git の初期設定を行います.

### 1.1.1. git のインストール

* Windows の場合

winget でインストールをします.

Windowsキーを押して `wt` と入力して Windows Terminal を起動し, 以下のコマンドを実行します.

```powershell
winget install --id Git.Git -e --source winget
``` 

* Mac の場合

TODO: 誰か詳しく書いて

Homebrew でインストールをします.

```bash
brew install git
```

* その他

自力で頑張ってください.

### 1.1.2. GitHub アカウントの作成

アカウントを持っていない人は, 以下の URL からアカウントを作成してください. 持ってればここの項目はスキップして OK です.

https://github.com/join

メールアドレスは個人用が望ましいです. 大学メアドだと卒業時に使えなくなる可能性があります.

### 1.1.3. git の初期設定

git の初期設定を行います. `user.name` の項目に GitHub のアカウント名, `user.email` の項目に GitHub のメールアドレス, `core.editor` の項目にエディタの設定を行います. 以下にそれぞれの 3 つのコマンド例を示します.

```powershell
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global core.editor "code --wait"
```

* GitHub のアカウント名

SUGAWA の GitHub アカウント名は `sugawa197203` です. なので `user.name` の項目は `sugawa197203` に設定します.

```powershell
git config --global user.name "sugawa197203"
```

* GitHub のダミーメールアドレス

`user.email` の項目は GitHub のダミーのメールアドレスに設定します. なぜダミーメールアドレスを使うかは後ほど説明します.

自身の GitHub のダミーメールアドレスは, GitHub の Settings -> Emails から確認できます.

Settings は右上のプロフィールアイコン -> Settings で開けます.

![GitHub の Settings -> Emails](./img/githubmail1.png)

メールアドレスは Settings の左のメニューから Emails を選択すると, `Keep my email addresses private` の部分に `数字+アカウント名@users.noreply.github.com` という形式で表示されます.

![Emails](./img/githubmail2.png)

SUGAWA の場合は `96975428+sugawa197203@users.noreply.github.com` というメールアドレスが表示されているので, これを `user.email` の項目に設定します.

```powershell
git config --global user.email "96975428+sugawa197203@users.noreply.github.com"
```

* エディタの設定

エディタの設定は気にしなければ以下のコマンドで OK です. `code` は Visual Studio Code のコマンドです.

```powershell
git config --global core.editor "code --wait"
```

これで git の環境構築は完了です.

## 1.2. グラフについて

git について学ぶ前に, グラフについて軽く学びます.
