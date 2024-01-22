
**Splash**
- From uboots perspective the screen is 800x1280, portrait orientation
- The splash screen loaded by uboot is just the first frame of bootanimation.zip
- The image data must be RLE and have an appropriate header prepended
- logo_gen.py generates the RLE section from PNGs
- append to kingston-splash-header.bin  
- logo_gen.py depends on python2 PIL, I use it in a container of debian oldstable

**Bootanimation**

- screencapped @andyfitz's animation
- used openshot to export a webm of the animation in the correct resolution
- ffmpeg to rip the frames
- pngquant to reduce their size
- shoved it all into the right dir structure with desc.txt and zipped

**boot image**
- must be signed, any signature will do
- for testing, the magiskboot utility can place a default signature in a repacked image

**chromium / webview**
- building chromium with the package name "com.google.webview" makes it much easier for users to update system webview
