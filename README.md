# Box3D Lua Bindings

Unofficial [Box3D](https://github.com/erincatto/box3d) LuaJIT FFI bindings, generated from the Box3D C header files.

I decided to put Box3D into a small engine project im working on [Modit](https://github.com/modit-engine).

Since they could be useful to anyone else wanting to mess with Box3D in Lua here they are.

The bindings cover the exported C API declared in the headers.

## Requirements

- LuaJIT with FFI support
- A compiled Box3D shared library
- Supports both single-precision (`float`) and double-precision (`BOX3D_DOUBLE_PRECISION`) Box3D builds (automatically detected at runtime)

## Usage

Load the module from LuaJIT:

```lua
local box3d = require("box3d.ffi")

local ffi = box3d.ffi
local lib = box3d.lib

print("Box3D version:", box3d.version)
print("Double precision mode:", box3d.is_double)
```

You'll need to build Box3D separately and make its shared library available to the loader. Depending on your setup, you may need to adjust the library path in `ffi.lua`.

## Notes

These bindings are unofficial and aren't affiliated with or maintained by the Box3D project. They're generated from the upstream headers, so compatibility may depend on the version of Box3D you're using.

The loader automatically checks whether the library was compiled with single or double precision (`b3IsDoublePrecision`) and adjusts `b3Pos` and `b3WorldTransform` declarations accordingly.

I'll try to keep things updated as upstream changes, but updates may not always be immediate. Contributions, fixes, and suggestions are welcome!

## License

Released under the MIT License. See [LICENSE](LICENSE) for details.