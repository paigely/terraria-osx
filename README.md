
## Anatomy
* `osx.zip` - Collection of Terraria's latest libraries
built from source

## Patching shared libs (dylibs)
Download `osx.zip` from this repository and replace:

`~/Library/Application Support/Steam/steamapps/common/Terraria/Terraria.app/Contents/MacOS/osx`

with its contents

<details>
  <summary>Shared libraries source code</summary>

  <br>

  <p>
    Unmodified libs are omitted. libnfd was modified by myself
    in order for the SConstruct to compile with new scons, but
    no other changes were made. Some libs are still Intel as
    Terraria rejects them if they're not, I'm still looking into
    this
  </p>
  
  <img align="center" src="https://files.catbox.moe/5hahf1.png" width="24" height="24"> [libFAudio.0.dylib](https://github.com/FNA-XNA/FAudio/)
  
  <img align="center" src="https://files.catbox.moe/5hahf1.png" width="24" height="24"> [libFNA3D.0.dylib](https://github.com/FNA-XNA/FNA3D/)
  
  <img align="center" src="https://files.catbox.moe/5hahf1.png" width="24" height="24"> [libFNA3D.0.dylib](https://github.com/FNA-XNA/FNA3D/)
  
  <img align="center" src="https://files.catbox.moe/5hahf1.png" width="24" height="24"> [libjpeg.9.dylib](https://github.com/winlibs/libjpeg/)

  <img align="center" src="https://files.catbox.moe/5hahf1.png" width="24" height="24"> [libMoltenVK.dylib](https://github.com/KhronosGroup/MoltenVK/)

  <img align="center" src="https://files.catbox.moe/5hahf1.png" width="24" height="24"> [libnfd.dylib](https://github.com/native-toolkit/libnfd/)
  
  <img align="center" src="https://files.catbox.moe/5hahf1.png" width="24" height="24"> [libogg.0.dylib](https://github.com/xiph/ogg/)
  
  <img align="center" src="https://files.catbox.moe/5hahf1.png" width="24" height="24"> [libopenal.1.dylib](https://github.com/kcat/openal-soft/)
  
  <img align="center" src="https://files.catbox.moe/5hahf1.png" width="24" height="24"> [libpng16.16.dylib](https://github.com/pnggroup/libpng/)
  
  <img align="center" src="https://files.catbox.moe/5hahf1.png" width="24" height="24"> [libSDL2-2.0.0.dylib](https://github.com/libsdl-org/SDL/tree/SDL2/)
  
  <img align="center" src="https://files.catbox.moe/5hahf1.png" width="24" height="24"> [libtheoradec.1.dylib](https://github.com/xiph/theora/)
  
  <img align="center" src="https://files.catbox.moe/5hahf1.png" width="24" height="24"> [libtheorafile.dylib](https://github.com/xiph/theora/)
  
  <img align="center" src="https://files.catbox.moe/5hahf1.png" width="24" height="24"> [libvorbis.0.dylib](https://github.com/xiph/vorbis/)
  
  <img align="center" src="https://files.catbox.moe/5hahf1.png" width="24" height="24"> [libvorbisfile.3.dylib](https://github.com/xiph/vorbis/)
  
  <img align="center" src="https://files.catbox.moe/5hahf1.png" width="24" height="24"> [libvulkan.1.dylib](https://github.com/KhronosGroup/Vulkan-Loader/)
</details>

## Vulkan
Vulkan can almost quadruple your performance with a drawback of having
to patch Terraria since its implementation memory leaks

1. Put `/gldevice:Vulkan` in Terraria's launch options
<img width="425" height="326" alt="image" src="https://github.com/user-attachments/assets/a5e582aa-b41a-4a7d-8d96-df061339e772" />

2. Follow the instructions to patch dylibs as shown above

## To-do
* Look into decompiling and poking at Terraria
  * I already tried doing this but I ran out of storage because C# tooling is huge
* Look into why Terraria rejects some dylibs when they are
built for apple silicon (SDL2 for instance)
