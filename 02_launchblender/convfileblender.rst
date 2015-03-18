========================================================
BlenderでOBJファイルをFBXに自動変換して出力するサンプル
========================================================

Blenderの起動時に指定したOBJファイルを自動的にインポートし、
FBXファイルを出力するサンプルです。


   :Version: 2.73a
   :キーワード: Python,FBX ,OBJ,ファイルフォーマット変換
   :OS: Windows , OS X 





サンプルコード
===================================

いろいろ考慮すべき部分を端折ってますので'サンプル'ということで。

convfileblender.bat
-------------------------

   ::

      c:\blender\blender.exe -P C:\Users\username\desktop\testconv.py -b -- %1

convfileblender.scpt
-------------------------

   ::

		on main(input)
			try
				do shell script "/Applications/Blender274RC1/blender.app/Contents/MacOS/blender -P ~/Desktop/testconv.py -b --" & space & input
			end try
		end main
		
		on open argv
			repeat with aFile in argv
				main(quoted form of POSIX path of aFile)
			end repeat
		end open
		
		on run
			main(quoted form of POSIX path of (choose file))
		end run

testconv.py
-------------------------

   ::

		import bpy
		import sys
		import os
		
		def delete_all():
		    for item in bpy.context.scene.objects:
		        bpy.context.scene.objects.unlink(item)
		
		    for item in bpy.data.objects:
		        bpy.data.objects.remove(item)
		
		    for item in bpy.data.meshes:
		        bpy.data.meshes.remove(item)
		
		    for item in bpy.data.materials:
		        bpy.data.materials.remove(item)
		
		def convert_file(filepath):
		    basename = filename = fileext = ext = outpath =''
		    dirname = os.path.dirname(filepath)
		    basename = os.path.basename(filepath)
		    (filename,fileext) = os.path.splitext(basename)
		    
		    ext = fileext.lower()
		    
		    if os.path.isfile(filepath):
		
		        # .obj -> .fbx
		        if ext =='.obj':
		            bpy.ops.import_scene.obj(filepath=filepath)
		            
		            outpath = os.path.join(dirname,filename+".fbx")
		            bpy.ops.export_scene.fbx(filepath=outpath)
		
		        else:
		            None
		
		
		if __name__ == "__main__":
		    delete_all()
		    convert_file(filepath=sys.argv[-1])
		


[EOF]