============================================
Blenderで使えるモジュールを調べてみよう
============================================

http://lab1092.blog.jp/archives/51891633.html から。

Blenderで使えるモジュールを調べてみよう
================================================

今回はBlenderのPythonで使えるモジュールを調べてみることにします。
やっていることはBlenderっぽくないですが、「Pythonの基本的なところを学習する環境としても使える」ということをわかってもらえるといいんじゃないでしょうか。

以下のBlog記事で紹介されているものをBlender上のPython Interactive console上で、というわけですね。

   * `利用可能なモジュール一覧を取得する <http://tell-k.hatenablog.com/entry/2012/02/04/131805>`__

ロード済みモジュールを確認
-----------------------------------

ロード済みモジュールを確認するには、 ``sys.modules.keys()`` を実行します。

   ::
   
      >>> import sys
      >>> sys.modules.key()
      


利用可能なモジュールを確認
-----------------------------------

Blenderに同梱されているPythonのライブラリは、「標準ライブラリ(流石にTKはありません)」+αです。これを一覧で確認します。

   ::
   
      >>> buf=[]
      >>> for m in pkgutil.iter_modules():
      ...     buf.append(m[1])
      ...     
      >>> buf.sort()
      >>> buf

これで確認してみると…。xmlrpcとかnumpy…えっ?numpy???


「何をするものか」を確認
-------------------------------------

さて、一覧が取得できても、個々に「何をするもの」かまでは名前からだけではわかりません。そこで help() 関数。 以下のように実行してみます。

   ::
   
      >>> import xmlrpc
      >>> help(xmlrpc)
      Help on package xmlrpc:
      NAME
          xmlrpc - # This directory is a Python package.
      PACKAGE CONTENTS
          client
          server
      FILE
          /Applications/Blender/blender.app/Contents/Resources/2.74/python/lib/python3.4/xmlrpc/__init__.py

パッケージやモジュール、関数に help() 関数を使ってみると説明が表示されるので良さげです。

ここで、落とし穴。 BlenderのInteractive Python Consoleは表示できる行が決まっていて(デフォルト256行)、help(numpy) とか help(unittest) とか長い内容の表示は全部できずに(先頭が)切れてしまいます。これを変更するには Console Scrollback の値を増やします。

    * 参考: `How to increase the scrollback history of the Python console/terminal within Blender? <http://blender.stackexchange.com/questions/5779/how-to-increase-the-scrollback-history-of-the-python-console-terminal-within-ble>`__


[Add-on]自分で作ったAdd-onに追加のモジュールが使えるかどうかで機能を変える
-----------------------------------------------------------------------------------------------------

Pythonは自身で書いた .py ファイルをモジュールとして使用することが可能です。Add-onで、特定のパッケージまたはモジュールがインポート可能な時のみ特定機能を使用可能にする、というのを `submitwordpress.py <https://github.com/lab1092/submitwordpress>`__ で使っていたりします。

   ::
   
      kanaflg = False
      # import romankanatbl as extention
      try:
          import romakanatbl.romakanatbl as rk
          kanaflg = True
          print("[SubmitWordPress] romankana extention is available.")
      except:
          print("[SubmitWordPress] no romankana extention.")

try文の中で import 文を実行して登録できるかをやっているわけですね。


あと、「モジュールとして登録できるファイルは一体どこに？」とかは最初に紹介したBlog記事を参考にしてスクリプトを実行するか、 メニュー、Help > System Info で出力されるテキストから、 Directories あたりの項目をチェックしておけばいいんではないでしょうか。 
