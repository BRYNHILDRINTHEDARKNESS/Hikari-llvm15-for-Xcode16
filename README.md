# Hikari-llvm15-for-Xcode16
```
git clone --recursive -b llvm-16.0.0rel https://github.com/61bcdefg/Hikari-LLVM15.git Hikari
cd Hikari
git submodule update --remote --recursive
mkdir build
cd build
cmake -G Ninja -DCMAKE_BUILD_TYPE=Release -DCMAKE_OSX_ARCHITECTURES=arm64 -DLLVM_ENABLE_PROJECTS="clang;lld" -DLLVM_TARGETS_TO_BUILD="X86;ARM;AArch64" -DLLVM_ENABLE_ZSTD=OFF -DCMAKE_OSX_DEPLOYMENT_TARGET=12.0 -DLLVM_CREATE_XCODE_TOOLCHAIN=ON  -DLLVM_INCLUDE_TESTS=OFF -DLLVM_INCLUDE_EXAMPLES=OFF -DLLVM_INCLUDE_UTILS=OFF -DLLVM_INCLUDE_BENCHMARKS=OFF -DLLVM_BUILD_TOOLS=OFF -DLLVM_INSTALL_TOOLCHAIN_ONLY=ON -DCMAKE_INSTALL_PREFIX="./install" ../llvm
ninja
ninja install-xcode-toolchain
mv your_path/build/Toolchains/Hikari_LLVM16.0.0.xctoolchain /Library/Developer/Toolchains/Hikari_LLVM16.0.0.xctoolchain
Xcode -> Toolchains -> hikari.llvm16.0.0
```
