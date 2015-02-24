===============================
アポロチョコを作成する
===============================

`少しゆるめなBlender勉強会開催後＋ <https://lab1092.wordpress.com/2015/02/01/yurublend/>`__
で紹介した「アポロチョコ」のモデリング。

   :Version: 2.73a
   :キーワード: ループ選択、マテリアル、スムース化、チェッカー選択、ナイフツール、ループカット、エッジスライド

完成図
===================================


.. image:: apollo_001.png


目標は「それなりに見えること」。今回の手順ではソリッドカラーのマテリアルを割り当てるのみで、
シーンセッティングまではしません。


開始
===================================

デフォルトキューブを消す
-------------------------

デフォルトキューブを消します。Cubeを選択した状態で[X]キーを押して削除します。


.. image:: apollo_002.png

.. image:: apollo_003.png

.. image:: apollo_004.png


新規オブジェクトの作成
----------------------

Coneを追加します。その前に、追加する位置はグローバル座標原点にしたいので、
3Dカーソル(赤白の輪っか)を原点に移動させます。ずれている場合には[Shift]+[S]、
メニューから”Cursor to Center”を選択。

.. image:: apollo_005.png

メッシュの追加。[Shift]+[A]キーを押したメニューからMesh >Cone と選んで、”Cone”を追加します。

.. image:: apollo_006.png

.. image:: apollo_007.png


メッシュ編集
--------------------

マウスホイールでコーンの表示を大きくします。次にエディットモードにして、底面を見える位置に視点を変更します。

.. image:: apollo_008.png

.. image:: apollo_009.png

.. image:: apollo_010.png


[A]キーで選択解除、[Alt]+[右クリック]でループ選択します。その状態で3Dビューのメニューから
Select > Checker Deselect を選択し、底部分の頂点が飛び飛びに選択されている状態にします。

.. image:: apollo_011.png

.. image:: apollo_012.png

選択状態を保持し、[S]キーを押してサイズを変更します。すると星型のような形になります。そこで確定。

.. image:: apollo_013.png

[A]キーで全ての頂点の選択を解除しておきます。

[K]キーを押し、[左クリック]を1回押してマウスを動かします。

.. image:: apollo_014.png

.. image:: apollo_015.png

直線が現れたところで[Z]キーを押し、非表示面も切る対象とします。

.. image:: apollo_016.png

[Ctrl]+[左クリック]で切断する場所を仮確定にします(辺の中点)。[Enter]キーで確定。

.. image:: apollo_017.png

.. image:: apollo_018.png

エッジスライド([G],[G])で、選択中の頂点を上に持ち上げます。

.. image:: apollo_019.png

Subdivision Surfaceモディファイアを適用します。
プロパティウィンドウのSpufaceボタンを押して出てくるAdd ModifierからSubdivision Surfaceを選択。

.. image:: apollo_020.png

.. image:: apollo_021.png

.. image:: apollo_022.png

ツールシェルフのSmoothボタンをおして面をスムーズに表示、Subdivision Surfaceの細分化のレベルを上げておきます。

.. image:: apollo_023.png

.. image:: apollo_025.png

底部分の星型を出すために、[Ctrl]+[R]でループカットを行います。[Ctrl]+[R]を押した後、
マウスを動かしてピンクの線が出てくるところで[左ボタン]クリックして、下方向にエッジを移動させて確定します。

.. image:: apollo_027.png



.. image:: apollo_028.png

再度、[Ctrl]+[R]でループカットを行います。位置は適当に。ここがストロベリーチョコとミルクチョコの境界です。

.. image:: apollo_029.png

.. image:: apollo_030.png

上の頂点に丸みが欲しいので、頂点を少し下げます。[G],[Z]か、マニピュレーターの青い矢印をドラッグするかで、頂点を移動します。

.. image:: apollo_031.png

.. image:: apollo_032.png

.. image:: apollo_034.png

.. image:: apollo_035.png

マテリアルの追加・割り当て
---------------------------------

プロパティウィンドウのマテリアルボタンを押し、マテリアルの設定をはじめます。
マテリアルスロットの+ボタンを押して追加、さらに[+ New]ボタンを押して、
マテリアルを追加します。最初に設定したマテリアルはそのオブジェクトのデフォルトとして適用されます。

.. image:: apollo_036.png

.. image:: apollo_037.png

.. image:: apollo_038.png

.. image:: apollo_039.png

マテリアルカラーを設定します。

.. image:: apollo_040.png

.. image:: apollo_041.png


.. image:: apollo_042.png

次の作業のために下半分を選択します。limitvisibleボタンを押して、
隠れた部分の頂点も選択できる状態にし、[B]キーの領域選択で選択状態にします。

.. image:: apollo_043.png

.. image:: apollo_044.png

.. image:: apollo_045.png

マテリアルスロットの+ボタンを押して２つ目のマテリアルスロットを追加、マテリアルを追加します。

.. image:: apollo_046.png

.. image:: apollo_047.png

.. image:: apollo_049.png

2つ目のマテリアルを割り当てます。マテリアルスロットの下、Assignボタンを押します。
下半分の色が2番目のマテリアル色に変更されました。

.. image:: apollo_050.png

.. image:: apollo_051.png

一度エディットモードからオブジェクトモードにし、アングルを変えて確認します。
今のままでは縦に長いので、エディットモードで全選択([A])、[S]、[Z]でサイズ変更します。

.. image:: apollo_052.png

.. image:: apollo_053.png

完成です。

.. image:: apollo_054.png



[EOF]