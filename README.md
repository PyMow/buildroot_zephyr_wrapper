# buildroot_zephyr_wrapper
Wrap the different piece of a zephyr project to build in buildroot package


# Build
In standalone
```
cmake -Bbuild -DBOARD=pic64gx_curiosity_kit -G "Unix Makefiles" pic64gx-soc/apps/blinky
make -C build
```

the resulting elf is located here: build/zephyr/zephyr.elf

# Flash

to be flashed on a sdcard it need a HSS compatible header
for blinky example:
```
/home/phm/Projects/Microchip/zephyr/zephyr_pic64gx/hss-payload-generator/hss-payload-generator/binaries/hss-payload-generator -c pic64gx-soc/payload-configs/single_hart_ddr.yaml output.bin
```
and then to flash


# Notes

PLease note that for the moment no zepyr modules have been added, as
they have to be added individualy as submodule.
