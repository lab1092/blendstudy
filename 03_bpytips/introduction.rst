===============================
イントロダクション
===============================

[ToDo]Blender Pythonについて簡単な説明を書く


Blenderが使っているPythonのバージョンは?
------------------------------------------

Pythonインタラクティブコンソールで確認できます。以下だと"3.4.2"ですね。


   ::

		PYTHON INTERACTIVE CONSOLE 3.4.2 (default, Nov 25 2014, 12:01:44)  [GCC 4.2.1 Compatible Apple LLVM 6.0 (clang-600.0.54)]

		Command History:     Up/Down Arrow
		Cursor:              Left/Right Home/End
		Remove:              Backspace/Delete
		Execute:             Enter
		Autocomplete:        Ctrl-Space
		Zoom:                Ctrl +/-, Ctrl-Wheel
		Builtin Modules:     bpy, bpy.data, bpy.ops, bpy.props, bpy.types, bpy.context, bpy.utils, bgl, blf, mathutils
		Convenience Imports: from mathutils import *; from math import *
		Convenience Variables: C = bpy.context, D = bpy.data


インタラクティブコンソールで以下のようにしても確認は可能です。

そんなに頻繁に確認するわけでもない(というかPy3かどうかくらいの厳密さで十分)ので、
画面の操作でエディタータイプを変更して表示させるだけでいいかと。

   ::
   
		>>> import sys
		>>> sys.version
		'3.4.2 (default, Nov 25 2014, 12:01:44) \n[GCC 4.2.1 Compatible Apple LLVM 6.0 (clang-600.0.54)]'







   

