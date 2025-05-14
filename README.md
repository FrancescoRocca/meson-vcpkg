# meson-vcpkg
Example repository to demonstrate how to integrate vcpkg with meson build system.

## Configuration
- Edit the `meson-vcpkg.txt` file: modify `vcpkg_base_path` and `vcpkg_base_install_dir` so that they point to the correct vcpkg installation folder.
- Add your dependencies in `vcpkg.json`.
- Adjust `meson.build` for your project.

## Compiling
Compile your project with:

```bash
$ meson setup build --native-file <src_path>/meson-vcpkg.txt --wrap-mode nodownload <src_path>
$ cd build
$ meson compile
```

It will automatically invoke vcpkg to install dependencies listed in `vcpkg.json`.

### Example output:
```
The Meson build system
Version: 1.8.0
Source dir: C:\meson-vcpkg
Build dir: C:\meson-vcpkg\build
Build type: native build
Project name: meson-vcpkg
Project version: undefined
C compiler for the host machine: clang (clang 20.1.4 "clang version 20.1.4")
C linker for the host machine: clang link 14.44.35207.1
Host machine cpu family: x86_64
Host machine cpu: x86_64
Found pkg-config: YES (C:/vcpkg/installed/x64-windows/tools/pkgconf/pkgconf.exe) 2.4.3
Run-time dependency sdl3 found: YES 3.2.12
Run-time dependency yaml-0.1 found: YES 0.1
Build targets in project: 1

meson-vcpkg undefined

  User defined options
    Native files: .\meson-vcpkg.txt
    wrap_mode   : nodownload

Found ninja-1.12.1 at "C:\Program Files\Meson\ninja.EXE"
```

Inside `meson-logs/meson-log.txt` you'll find the installation information of vcpkg.

> Remember to copy all the DLL files into the same folder as your executable
