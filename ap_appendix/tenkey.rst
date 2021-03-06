﻿===============================
Blenderとテンキーの話
===============================

Blenderは「テンキーがないと使えない」?
===============================================

Blenderでは視点の切り替えに使用するテンキー。ただ、ノートPCだと、テンキーを省いた
キーボードレイアウトであることが多く、「どうすればいいの?」となることがあります。

テンキーがない場合にどうするかということについて書いていきたいと思います。

1.外部接続のテンキーを購入する
-------------------------------------

はい、ハードウェアを入手します。「無ければ追加購入する」、これが王道です(にっこり

   * `ノートPCなのでテンキーが使えないのですが <http://blenderfaq.blender.jp/oldfaq/problem/noto-pcna-node-tenki-ga-tsukae-nai-no-desu-ga>`_

有線(USB)、無線などの接続方法があり、ものによってはドライバーのインストールが必要なもの
もあります。

2.'Emulate Numpad'機能を有効にする
-------------------------------------

ユーザープリファレンス画面の'Emulate Numpad'を有効にすることで、キーボード上段の
数字キーをテンキー操作に割り当てます。

   +---+----------------------------------+
   | 1 | フロントビュー                   |
   +---+----------------------------------+
   | 3 | サイドビュー                     |
   +---+----------------------------------+
   | 7 | トップビュー                     |
   +---+----------------------------------+
   | 0 | カメラビュー                     |
   +---+----------------------------------+

レイヤー切り替えの代わりに視点切り替えにするわけですね。

選択されたものを表示'View Selected'([テンキー.]) についてどこに割り当てようか、と思案のしどころでしょうか。


参照:

   * http://www.blender.org/manual/preferences/input.html#numpad-emulation
   * http://www.blender.org/manual/getting_started/installing_blender/configuration.html#input
   
   
3.'Pie Menus' Add-onを使う
-------------------------------------

Blender 2.72 から 'Pie Menus' が標準Add-onで付いてくるようになりました。
ただし、デフォルトでは無効の設定になっているので、これを有効にする必要があります。

   * :doc:`piemenufrom272`


4.'Blender keypad'を使う
-------------------------------------

「物理的なテンキー」を別途購入するまでもないかな、という場合に'Blender keypad'が
使えるかもしれません。iPhone/iPad/iPot touchと無線ネットワーク接続できる環境が必要です。

   * Blender KeyPad 
      * https://itunes.apple.com/us/app/blender-keypad/id430784289?mt=8

5. '3D Navigation' Add-onを使う
-------------------------------------

標準Add-onの '3D Navigation' を有効にすると 3Dビューのツールシェルフに
'Navigation'タブが出現します。そのタブ内のボタンでビュー操作が可能です。

