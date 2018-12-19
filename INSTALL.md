##  Installation instruction
----------------------------

### Build
```
  mkdir ./build && cd ./build
  cmake -G 'Unix Makefiles' -DCMAKE_BUILD_TYPE=RelWithDebInfo ..
  make -j20 clang
  make -j20 check-clang check-cxx
  ./bin/llvm-lit -sv --param cxx_under_test=`pwd`/bin/clang ../projects/libcxx/test/

  rm CMakeCache.txt
  CXX="$(pwd)/llvm/build/bin/clang++" \
  CXXFLAGS="-cxx-isystem /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/include/c++/v1 -isystem /usr/include" \
  cmake -G 'Unix Makefiles' -DCMAKE_BUILD_TYPE=RelWithDebInfo ..

  cp bin/clang-8 clang-ok
  find ../include/ -name '*.h' | xargs touch
  make -j20 clang VERBOSE=1
```
