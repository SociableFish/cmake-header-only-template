# cmake-header-only-template
A nice and easy-to-use CMake template for header-only libraries, licensed under
the MIT License. Change all instances of `yourlib` and `YOURLIB` (so far only in
`CMakeLists.txt` and `test/CMakeLists.txt`) to the name of your library. Files
should be located in `include`, which is added as an include path. Tests are
located in `test` and use GoogleTest. No other features are currently supported.