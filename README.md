
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/fe73b673bf0343aeae1c84ff1911b3ce)](https://www.codacy.com/gh/terminaldweller/delf/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=terminaldweller/delf&amp;utm_campaign=Badge_Grade)

# delf
delf is an ELF dump tool.<br/>

## Installation
You will also need to have `libcapstone` installed.
```sh
pip install delf
```

## Requirements
You need python3 and `capstone`. If you don't have capstone you can get it by:<br/>
```bash

pip install capstone

```
Your terminal needs to support ASCII escape sequences.<br/>

## Options
For a list of available options just run `delf -h`. Here's what you'll get:<br/>
```bash

usage: delf [-h] [--dbg] [--obj OBJ] [--header] [--symboltable] [--phdrs]
            [--shdrs] [--symbolindex] [--stentries] [--objcode] [--test]
            [--test2] [--funcs] [--objs] [--dynsym] [--dlpath] [--phdynent]
            [--section SECTION] [--dumpfunc DUMPFUNC]
            [--dumpfuncasm DUMPFUNCASM] [--textasm] [--dynsecents] [--reladyn]
            [--relaplt] [--rodata] [--disass DISASS]

optional arguments:
  -h, --help            show this help message and exit
  --dbg                 debug
  --obj OBJ             path to the executbale, shared object or object you
                        want to load in bruiser
  --header              dump headers
  --symboltable         dump symbol table
  --phdrs               dump program haeders
  --shdrs               dump section haeders
  --symbolindex         dump symbol index
  --stentries           dump section table entries
  --objcode             dump objects
  --test                test switch
  --test2               test switch 2
  --funcs               dump functions
  --objs                dump objects
  --dynsym              dump dynamic symbol table
  --dlpath              dump dynamic linker path
  --phdynent            dump ph PT_DYNAMIC entries
  --section SECTION     dump a section
  --dumpfunc DUMPFUNC   dump a functions machine code
  --dumpfuncasm DUMPFUNCASM
                        dump a functions assembly code
  --textasm             disassemble the text section
  --dynsecents          dynamic section entries
  --reladyn             .rela.dyn entries
  --relaplt             .rela.plt entries
  --rodata              dump .rodata
  --disass DISASS       disassemblt a section

  ```

## Feature Request
If there is something you need delf to do, make an issue and I'll take a look.<br/>

## TODO
delf does not support ELF32. I'll write that in whenever I get the time to work on delf<br/>
