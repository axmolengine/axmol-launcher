# The adxeproject, another fork of Cocos2d-x (4.0)

## Purpose:
**Make Cocos2d-x better**

## New project (python2 or python3 works)
* Cpp Project: ```adxe new -p cppgame.c4games.com -d D:\dev\projects\ -l cpp --portrait CppGame```
* Lua Project: ```adxe new -p luagame.c4games.com -d D:\dev\projects\ -l lua --portrait LuaGame```

## Android: apk min size release (only contains armv7a arch)
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
- **Chipmunk2D** engine (Ccp Test: Chipmunk2D - Basic)
  - Use class PhysicsSpriteChipmunk2D 
    - (Class PhysicsSprite can be use with CC_ENABLE_CHIPMUNK_INTEGRATION 1)

- **Box2D** engine (Ccp Test: Box2D - Basic)
  - Use class PhysicsSpriteBox2D 
    - (Class PhysicsSprite can be use with CC_ENABLE_BOX2D_INTEGRATION 1)

- **Engine-x 2D physics integration API** (Ccp Test: Node: Physics)
  - It using Chipmunk2D as internal 2D physics engine

- **Outdated/Abandom**:
  - class PhysicsSprite: Be only part of the engine-x for backwards compatibility with Cocos2d-x.
    - **CC_ENABLE_BOX2D_INTEGRATION** / **CC_ENABLE_CHIPMUNK_INTEGRATION** are only used on class PhysicsSprite.
