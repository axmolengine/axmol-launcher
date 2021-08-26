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

## 2D Physics Engines informations:
- **Chipmunk2D** engine (Cpp Test: Chipmunk2D - Basic) 
  - Use class PhysicsSpriteChipmunk2D 
  
- **Box2D** engine (Cpp Test: Box2D - Basic)
  - Use class PhysicsSpriteBox2D 
  
- **Box2D-optimized (This project is currently in alpha)
  - adxe add Box2D-optimized for your own tests 
  - Use cmake option: OPT_BOX2D_OPTIMIZED=ON to enable it on "adxe\thirdparty\CMakeLists.txt")

  
- **adxe 2D physics integration API** (Cpp Test: Node: Physics)
  - It using Chipmunk2D as internal 2D physics engine

- **Outdated/Abandom/Cocos2d-x**:
  - class PhysicsSprite: Be only part of the adxe for backwards compatibility with Cocos2d-x.
Use CC_ENABLE_BOX2D_INTEGRATION 1 (using Box2D) or CC_ENABLE_CHIPMUNK_INTEGRATION 1 (using Chipmunk2D)

## Chipmunk2D-/Box2D - Testbeds:
The goals where: 
- Using the original source files of the testbeds as possible. 
- Let the original source files be the original sources as much as possible.
- Give "a small view" to the Testbed examples.
- Please remind: Not all 'Box2D - TestBed' demos working full at the moment (because of different keyboard implementation, mouse buttons has some lags also).

## Support for custom texture atlas (sprite sheet) formats
- Default sprite sheet format is PLIST v3.  This is the format that the `TexturePacker` application outputs when you select the "Cocos2d-x" option.
- Custom sprite sheet format reader is created by implementing the `SpriteSheetLoader` interface, then registering this implementation by calling `SpriteFrameCache::registerSpriteSheetLoader()`.
- Custom SpriteSheetLoader must have a unique identifier, which is assigned by using the `SpriteSheetFormat::CUSTOM` as the base value. For example, `MyFormatId = SpriteSheetFormat::CUSTOM + 10`.
- In cpp-tests, SpriteFrameCache test has an implementation of a JSON sprite sheet format loader, implemented with the name `GenericJsonArraySpriteSheetLoader`. View this example and the default `PlistSpriteSheetLoader` for examples on how to implement the `SpriteSheetLoader` interface.
- **Sprite sheets must always contain unique identifiers for the sprite frames.**  Loading more than one sprite sheet that uses the exact same frame identifers will result in undefined behaviour.  There are several ways to handle this, one being to prefix the graphic filenames, so for example, if two different files are named `image1.png`, one being for scene1 and another for scene of a game, then you would name them `scene1_image1.png`, `scene2_image1.png`.  The other, and possibly the better method, is to use sub-folders folders to differentiate between frame names, such as `scene1/image1.png` and `scene2/image1.png`, and ensure that the sub-folder name is not stripped out during sprite sheet creation.