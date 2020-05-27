# README

## セットアップ

サイト作成

```shell
hugo new site hugo-diary
```

レポジトリ初期化

```shell
cd hugo-diary
git init
echo '*~' >> .gitignore
echo '*.bak' >> .gitignore
echo '*.orig' >> .gitignore
echo '.env' >> .gitignore
echo 'public' >> .gitignore
```

テーマ設定

```shell
cd themes 
git submodule add git@github.com:AmazingRise/hugo-theme-diary.git
```

サイト設定

```shell
cd ..
cp -pr themes/hugo-diary/exampleSite/{content,config.toml} .
```

config.toml

```toml
baseURL = "https://higebobo.github.io/hugo-diary/"
languageCode = "ja"
title = "Hugo Diary"
theme = "hugo-theme-diary"
```

> github pagesやnetlifyで使う場合はbaseURLのプロトコルはhttpsにすること

Githubレポジトリ作成後

```shell
cp somplace/Makefile
git remote add origin git@github.com:higebobo/hugo-diary.git
git add .
git commit -m 'init'
git push -u origin master
```

## Github Actionsの利用

* .github/workflows/gh-pages.yamlを作成
    * ソースはmasterブランチ
    * 出力はpublicフォルダの内容をgh-pagesブランチ
        * Github>Settings>Gighub Pages>Source>gh-pages branch

## 既存のレポジトリからクローンする場合

```shell
git clone git@github.com:higebobo/hugo-diary.git higebobo-diary
cd higebobo-diary
git submodule update --init --recursive
```

## 使い方

### 投稿

新規投稿

```shell
hugo new posts/hello.md
content/posts/hello.md created
```

編集

```shell
vi content/posts/hello.md
```

## Link

* [Hugo Theme Diary \| Hugo Themes](https://themes.gohugo.io/hugo-theme-diary/)
