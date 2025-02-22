# LLVM 10 Ports

This project ports the [LLVM Project](https://llvm.org/) to recent Debian
and Ubuntu releases.

The origin [zhongruoyu/llvm-ports](https://hub.docker.com/r/zhongruoyu/llvm-ports) is for LLVM 11-17, this fork is used for the Fundamentals of Compiling course using LLVM 10.

Either Debian 11 (Bullseye) or Ubuntu 20.04 (Focal Fossa), namely 10-bullseye and 10-focal, are recommended for the Fundamentals of Compiling course.

## Images

The ports are available as Docker images at
[Docker Hub](https://hub.docker.com/r/spaceskynet/llvm-10-ports). They also come
with the Debian/Ubuntu release's default [GCC](https://gcc.gnu.org/), and the
releases of [GNU Binutils](https://www.gnu.org/software/binutils/)
(version 2.38) and [CMake](https://cmake.org/) (version
3.16.7). It's painful to find a correct version for CMake with LLVM 10.

The image tags are in the format of `version[-variant]-codename`, where
`version` is the LLVM release version, `codename` is the codename of the
Debian/Ubuntu release, and `variant` is an optional variant identifier (see
below). For example, tag `15.0.7-jammy` refers to the image with LLVM 15.0.7 on
Ubuntu 22.04 (Jammy Jellyfish), and tag `14-slim-bullseye` refers to the "slim"
variant of the image with the latest LLVM 14 release on Debian 11 (Bullseye).

The following LLVM releases are available:

| LLVM release | versions as appeared in tags |
| ------------ | ---------------------------- |
| LLVM 10.0.1  | `10`, `10.0`, `10.0.1`       |

The following Debian/Ubuntu releases are available:

| Release                        | codename as appeared in tags |
| ------------------------------ | ---------------------------- |
| Debian 12 (Bookworm)           | `bookworm`                   |
| Debian 11 (Bullseye)           | `bullseye`                   |
| Debian 10 (Buster)             | `buster`                     |
| Ubuntu 22.04 (Jammy Jellyfish) | `jammy`                      |
| Ubuntu 20.04 (Focal Fossa)     | `focal`                      |
| Ubuntu 18.04 (Bionic Beaver)   | `bionic`                     |

All images provide the [LLVM Core](https://llvm.org/) libraries,
[Clang](https://clang.llvm.org/),
[Extra Clang Tools](https://clang.llvm.org/extra/index.html),
[LLD](https://lld.llvm.org/), [LLDB](https://lldb.llvm.org/),
[MLIR](https://mlir.llvm.org/), [Polly](https://polly.llvm.org/),
[compiler-rt](https://compiler-rt.llvm.org/),
[libc++](https://libcxx.llvm.org/), [libc++ ABI](https://libcxxabi.llvm.org/),
libunwind, and [OpenMP](https://openmp.llvm.org/).

Due to CMake Error, will not build the "slim" version.

~~The "slim" variants are available. They provide significantly smaller images by having LLVM and Clang libraries dynamically linked. This, however, also comes at the cost of a substantial performance penalty. See [here](https://llvm.org/docs/BuildingADistribution.html#general-distribution-guidance) for more details.~~

See [here](https://hub.docker.com/r/zhongruoyu/llvm-ports/tags) for a complete
list of tags.

## License

This project is licensed under the [GPL-3.0 License](LICENSE).
