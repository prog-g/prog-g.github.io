---
layout: post
title: "Raspberry PiにApache 2とPHPをインストールする"
tag: [環境構築, Web]
---

稀にしかやらず、すぐ忘れてしまうので書き残す。
これからやる人の参考になれば幸い。

| モデル                  | OS                                    |
| :---------------------- | :------------------------------------ |
| Raspberry Pi 3 Model B+ | Raspberry Pi OS (32-bit) with desktop |

## Apache 2 のインストール

`apt` コマンドのみで完結する。

```sh
sudo apt install apache2
```

バージョン確認のコマンドで成否を確かめられる。

```sh
apachectl -v
```

ここで、HTTP でホストに接続すると Apache 2 Debian Default Page が出力されるはずである。

## ユーザごとの公開ディレクトリを有効にする

`~/public_html` にドキュメントを配置して、`http://{host}/~{user}` でアクセスできるようにする。

```sh
sudo a2enmod userdir
```

## PHP のインストール

こちらも `apt` コマンドのみで完結させられる。

まず、リポジトリに存在する最新のバージョンを調べる。
バージョンを適当に指定して、パッケージがあるか調べる。

```sh
# 検索の例
apt-cache search php7.2
apt-cache search php7.3
apt-cache search php7.4
```

バージョンを決めたらインストールする。

```sh
sudo apt install php7.3
```

## ユーザごとの公開ディレクトリでも PHP を有効化

デフォルトでは `~/public_html` 以下の PHP スクリプティングは無効になっている。
`php7.3.conf` 内の無効化を行っている部分をコメントアウトする。

```sh
sudo vi /etc/apache2/mods-enabled/php7.3.conf
```

最後に Apache を再起動して、ここまでの変更を反映する。

```sh
systemctl restart apache2
```
