
To compile this wrapper of eigen to asm.js, download and install the emscripten SDK from [here](http://kripken.github.io/emscripten-site/docs/getting_started/downloads.html). Then run the following instructions:


```# Make the "latest" EMCC SDK "active" for the current user. (writes ~/.emscripten file)
./emsdk activate latest

# Activate PATH and other environment variables in the current terminal
source ./emsdk_env.sh

```




```
emcc -O3 --memory-init-file 0 -I/c++/Eigen -I/c++/eigen-wrapper/ -s ALLOW_MEMORY_GROWTH=1 -s MODULARIZE=1  -s WASM=0 -s DEMANGLE_SUPPORT=1 --bind -o linear-algebra-asm-lib.js c++/embind.cpp 
```

 `linear-algebra-asm-lib.js` is the output file


// Include this for React-supported version 
// See https://stackoverflow.com/questions/54115783/how-to-use-emscripten-compiled-javascript-within-react-react-native
``-s MODULARIZE=1```

// `-s WASM=1` - to include web asm file (or `-s WASM=0` for no wasm file)