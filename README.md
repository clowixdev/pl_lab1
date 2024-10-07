# Laboratory work for University

## Principles of optimizing compilers

In this laboratory work we have to learn how to deal with optimizing compilers
and try them by ourselves.

We had some source code with parts that can be optimized by compilers,
and we compared assembly codes of optimized and none optimized binary files.

### Compilation

We used `gcc` co compile `OPTBENCH.c` with optimization flags and without them.

without any flags for optimization:

```console
gcc OPTBENCH.c -o non-optimized.exe
```

with optimization flags for speed:

```console
gcc -Ofast OPTBENCH.c -o optimized.exe
```

- `-Ofast` is equivalent to `-O3 -ffast-math` turning on higher optimization levels and more aggressive math optimization

with optimization flags:

```console
gcc -m64 -Ofast -flto -march=native -funroll-loops OPTBENCH.c -o optimized.exe
```

- `-Ofast` is equivalent to `-O3 -ffast-math` turning on higher optimization levels and more aggressive math optimization
- `-march=native` - it's turning on architecture optimizations
- `-flto` - intermodular optimizations
- `-m64` - 64 bits mode
- `-funroll-loops` - turning on loops unpacking


### Disassembly

Disassembling was provided by `objdump` utility with this command line:

```console
objdump -d -Mintel <file>
```

where:
- `-d` - disassembly flag
- `-Mintel` - flag that sets intel architecture for asm syntax

### Comparison

>STATUS: processing results
