Godot Bare-runtime addon


https://docs.godotengine.org/en/latest/tutorials/scripting/gdextension/gdextension_cpp_example.html#doc-gdextension-cpp-example

https://github.com/holepunchto/bare?tab=readme-ov-file#building

```
# godot-builddeps.sh

DEPS="alsa-lib-devel freetype-devel mesa glu-devel libXcursor-devel \
 libXi-devel libXinerama-devel libXrender-devel libXrandr-devel libX11-devel \
 libpng-devel libwebp-devel libogg-devel libtheora-devel libvorbis-devel \
 libenet-devel zlib-devel mbedtls-devel miniupnpc-devel pcre2-devel \
 pulseaudio-devel graphite-devel harfbuzz-devel libzstd-devel \
 speech-dispatcher-devel brotli-devel icu-devel"

echo $DEPS
```


```
# godot-cpp/mybuild.sh

scons platform=linuxbsd use_llvm=yes linker=lld
WEBOPTS="platform=web threads=no"
scons $WEBOPTS target=template_debug
scons $WEBOPTS target=template_release

#TEMPLATES_PATH="~/.local/share/godot/export_templates/4.3rc/"
#mkdir -p $TEMPLATES_PATH
#cp bin/*.zip $TEMPLATES_PATH

# ln $TEMPLATES_PATH $(pwd)/bin

cd bin
mv godot.web.template_debug.wasm32.nothreads.zip web_nothreads_debug.zip
mv godot.web.template_release.wasm32.nothreads.zip web_nothreads_release.zip
cd -
```
