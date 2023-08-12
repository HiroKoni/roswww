# roswww講習資料

この講習では、`roswww`, `roslibjs`といったツールを使って、WEBブラウザからROS-basedなロボットを操作できるクライアントを開発することを目指します。
この講習の終了時に、受講者は、以下のような状態になっていることが期待されます。

- Webアプリケーションの開発に不可欠な、HTML, CSS, JavaScriptの基礎知識を習得している
- ブラウザからTopicのSubscribe, Publishができる
  - ボタンを押すことで、TopicのPublishができる
  - Subscribeした内容に応じ、画面の表示を変化させられる

## 前提
- ROS noetic の環境
- ROSの基本的な知識
  - Topic, Message, Node, Launchファイルなど
- 基本的なプログラミングの知識（言語問わず）
  - クラスやオブジェクトの概念についての基本理解が望まれる

## リスト
1. [概要（このページ）](readme.md)
2. [セットアップ](setup.md)
3. [パッケージへの導入](integration.md)
4. [Pub/Subしよう](pubsub.md)


## 参考サイト
- [roswwwのドキュメント](https://docs.ros.org/en/indigo/api/roswww/html/)
- [roslibjsのリファレンス](https://robotwebtools.github.io/roslibjs)