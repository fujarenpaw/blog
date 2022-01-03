# Marp Cliを使ってMarkdownファイルをパワーポイント形式に変換してみる

どうも[わや](https://twitter.com/wayawatech)です。

ブログ作って早々気づいたら2年間も放置してました、時が経つのは早いですね。



先日ツイッターを眺めてみると、こんなツイートがありちょうどMarkdownをパワーポイントに変換したいと思っていたのでMarpを使ってみたいと思います。

[vscode Marp](https://twitter.com/Pythonist19/status/1442332335085539337)



なお、この記事ではVisual Studio Codeの拡張機能のMarpではなくCliのMarpを使用します。



## この記事でわかること

- Marp Cliのインストール方法
- Marp Cliの簡単な使い方



## この記事の想定読者レベル

- Windowsユーザー
- Markdownが何となくでもわかる



## 環境構築

[Marpのドキュメント](https://github.com/marp-team/marp-cli)を見るとWin環境ではScoopでインストールができます。

Scoop環境がない場合は、Scoopもインストールしちゃいましょう。



#### Scoopのインストール

コマンドプロンプト上、または`Win + R`キーで`powershell`と打ちpowershellプロンプトで下記のコマンドを打ちます。

```
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser -Force
iwr -useb get.scoop.sh | iex
```

エラーメッセージが出た場合は、TLS1.2の有効化してから、再度コマンドを打ってみてください。

> iwr : 要求は中止されました: SSL/TLS のセキュリティで保護されているチャネルを作成できませんでした

```
// TLS1.2有効化
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
```



####  Marp Cliのインストール

コマンドプロンプト上で、下記のコマンドを打ちます。

```
scoop install marp
```



## 使い方

MarpのGithubに[デモ用のMarkdownファイル](https://github.com/marp-team/marp-cli/blob/main/docs/demo.md)があるのでダウンロードしてきましょう。

ダウンロード出来たら、コマンドプロンプトでMarkdownファイルのあるフォルダへ移動し、下記のコマンドを打ちます。

```
marp --pptx demo.md
```

変換が完了するとこんな感じのパワーポイントが生成できました。

![marpCliDemo](C:\Users\hoge\Documents\GitHub\blog\img\marpCliDemo.PNG)



パワーポイント形式のほかに、HTML, PDF, PNG, JPEG形式の変換ができるようです。





## 終わりに

Markdownは書きやすく便利なものの、僕の周りでは詳しい人ばかりではなく 資料はパワーポイントで と言われる事も少なくなかったので、Markdownからパワーポイントに変換できるMarp Cliを使ってみました。

定型的な資料作成は、元となるMarkdownをプログラムで生成してパワーポイントに変換して提出、のようにして楽していきたいですね。







