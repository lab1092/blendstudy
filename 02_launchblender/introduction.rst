========================================================
Blender起動時オプション
========================================================

Blenderの起動時にオプションを渡すことで、自動化させたり、より高度なことが可能になります。


コマンドラインからの実行
===================================

コマンドラインオプションについて:

   * https://www.blender.org/manual/render/workflows/command_line.html

``blender --help`` などしても確認できます。

hoge.blendを読み込む
-------------------------

.blendファイルを読み込んで開くことが可能です。

   ::

      c:\blender\blender.exe hoge.blend

バックグラウンド実行
-------------------------

バックグラウンド実行させることでblenderのGUIを開くことなく実行させることが可能です。
セットアップ済みシーンファイルのレンダリングを自動で行わせたい場合などに使用できます。

10フレーム目を出力:

   ::

      blender -b file.blend -f 10

アニメーションを出力:

   ::

      blender -b file.blend -a




スクリプト実行
-------------------------

特殊な処理を行いたい場合に、Pythonスクリプトを使用することも可能です。
:doc:`launchblender` や :doc:`convfileblender` のようなことが可能です。

起動時にhoge.blend 内のテキスト、 testpy を使用する例:

  ::

      $ blender hoge.blend -P testpy



起動時に外部ファイル test.py を使用する例:

  ::

      $ blender hoge.blend -P test.py





[EOF]