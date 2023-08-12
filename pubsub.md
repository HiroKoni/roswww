# Pub/Subしよう
では、roslibjsを使って、ブラウザからROSのTopicをSubscribe, Publishしてみましょう。

ブラウザ上で動的に動作するプログラムを書くには、JavaScriptという言語を使用します。

[roslibjs.min.js](https://github.com/RobotWebTools/roslibjs)を入手しましょう。

以下の3ファイルを、`www`ディレクトリに配置します。
- index.html
- script.js
- roslib.min.js

HTMLの`<head>`タグ内に、以下のように記述します。

```html
<script src="./roslib.min.js" defer></script>
<script src="./script.js" defer></script>
```

あなたのプログラムは、`script.js`に書き込みます。
では、[公式ドキュメント](https://wiki.ros.org/roslibjs/Tutorials/BasicRosFunctionality)を参考に、ブラウザから適当なTopicをSubscribe, Publishしてみましょう。


## 参考サイト
- https://docs.ros.org/en/indigo/api/roswww/html/
- https://robotwebtools.github.io/roslibjs

[前（パッケージへの導入）](integration.md)