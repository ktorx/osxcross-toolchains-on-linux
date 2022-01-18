<h1 align="center">crossmac</h1> 
<p align="center">Cross Compiler for MacOS</p>

## Problem
* MacOS is worthy Release Target for a Software since many people use it.
* MacOS is required officially to develop for MacOS(also because of SDKs) and not everyone owns Mac Devices. Thus, Cross Compiling to MacOS is necessary.
* For cross-compiling to MacOS , you require Apple SDK and osxcross (wrapper to Clang).
* Compiling osxcross takes time. Also , Size of osxcross after compilation is >500MB thus making osxcross unfit to compile during CI/CD.

## Introduction
* `crossmac` is Pre-Built [osxcross](https://github.com/tpoechtrager/osxcross) (MacOS cross compiler) with SDK taken from [phracker/MacOSX-SDKs](https://github.com/phracker/MacOSX-SDKs). 
* [Github Actions](https://github.com/features/actions) is used to build `crossmac`.
* It is heavily compressed(from `~550MB to ~50MB`) using `zstd`. 
* It is ideal to use for CI/CD or if you don't want to compile osxcross.
* It's built on Void Linux and works properly on not-old Linux glibc Distributions.

## Usage
* Download crossmac and extract it.
* Add `lib/` folder of crossmac to `LD_LIBRARY_PATH`

  `export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:CROSSMAC/lib/` 
* Add `bin/` folder of crossmac to `PATH`

  `export PATH=$PATH:CROSSMAC/bin/`
* Make sure that you have `clang` or `gcc` installed (`clang` is preferred).
* You can use `o64-clang` / `o64-clang++` to target for Intel Mac Devices . You can use `oa64-clang` / `oa64-clang++` to target for Apple Silicon Mac Devices (`arm64` devices).
* Refer [osxcross](https://github.com/tpoechtrager/osxcross) for More Information.

## License
[GPL-2.0](LICENSE)
