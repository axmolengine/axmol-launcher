# engine-x-wiki

Welcome to the engine-x wiki, another fork of cocos2d-x-4.0
Purpose:

Make cocos2d-x better
gitee repo:

https://gitee.com/c4games/engine-x (because gitee repo sync failed with too large, please upstream github always)
New project (python2 or python3 works)

    Cpp Project: cocos new -p cppgame.c4games.com -d D:\dev\projects\ -l cpp --portrait CppGame
    Lua Project: cocos new -p luagame.c4games.com -d D:\dev\projects\ -l lua --portrait LuaGame

#### Android APK min size release (only contains armv7a arch)
    CppGame-release.apk (3.34MB)

#### Using physics integration API:
It works with Chipmunk2D or Box2D (at the moment)

If you want use Chipmunk2D as physics 2D framework
set ```CC_ENABLE_CHIPMUNK_INTEGRATION 1```

If you want use Box2D as physics 2D framework
set ```CC_ENABLE_BOX2D_INTEGRATION 1``` 

If you set both  to 1 than Chipmunk2D is the defaut!!
