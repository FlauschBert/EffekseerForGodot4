# EffekseerForGodot4

## Overview
This is the Effekseer's runtime plugin for [Godot Engine](https://godotengine.org).  
You will be able to show the effects that was created with Effekseer.  

[Godot Engine](https://godotengine.org)向けEffekseerプラグインです。  
Effekseerで作成したエフェクトをGodot Engine 4.xで表示することができます。

- [Official website](https://effekseer.github.io)
- [For Godot 3.x plugin](https://github.com/effekseer/EffekseerForGodot3)

## Documents (How to use it)

- [Help](https://effekseer.github.io/Help_Godot/v4/index.html)

## How to develop the plugin

### Clone the repository

```
git clone https://github.com/effekseer/EffekseerForGodot4 --recursive
```

### Build binaries

Call `setup.py` only once to generate the bindings. If the bindings are generated before every build scons builds all targets every time.

#### Windows

- python3 and scons `pip install scons`
- Visual Studio 2019 or later.

Execute `python3 Dev/Cpp/setup.py platform=windows`  
Execute `python3 Dev/Cpp/build.py platform=windows`

#### macOS, iOS

- python3 and scons `brew install scons`
- Latest Xcode

Execute `python3 Dev/Cpp/setup.py platform=osx`  
Execute `python3 Dev/Cpp/build.py platform=osx`

Execute `python3 Dev/Cpp/setup.py platform=ios`  
Execute `python3 Dev/Cpp/build.py platform=ios`

#### Android

- macOS or Linux
- python3 and scons
- Android NDK. ANDROID_NDK_ROOT required.

Execute `python3 Dev/Cpp/setup.py platform=android`  
Execute `python3 Dev/Cpp/build.py platform=android`

#### Linux

- Ubuntu (64bit)
- python3 and scons `apt install scons`
- Multilib `apt install gcc-multilib g++-multilib`

Execute `python3 Dev/Cpp/setup.py platform=linux`  
Execute `python3 Dev/Cpp/build.py platform=linux`

### Build Godot debug editor for windows

#### Get the code

https://docs.godotengine.org/en/stable/contributing/development/compiling/getting_source.html

`git clone  --branch="4.1.1-stable" --depth=1 https://github.com/godotengine/godot.git`

#### Compiling

https://docs.godotengine.org/en/stable/contributing/development/compiling/compiling_for_windows.html#doc-compiling-for-windows

`scons p=windows vsproj=yes debug_symbols=yes progress=no optimize=speed_trace target=editor`

### Edit native codes

#### Windows

Create an effekseer build environment.

```
mkdir Dev/Effekseer/build
cd Dev/Effekseer/build
cmake -DBUILD_VIEWER=ON -DBUILD_EDITOR=ON .. 
```

Uses Visual Studio 2019 or later, to open and build the following solution file.

- Dev/Cpp/EffekseerGodot.sln

### Run by Godot Engine

Uses Godot Engine 4.x, to open the following project file.

- Dev/Godot/project.godot
