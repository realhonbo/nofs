
### How To Build

1. CMake
```bash
rm -rf build ; mkdir build ; cd build
cmake .. -G "Unix Makefiles" -DCMAKE_EXPORT_COMPILE_COMMANDS=1
make
```

2. Make
```bash
make clean
bear -- make -j$(nproc)
```

### Debug
```bash
openocd
-c "tcl_port disabled"
-c "gdb_port 3333"
-c "telnet_port 4444"
-s /usr/share/openocd/scripts/
-f stlink.cfg
-c "program nofs.elf"
-c "init;reset init;"
-c "echo  ===<- READY ->=== "
```
