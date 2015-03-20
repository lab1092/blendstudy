===============================
マクロとして使う
===============================

Blenderは操作の一部をログ出力しています。それらを切り出すことで
マクロのようなものとして使うことができます。


ログが書かれている場所は?
==============================

画面上部のメニューバーの上にあります。隠れているのでメニューバーの
下側を掴んで移動させて表示します。


   .. image:: useasmacro_001.png

ログ出力は以下のように出力されます。
      
  ::

		bpy.ops.mesh.primitive_monkey_add(radius=1, view_align=False, enter_editmode=False, location=(0, 0, 0), layers=(True, False, False, False, False, False, False, False, False, False, False, False, False, False, False, False, False, False, False, False))
		bpy.ops.object.duplicate_move(OBJECT_OT_duplicate={"linked":False, "mode":'TRANSLATION'}, TRANSFORM_OT_translate={"value":(3, 0, 0), "constraint_axis":(True, False, False), "constraint_orientation":'GLOBAL', "mirror":False, "proportional":'DISABLED', "proportional_edit_falloff":'SMOOTH', "proportional_size":1, "snap":False, "snap_target":'CLOSEST', "snap_point":(0, 0, 0), "snap_align":False, "snap_normal":(0, 0, 0), "gpencil_strokes":False, "texture_space":False, "remove_on_cancel":False, "release_confirm":False})
		bpy.context.space_data.context = 'MATERIAL'
		bpy.ops.material.new()
		bpy.context.object.active_material.diffuse_color = (0.8, 0, 0.00109809)
		bpy.context.object.active_material.diffuse_color[2] = 0
		bpy.context.object.active_material.diffuse_color[0] = 1
		bpy.context.object.active_material.diffuse_color = (1, 0, 0)


出力ログをコピーする場合には、以下の操作を行います。

   1. 該当の行を右クリック選択(選択行の色が変わります)
   2. 選択された状態で [Ctrl]+[C] を押してクリップボードにコピーします。


再現用スクリプトとして編集
===========================

上記を少し整理して書くと以下のようになります。 usermacro.py という名前で保存します。

  ::

		import bpy
		
		bpy.ops.mesh.primitive_monkey_add()
		bpy.ops.object.duplicate_move(OBJECT_OT_duplicate={"linked":False, "mode":'TRANSLATION'}, TRANSFORM_OT_translate={"value":(3, 0, 0)})
		bpy.context.space_data.context = 'MATERIAL'
		bpy.ops.material.new()
		bpy.context.object.active_material.diffuse_color = (1, 0, 0)


スクリプトの読み込み、実行
===========================

Blenderのテキストエディタに保存したPythonスクリプトを読み込んで実行します。

テキストエディタにスクリプトを読み込んだ状態でメニューから
Text > Run Script ([Alt]+[P])を実行します。

.. note::
   コマンドラインオプションから保存したファイルを指定して実行させることも可能です。


