# セットアップ

ROS noeticの環境が構築されていることを前提とします。
また、各コマンドは、Ubuntu 20.04を想定しています。

## roswwwのインストール
```bash
$ sudo apt update
$ sudo apt install ros-noetic-roswww
```

### インストールの確認
roswwwに含まれるサーバーを実行してみましょう。
```bash
$ roslaunch roswww roswww.launch
```
成功した場合、
```
Webserver successfully started on port %PORT_NUMBER%
```
という内容を含むメッセージが表示されます。
`http://localhost:%PORT_NUMBER%/`に、ブラウザからアクセスしてみましょう。例えば、表示されたポート番号が8085（デフォルトではこの番号のはずです）の場合、http://localhost:8085/ にアクセスします。起動に成功すると、
```
ROS web server successfully started.
```
とブラウザに表示されます。

## WEB開発環境
HTML, CSS, JavaScriptは、ブラウザさえあればコンパイルする必要もなく動作するので、エディタさえあれば開発できます。
エディタは何でもいいのですが、個人的にはVisual Studio Codeがおすすめです。


## 参考サイト
- https://docs.ros.org/en/indigo/api/roswww/html/
- https://robotwebtools.github.io/roslibjs


 [次（パッケージへの導入）](integration.md)