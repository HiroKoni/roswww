# Pub/Subしよう
では、roslibjsを使って、ブラウザからROSのTopicをSubscribe, Publishしてみましょう。

ブラウザ上で動的に動作するプログラムを書くには、JavaScriptという言語を使用します。roslibjsは、このJavaScriptからROSの機能を利用できるようにするライブラリです。このライブラリのファイルを、[roslibjs.min.js](https://github.com/RobotWebTools/roslibjs)をダウンロードすることで入手しましょう。

以下の3ファイルを、`www`ディレクトリに配置します。`index.html`と`script.js`は、講習資料の`sample/pubsub`にあるものをコピーしましょう。
- index.html
- script.js
- roslib.min.js

HTMLの`<head>`タグ内に、以下のように記述します。これにより、`index.html`をブラウザで開いたときに、`roslib.min.js`と`script.js`が読み込まれるようになります。

```html
<script src="./roslib.min.js" defer></script>
<script src="./script.js" defer></script>
```

あなたのプログラムは、`script.js`に書き込んでいきましょう。

では、[公式ドキュメント](https://wiki.ros.org/roslibjs/Tutorials/BasicRosFunctionality)を参考に、ブラウザから適当なTopicをSubscribe, Publishしてみましょう。
ただし、ドキュメントでは変数宣言に`var`を用いていますが、今日日使わない古い記法なので、`const`または`let`を使うようにしましょう。基本的にはなんでもかんでも`const`で大丈夫です。この文書はJavaScriptの詳細には立ち入らないので、詳しい解説は省略します。

## トピックの記述
`rosmaster`との接続などは、前述の公式ドキュメントを参照してください。ここでは、トピック周りの記述についてのみ説明します。
`roscpp`との相違点として特筆すべきこととして、`roslibjs`では、publisherとsubscriberを同じ`Topic`構造体で扱うことです。ですから、以下のようなコードで、`/cmd_vel`というTopicに対して、PublishとSubscribeを同時に行うことができます。
```js
var cmd_vel = new ROSLIB.Topic({
ros : ros,
name : '/cmd_vel',
messageType : 'std_msgs/Int32'
});
```

### Publish
```js
const vel = new ROSLIB.Message({
    data: 50
})
cmd_vel.publish(angle);
```
メッセージは、ROSの`.msg`ファイルに書いてある定義の中身の通りに書きましょう。今回は`std_msgs/Int32`を使っているので、`data`という変数に値を入れています。標準型の`.msg`ファイルは、[こちら](https://docs.ros.org/en/api/std_msgs/html/index-msg.html)から確認できます。

### Subscribe
```js
cmd_vel.subscribe(function (message) {
    // ここに、Subscribeしたときの処理を書く
    console.log('Received message on ' + cmd_vel.name + '. It says : ' + message.data);
});
```


## 参考サイト
- [roslibjsのリファレンス](https://robotwebtools.github.io/roslibjs)

[前（パッケージへの導入）](integration.md)