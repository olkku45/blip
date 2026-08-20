# kernel

## commands (from root)
1. `nasm -f elf64 src/boot_sector.asm -o build/boot_sector.o`
2. `ld -T src/linker.ld -o build/linked.o build/boot_sector.o`
3. `objcopy -O binary build/linked.o build/boot_img`
4. `qemu-system-x86_64 -no-reboot -drive file=build/boot_img,format=raw,index=0,media=disk`
