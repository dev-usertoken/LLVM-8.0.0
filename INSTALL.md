##  Installation instruction
----------------------------

### Build
```
  mkdir ./build && cd ./build
  cmake -G 'Unix Makefiles' -DCMAKE_BUILD_TYPE=RelWithDebInfo ..
  make -j20 clang
  make -j20 check-clang check-cxx
  ./bin/llvm-lit -sv --param cxx_under_test=`pwd`/bin/clang ../projects/libcxx/test/

  make install
```
