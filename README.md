![QOI Logo](https://qoiformat.org/qoi-logo.svg)

# QOI - The “Quite OK Image Format” for fast, lossless image compression

Single-file MIT licensed library for C/C++

See [qoi.h](https://github.com/phoboslab/qoi/blob/master/qoi.h) for
the documentation and format specification.

More info at https://qoiformat.org


## Why?

Compared to stb_image and stb_image_write QOI offers 20x-50x faster encoding,
3x-4x faster decoding and 20% better compression. It's also stupidly simple and
fits in about 300 lines of C.


## Example Usage

- [qoiconv.c](https://github.com/phoboslab/qoi/blob/master/qoiconv.c)
converts between png <> qoi
 - [qoibench.c](https://github.com/phoboslab/qoi/blob/master/qoibench.c)
a simple wrapper to benchmark stbi, libpng and qoi


## Limitations

The QOI file format allows for huge images with up to 18 exa-pixels. A streaming 
en-/decoder can handle these with minimal RAM requirements, assuming there is 
enough storage space.

This particular implementation of QOI however is limited to images with a 
maximum size of 400 million pixels. It will safely refuse to en-/decode anything
larger than that. This is not a streaming en-/decoder. It loads the whole image
file into RAM before doing any work and is not extensively optimized for 
performance (but it's still very fast).

If this is a limitation for your use case, please look into any of the other 
implementations listed below.


## Improvements, New Versions and Contributing

The QOI format has been finalized. It was a conscious decision to **not** have a
version number in the file header. If you have a working QOI implementation today, 
you can rest assured that it will be compatible with all QOI files tomorrow.

There are a lot of interesting ideas for a successor of QOI, but none of these will 
be implemented here. That doesn't mean you shouldn't experiment with QOI, but please
be aware that pull requests that change the format will not be accepted.

Likewise, pull requests for performance improvements will probably not be accepted
either, as this "reference implementation" tries to be as easy to read as possible.


## Tools

- https://github.com/floooh/qoiview - native QOI viewer
- https://github.com/pfusik/qoi-ci/releases/tag/qoi-ci-1.1.1 - QOI Plugin installer for GIMP, Imagine, Paint.NET and XnView MP
- https://github.com/iOrange/QoiFileTypeNet/releases/tag/v0.2 - QOI Plugin for Paint.NET
- https://github.com/iOrange/QOIThumbnailProvider - Add thumbnails for QOI images in Windows Explorer
- https://github.com/Tom94/tev - another native QOI viewer (allows pixel peeping and comparison with other image formats)
- https://apps.apple.com/br/app/qoiconverterx/id1602159820 QOI <=> PNG converter available on the Mac App Store
- https://github.com/kaetemi/qoi-max - QOI Bitmap I/O Plugin for 3ds Max
- https://raylibtech.itch.io/rtexviewer - texture viewer, supports QOI
- https://raylibtech.itch.io/rtexpacker - texture packer, supports QOI
- https://github.com/DmitriySalnikov/godot_qoi - QOI GDNative Addon for Godot Engine
- https://gitlab.com/dan9er/farbfeld-convert-qoi - QOI <=> farbfeld converter


## Implementations & Bindings of QOI

- https://github.com/pfusik/qoi-ci (Ć, transpiled to C, C++, C#, Java, JavaScript, Python and Swift)
- https://github.com/kodonnell/qoi (Python)
- https://github.com/JaffaKetchup/dqoi (Dart, with Flutter support)
- https://github.com/Cr4xy/lua-qoi (Lua)
- https://github.com/superzazu/SDL_QOI (C, SDL2 bindings)
- https://github.com/saharNooby/qoi-java (Java)
- https://github.com/MasterQ32/zig-qoi (Zig)
- https://github.com/rbino/qoix (Elixir)
- https://github.com/NUlliiON/QoiSharp (C#)
- https://github.com/aldanor/qoi-rust (Rust)
- https://github.com/zakarumych/rapid-qoi (Rust)
- https://github.com/takeyourhatoff/qoi (Go)
- https://github.com/DosWorld/pasqoi (Pascal)
- https://github.com/elihwyma/Swift-QOI (Swift)
- https://github.com/xfmoulet/qoi (Go)
- https://erratique.ch/software/qoic (OCaml)
- https://github.com/arian/go-qoi (Go)
- https://github.com/kchapelier/qoijs (JavaScript)
- https://github.com/KristofferC/QOI.jl (Julia)
- https://github.com/shadowMitia/libqoi/ (C++)
- https://github.com/MKCG/php-qoi (PHP)
- https://github.com/LightHouseSoftware/qoiformats (D)
- https://github.com/mhoward540/qoi-nim (Nim)
- https://github.com/wx257osn2/qoixx (C++)
- https://github.com/Tiefseetauchner/lr-paint (Processing)
- https://github.com/amstan/qoi-fpga (FPGA: verilog)
- https://github.com/musabkilic/qoi-decoder (Python)
- https://github.com/mathpn/py-qoi (Python)
- https://github.com/JohannesFriedrich/qoi4R (R)
- https://github.com/shraiwi/mini-qoi (C, streaming decoder)
- https://github.com/10maurycy10/libqoi/ (Rust)
- https://github.com/0xd34df00d/hsqoi (Haskell)
- https://github.com/418Coffee/qoi-v (V)
- https://github.com/Imagine-Programming/QoiImagePlugin (PureBasic)

## QOI Support in Other Software

- [SerenityOS](https://github.com/SerenityOS/serenity) supports decoding QOI system wide through a custom [cpp implementation in LibGfx](https://github.com/SerenityOS/serenity/blob/master/Userland/Libraries/LibGfx/QOILoader.h)
- [Raylib](https://github.com/raysan5/raylib) supports decoding and encoding QOI textures through its [rtextures module](https://github.com/raysan5/raylib/blob/master/src/rtextures.c)
- [Rebol3](https://github.com/Oldes/Rebol3/issues/39) supports decoding and encoding QOI using a native codec
- [c-ray](https://github.com/vkoskiv/c-ray) supports QOI natively
- [SAIL](https://sail.software) image decoding library, supports decoding and encoding QOI images
- [Orx](https://github.com/orx/orx) 2D game engine, supports QOI natively
- [IrfanView](https://www.irfanview.com) supports decoding and encoding QOI through its Formats plugin
- [ImageMagick](https://github.com/ImageMagick/ImageMagick) supports decoding and encoding QOI, since 7.1.0-20
- [barebox](https://barebox.org) bootloader, supports decoding QOI images for splash logo, since v2022.03.0
- [KorGE](https://korge.org) & KorIM Kotlin 2D game engine and imaging library, supports decoding and encoding QOI natively since 2.7.0
- [DOjS](https://github.com/SuperIlu/DOjS) DOS JavaScript Canvas implementation supports loading QOI files
- [XnView MP](https://www.xnview.com/en/xnviewmp/) supports decoding QOI since 1.00

## Packages

[AUR](https://aur.archlinux.org/pkgbase/qoi-git/) - system-wide qoi.h, qoiconv and qoibench install as split packages.


## Implementations not yet conforming to the final specification

These implementations are based on the pre-release version of QOI. Resulting files are not compatible with the current version.

- https://github.com/ChevyRay/qoi_rs (Rust)
- https://github.com/panzi/jsqoi (TypeScript)
