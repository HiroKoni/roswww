# roswwwのパッケージへの導入
それでは、`roswww`を用いて、パッケージにウェブサーバーの機能を追加してみましょう。

`package.xml`に`roswww`への依存関係を追加します。
```xml
<exec_depend>roswww</exec_depend>
```

`launch`ファイルを作成し、`roswww`と`rosbridge_server`を起動させるよう設定します。既存のlaunchファイルに追記してもいいですし、新しくlaunchファイルを作成してもいいです。
```xml
<arg name="port" default="8085"/> <!-- Apacheのデフォルトポートは避ける（不通は80） -->
<arg name="webpath" default="www"/> <!-- ウェブサーバーのルートディレクトリにするフォルダへの相対パス -->
<arg name="use_roswww" default="true" />


<!-- 以下はコピペするだけでOK -->
<include if="$(arg use_roswww)" file="$(find rosbridge_server)/launch/rosbridge_websocket.launch" />
<include if="$(arg use_roswww)" file="$(find roswww)/launch/roswww.launch">
  <arg name="port" value="$(arg port)"/>
  <arg name="webpath" value="$(arg webpath)"/>
</include>
```

パッケージの中に`www`フォルダを作成しましょう。このフォルダ（厳密には、launchファイルで`webpath`に設定したフォルダ）が、ウェブサーバーのルートディレクトリになります。講習資料の`sample/simple_static`ディレクトリの中身を、`www`フォルダにコピーしてみましょう。

`roslaunch`した後、`http://localhost:8085/%YOUR_PACKAGE_NAME%` にアクセスしてみましょう。`www/index.html`の内容が表示されているはずです。

このサンプルは、静的なコンテンツでしかありませんが、`roslibjs`を使うことで、topic通信など、ROSの機能が使えます。


## 参考サイト
- https://docs.ros.org/en/indigo/api/roswww/html/
- https://robotwebtools.github.io/roslibjs

[前（セットアップ）](setup.md)
　[次（Pub/Subしよう）](pubsub.md)