========================================================
OBJまたはFBXファイルを起動時に自動で開くサンプル
========================================================

Blenderの起動時に指定したOBJファイルを自動的にインポートするサンプルです。


   :Version: 2.73a
   :キーワード: Python,FBX ,OBJ
   :OS: Windows , OS X 



サンプルコード
===================================


launchblender.bat
-------------------------

   ::

      c:\blender\blender.exe -P C:\Users\username\desktop\test.py -- %1

launchblender.scpt
-------------------------

   ::

		on main(input)
			try
				do shell script "/Applications/Blender274RC1/blender.app/Contents/MacOS/blender -P ~/Desktop/test.py --" & space & input
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

test.py
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


		def launch_file(filepath):
			basename = filename = fileext = ext =''
			basename = os.path.basename(filepath)
			(filename,fileext) = os.path.splitext(basename)
	
			ext = fileext.lower()
	
			if os.path.isfile(filepath):

				if ext =='.fbx':
					bpy.ops.import_scene.fbx(filepath=filepath,automatic_bone_orientation=True)

				elif ext =='.obj':
					bpy.ops.import_scene.obj(filepath=filepath,axis_forward='-Z', axis_up='Y' )

				else:
					None


		if __name__ == "__main__":
			delete_all()
			launch_file(filepath=sys.argv[-1])


		


[EOF]