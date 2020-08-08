---
layout: post
title: "Raspberry PiにApache 2とPHPをインストールする"
tag: [環境構築, Web]
---

Raspberry Pi を家庭用 Web サーバのように使用して、個人的なアプリケーションを配置したりすることがあると思われる。
あるいは、Web 構築の学習などに使うことも考えられる。
それらの用途では、Apache 2 と PHP という構成は依然として広く使われているだろう（もちろん Node.js などを好む人もいる）。
PHP による動的 Web ページは仕組みが単純でスクリプティングも簡単でありながら、そこそこ高速に動作することも魅力の 1 つである。
しかし、それらの環境構築は稀にしかやらず、すぐ忘れてしまうので簡単な手順を書き残す（個人ディレクトリ下の PHP 有効化方法などを忘れやすい）。
これからやる人の参考になれば幸い（これを見て Raspberry Pi 4 を買うのも良いだろう）。

| モデル                  | OS                                    |
| :---------------------- | :------------------------------------ |
| Raspberry Pi 3 Model B+ | Raspberry Pi OS (32-bit) with desktop |

## Apache 2 のインストール

`apt` コマンドのみで完結する。

```sh
sudo apt update
sudo apt install apache2
```

バージョン確認のコマンドで成否を確かめられる。

```sh
apachectl -v
```

この段階で、HTTP でホストに接続すると Apache 2 Debian Default Page が出力されるはずである。

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
apt search php7.2
apt search php7.3
apt search php7.4
```

バージョンを決めたらインストールする。

```sh
sudo apt install php7.3
```

インストールした時点ですでに Apache の PHP スクリプティング MOD が有効化されていると思われる。

## ユーザディレクトリでも PHP を有効化

デフォルトでは `~/public_html` 以下の PHP スクリプティングは無効になっている。
`php?.?.conf` 内の無効化を行っている部分をコメントアウトする。

```sh
# 他エディタでも良い
sudo vi /etc/apache2/mods-enabled/php7.3.conf
```

最後に Apache を再起動して、ここまでの変更を反映する。

```sh
sudo systemctl restart apache2
```
