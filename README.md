# llvm-project
Repository to hold cross-compilers for platforms where no upstream binaries exist

To build a new release, go to the machine where you will build the toolchains and run the following:
```shell
VERSION=13.0.1
HOST_TRIPLE=arm64-apple-darwin
git clone https://github.com/llvm/llvm-project.git
cd llvm-project
git checkout "llvmorg-$VERSION"
cd ..
mkdir llvm-release
cd llvm-release
../llvm-project/llvm/utils/release/test-release.sh -lldb -release ${VERSION} -triple ${HOST_TRIPLE} -final -no-test-suite
```

The result will then be found in `llvm-release/final`.
