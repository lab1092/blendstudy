===============================
Bpy tips
===============================


ユーザー操作
============

blenderを終了する
------------------------------------------

   ::
   
		bpy.ops.wm.quit_blender()

オブジェクト操作
========================

モンキーを追加する
------------------------------------------

Add Mesh > Monkey と同じことを行います。

   ::
   
		bpy.ops.mesh.primitive_monkey_add()

選択されたオブジェクトを取得する
----------------------------------

Blenderの画面上で「アクティブ」と「選択されている」という二つの状態があります。

たとえば'Camera', 'Empty', 'Lamp'のオブジェクトがあるとして…

   ::

		>>> bpy.data.objects
		<bpy_collection[3], BlendDataObjects>

		>>> bpy.data.objects.keys()
		['Camera', 'Empty', 'Lamp']

アクティブなオブジェクトは以下で取得可能です。

   ::

		>>> bpy.context.object
		bpy.data.objects['Empty']

選択されたオブジェクトは以下で取得可能です。

   ::

		>>> bpy.context.selected_objects
		[bpy.data.objects['Empty'], bpy.data.objects['Camera']]

ちなみに、選択可能なオブジェクトはどうやったら確認できるか、というと

   ::

		>>> bpy.context.selectable_objects
		[bpy.data.objects['Empty'], bpy.data.objects['Camera'], bpy.data.objects['Lamp']]


オブジェクトを選択する
-----------------------

スクリプトからオブジェクトを選択することも可能です。

3Dビューのメニュー、Select > Select All by Type... > Empty と同等のコマンド

   ::

		>>> bpy.ops.object.select_by_type(type='EMPTY')
		{'FINISHED'}

オブジェクトの選択状態を保持するプロパティを変更して選択状態にします。

   ::

		>>> bpy.data.objects['Camera'].select
		False

		>>> bpy.data.objects['Camera'].select = True
		>>> bpy.data.objects['Camera'].select
		True




オブジェクトの親を取得する
--------------------------



   .. image:: useasmacro_001.png


(少し冗長に書きます)

   ::

		>>> bpy.data.objects
		<bpy_collection[3], BlendDataObjects>

		>>> bpy.data.objects.keys()
		['Camera', 'Empty', 'Lamp']

		>>> bpy.data.objects['Camera']
		bpy.data.objects['Camera']

		>>> bpy.data.objects
		<bpy_collection[3], BlendDataObjects>

		>>> bpy.data.objects.keys()
		['Camera', 'Empty', 'Lamp']

		>>> bpy.data.objects['Camera']
		bpy.data.objects['Camera']

		>>> bpy.data.objects['Camera'].parent
		bpy.data.objects['Empty']

		>>> bpy.data.objects['Camera'].parent_type
		'OBJECT'

