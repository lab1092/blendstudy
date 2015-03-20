===================================
Pythonインタラクティブコンソール
===================================

[Todo]コンソール関連情報



import thisを実行
-----------------

'Zen of Python'を表示します。

   ::

		>>> import this
		The Zen of Python, by Tim Peters

		Beautiful is better than ugly.
		Explicit is better than implicit.
		Simple is better than complex.
		Complex is better than complicated.
		Flat is better than nested.
		Sparse is better than dense.
		Readability counts.
		Special cases aren't special enough to break the rules.
		Although practicality beats purity.
		Errors should never pass silently.
		Unless explicitly silenced.
		In the face of ambiguity, refuse the temptation to guess.
		There should be one-- and preferably only one --obvious way to do it.
		Although that way may not be obvious at first unless you're Dutch.
		Now is better than never.
		Although never is often better than *right* now.
		If the implementation is hard to explain, it's a bad idea.
		If the implementation is easy to explain, it may be a good idea.
		Namespaces are one honking great idea -- let's do more of those!

		>>> 

クラスメンバや関数の表示
-------------------------

インタラクティブコンソールでは[Ctrl]+[Space]の補完で表示させることもできますが、
dir() を使って表示できます。

   ::
      
		>>> bpy.data.meshes.
							as_bytes(
							bl_rna
							data
							find(
							foreach_get(
							foreach_set(
							get(
							id_data
							is_updated
							items(
							keys(
							new(
							new_from_object(
							path_from_id(
							remove(
							rna_type
							tag(
							values(
		>>> dir(bpy.data.meshes)
		['__bool__', '__contains__', '__delattr__', '__delitem__', '__doc__', '__doc__', '__getattribute__', '__getitem__', '__iter__', '__len__', '__module__', '__setattr__', '__setitem__', '__slots__', 'bl_rna', 'find', 'foreach_get', 'foreach_set', 'get', 'is_updated', 'items', 'keys', 'new', 'new_from_object', 'remove', 'rna_type', 'tag', 'values']

		>>> 






