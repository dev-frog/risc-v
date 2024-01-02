# RISC-V

## Getting Started

you need `risc-v toolchain`

> arch linux

`yay -S riscv-gnu-toolchain-bin`

from the tool chaine we need

- `riscv32-unknown-elf-as`
- `riscv32-unknown-elf-ld`

TO run the kernel you need `qemu`

Reference the virt.c implementation of qemu's risc-v emulator: (https://github.com/qemu/qemu/blob/master/hw/riscv/virt.c)


> Compilation step
`riscv64-unknown-elf-as boot.S -o boot.o`

> Linking step

`riscv64-unknown-elf-ld -T kernel.lds boot.o -o kernel.elf`

## Qume config

`qemu-system-riscv64 -machine virt -cpu rv64 -smp 4 -m 128 -nographic -serial mon:stdio -bios none -kernel kernel.elf`