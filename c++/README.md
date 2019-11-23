
To compile this wrapper of eigen to asm.js, download and install the emscripten SDK from [here](http://kripken.github.io/emscripten-site/docs/getting_started/downloads.html). Then run the following instruction:


```
emcc -O3 --memory-init-file 0 -I/c++/Eigen -I/c++/eigen-wrapper/ -s ALLOW_MEMORY_GROWTH=1 -s MODULARIZE=1 -s DEMANGLE_SUPPORT=1 --bind -o OUTPUT_FILENAME c++/embind.cpp 
```

// Include this for React-supported version 
// See https://stackoverflow.com/questions/54115783/how-to-use-emscripten-compiled-javascript-within-react-react-native
``-s MODULARIZE=1```