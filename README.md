# The adxeproject, another fork of Cocos2d-x (4.0)

## Purpose:
**Make Cocos2d-x better**

## New project (python2 or python3 works)
* Cpp Project: ```adxe new -p cppgame.c4games.com -d D:\dev\projects\ -l cpp --portrait CppGame```
* Lua Project: ```adxe new -p luagame.c4games.com -d D:\dev\projects\ -l lua --portrait LuaGame```

## Android: apk min size release (adxe 1.0 beta1, only contains armv7a arch)
- CppGame-release.apk (3.34MB)

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

## 2D Physics Engines Informations:
- **Chipmunk2D** engine (Cpp Test: Chipmunk2D - Basic) 
  - Use class PhysicsSpriteChipmunk2D 
- **Box2D** engine (Cpp Test: Box2D - Basic)
  - Use class PhysicsSpriteBox2D 
- **adxe 2D physics integration API** (Cpp Test: Node: Physics)
  - It using Chipmunk2D as internal 2D physics engine

- **Outdated/Abandom/Cocos2d-x**:
  - class PhysicsSprite: Be only part of the adxe for backwards compatibility with Cocos2d-x. Can be use with CC_ENABLE_BOX2D_INTEGRATION 1 (using Box2D) or with CC_ENABLE_CHIPMUNK_INTEGRATION 1 (using Chipmunk2D)

## Chipmunk2D/Box2D Testbeds:
The goals where: 
- Using the original source files of the testbeds as possible. 
- Don't make the source files perfect adapted to adxe (it's not needed for adxe).
- Give "a short view" to the Testbeds examples.
