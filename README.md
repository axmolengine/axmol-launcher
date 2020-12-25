# Welcome to the engine-x wiki, another fork of cocos2d-x-4.0

## Purpose:
**Make cocos2d-x better**

## gitee repo:  
https://gitee.com/c4games/engine-x  (because gitee repo sync failed with too large, please upstream github always)

## New project (python2 or python3 works)
* Cpp Project: ```cocos new -p cppgame.c4games.com -d D:\dev\projects\ -l cpp --portrait CppGame```
* Lua Project: ```cocos new -p luagame.c4games.com -d D:\dev\projects\ -l lua --portrait LuaGame```

## apk min size release(only contains armv7a arch)
- CppGame-release.apk(3.34MB)

## Choose render backend
- By default
  - win32 and linux: DesktopGL
  - android: GLES
  - osx/ios: Metal
- Pass -DCC_COMPAT_GL=TRUE to CMake
  - win32: Google ANGLE with DirectX
  - linux: DesktopGL
  - osx: NSGL
  - ios: GLES
