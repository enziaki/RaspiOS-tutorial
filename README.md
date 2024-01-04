# Raspberry PI OS

This project is mainly for learning, I don't know shit.
It is an experiment from sergei's and Rockytriton's tutorials.


## Devel packages

+ Fedora
```
sudo dnf install gcc-arm-linux-gnu arm-none-eabi-gcc-cs arm-none-eabi-newlib gcc-aarch64-linux-gnu gcc-arm-linux-gnu
```

```
.globl _start
_start:
    mrs x0, mpidr_el1
    and x0, x0, #0xFF
    cbz x0, master
    b proc_hang

```

Thi section identifies the master core through mrs, then masks the all but the
lowest 8 bits of master core ID(to get the core number) and then hangs the rest
of the cores.