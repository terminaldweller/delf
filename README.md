[![Codacy Badge](https://app.codacy.com/project/badge/Grade/fe73b673bf0343aeae1c84ff1911b3ce)](https://www.codacy.com/gh/terminaldweller/delf/dashboard?utm_source=github.com&utm_medium=referral&utm_content=terminaldweller/delf&utm_campaign=Badge_Grade)

# delf

delf is an ELF 64 dump tool.<br/>

## Installation

```sh
pipx install delf
```

Or:

```sh
git clone https://github.com/terminaldweller/delf
cd delf
poetry install
```

You can then run it with `poetry shell` or `poetry run`.<br/>

## Options

For a list of available options just run `delf --help`:<br/>

```txt
$ delf --help
usage: delf [-h] [--dbg] [--obj OBJ] [--header] [--symboltable] [--phdrs] [--shdrs] [--symbolindex] [--stentries] [--objcode] [--test] [--test2] [--listdso] [--funcs] [--objs] [--dynsym] [--dlpath] [--phdynent]
            [--section SECTION] [--dumpfunc DUMPFUNC] [--dumpfuncasm DUMPFUNCASM] [--textasm] [--dynsecents] [--reladyn] [--relaplt] [--rodata] [--disass DISASS] [--disassp DISASSP] [--got] [--gotplt]
            [--noclor]

options:
  -h, --help            show this help message and exit
  --dbg                 debug
  --obj OBJ             path to the executbale, shared object or object you want to load in bruiser
  --header              dump headers
  --symboltable         dump symbol table
  --phdrs               dump program haeders
  --shdrs               dump section haeders
  --symbolindex         dump symbol index
  --stentries           dump section table entries
  --objcode             dump objects
  --test                test switch
  --test2               test switch 2
  --listdso             list DSOs
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
  --disass DISASS       disassembls a section by name in section headers
  --disassp DISASSP     disassembls a section by index in program headers
  --got                 dump .got section
  --gotplt              dump .got.plt section
  --noclor              dont use color
```

## Example usage

```txt
$ delf --obj ./main --shdrs

idx  sh_name               sh_type       sh_flags  sh_addr  sh_offset  sh_size  sh_link  sh_info  sh_addralign  sh_entsize
0    ''                    'NULL'        0         0        0          0        0        0        0             0
1    '.interp'             'PROGBITS'    2         792      792        28       0        0        1             0
2    '.note.gnu.property'  'NOTE'        2         824      824        32       0        0        8             0
3    '.note.gnu.build-id'  'NOTE'        2         856      856        36       0        0        4             0
4    '.note.ABI-tag'       'NOTE'        2         892      892        32       0        0        4             0
5    '.gnu.hash'           'GNU_HASH'    2         928      928        36       6        0        8             0
6    '.dynsym'             'DYNSYM'      2         968      968        144      7        1        8             24
7    '.dynstr'             'STRTAB'      2         1112     1112       136      0        0        1             0
8    '.gnu.version'        'VERSYM'      2         1248     1248       12       6        0        2             2
9    '.gnu.version_r'      'VERNEED'     2         1264     1264       48       7        1        8             0
10   '.rela.dyn'           'RELA'        2         1312     1312       192      6        0        8             24
11   '.init'               'PROGBITS'    6         4096     4096       23       0        0        4             0
12   '.plt'                'PROGBITS'    6         4128     4128       16       0        0        16            16
13   '.plt.got'            'PROGBITS'    6         4144     4144       8        0        0        8             8
14   '.text'               'PROGBITS'    6         4160     4160       262      0        0        16            0
15   '.fini'               'PROGBITS'    6         4424     4424       9        0        0        4             0
16   '.rodata'             'PROGBITS'    18        8192     8192       4        0        0        4             4
17   '.eh_frame_hdr'       'PROGBITS'    2         8196     8196       44       0        0        4             0
18   '.eh_frame'           'PROGBITS'    2         8240     8240       172      0        0        8             0
19   '.init_array'         'INIT_ARRAY'  3         15872    11776      8        0        0        8             8
20   '.fini_array'         'FINI_ARRAY'  3         15880    11784      8        0        0        8             8
21   '.dynamic'            'DYNAMIC'     3         15888    11792      432      7        0        8             16
22   '.got'                'PROGBITS'    3         16320    12224      40       0        0        8             8
23   '.got.plt'            'PROGBITS'    3         16360    12264      24       0        0        8             8
24   '.data'               'PROGBITS'    3         16384    12288      16       0        0        8             0
25   '.bss'                'NOBITS'      3         16400    12304      8        0        0        1             0
26   '.comment'            'PROGBITS'    48        0        12304      39       0        0        1             1
27   '.debug_aranges'      'PROGBITS'    0         0        12352      240      0        0        16            0
28   '.debug_info'         'PROGBITS'    0         0        12592      1393     0        0        1             0
29   '.debug_abbrev'       'PROGBITS'    0         0        13985      398      0        0        1             0
30   '.debug_line'         'PROGBITS'    0         0        14383      463      0        0        1             0
31   '.debug_str'          'PROGBITS'    48        0        14846      944      0        0        1             1
32   '.debug_line_str'     'PROGBITS'    48        0        15790      265      0        0        1             1
33   '.debug_rnglists'     'PROGBITS'    0         0        16055      66       0        0        1             0
34   '.symtab'             'SYMTAB'      0         0        16128      864      35       19       8             24
35   '.strtab'             'STRTAB'      0         0        16992      467      0        0        1             0
36   '.shstrtab'           'STRTAB'      0         0        17459      368      0        0        1             0
```

```txt
$ delf --obj ./main --phdrs

idx  p_type          p_flags  p_offset  p_vaddr  p_paddr  p_filesz  p_memsz  p_flags2  p_align
0    'PHDR'          'WR'     64        64       64       728       728      0         '0x8'
1    'INTERP'        'XW'     792       792      792      28        28       0         '0x1'
2    'LOAD'          'X'      0         0        0        1504      1504     0         '0x1000'
3    'LOAD'          'X'      4096      4096     4096     337       337      0         '0x1000'
4    'LOAD'          'X'      8192      8192     8192     220       220      0         '0x1000'
5    'LOAD'          'X'      11776     15872    15872    528       536      0         '0x1000'
6    'DYNAMIC'       'W'      11792     15888    15888    432       432      0         '0x8'
7    'NOTE'          'R'      824       824      824      32        32       0         '0x8'
8    'NOTE'          'R'      856       856      856      68        68       0         '0x4'
9    None            'XW'     824       824      824      32        32       0         '0x8'
10   'GNU_EH_FRAME'  ''       8196      8196     8196     44        44       0         '0x4'
11   'GNU_STACK'     'X'      0         0        0        0         0        0         '0x10'
12   'GNU_RELRO'     'W'      11776     15872    15872    512       512      0         '0x1'
```

```txt
$ delf --obj ./main --section .interp

000000 : 2f 6c 69 62 36 34 2f 6c 64 2d 6c 69 6e 75 78 2d /lib64/ld-linux-
000010 : 78 38 36 2d 36 34 2e 73 6f 2e 32 00             x86-64.so.2
```

```txt
$ delf --obj ./main --disass .text

0x0     xor     ebp, ebp
0x2     mov     r9, rdx
0x5     pop     rsi
0x6     mov     rdx, rsp
0x9     and     rsp, 0xfffffffffffffff0
0xd     push    rax
0xe     push    rsp
0xf     xor     r8d, r8d
0x12    xor     ecx, ecx
0x14    lea     rdi, [rip + 0xd5]
0x1b    call    qword ptr [rip + 0x2f5f]
0x21    hlt
0x22    nop     word ptr cs:[rax + rax]
0x2c    nop     dword ptr [rax]
0x30    lea     rdi, [rip + 0x2f99]
0x37    lea     rax, [rip + 0x2f92]
0x3e    cmp     rax, rdi
0x41    je      0x58
0x43    mov     rax, qword ptr [rip + 0x2f3e]
0x4a    test    rax, rax
0x4d    je      0x58
0x4f    jmp     rax
0x51    nop     dword ptr [rax]
0x58    ret
0x59    nop     dword ptr [rax]
0x60    lea     rdi, [rip + 0x2f69]
0x67    lea     rsi, [rip + 0x2f62]
0x6e    sub     rsi, rdi
0x71    mov     rax, rsi
0x74    shr     rsi, 0x3f
0x78    sar     rax, 3
0x7c    add     rsi, rax
0x7f    sar     rsi, 1
0x82    je      0x98
0x84    mov     rax, qword ptr [rip + 0x2f0d]
0x8b    test    rax, rax
0x8e    je      0x98
0x90    jmp     rax
0x92    nop     word ptr [rax + rax]
0x98    ret
0x99    nop     dword ptr [rax]
0xa0    endbr64
0xa4    cmp     byte ptr [rip + 0x2f25], 0
0xab    jne     0xd8
0xad    push    rbp
0xae    cmp     qword ptr [rip + 0x2eea], 0
0xb6    mov     rbp, rsp
0xb9    je      0xc7
0xbb    mov     rdi, qword ptr [rip + 0x2f06]
0xc2    call    0xfffffffffffffff0
0xc7    call    0x30
0xcc    mov     byte ptr [rip + 0x2efd], 1
0xd3    pop     rbp
0xd4    ret
0xd5    nop     dword ptr [rax]
0xd8    ret
0xd9    nop     dword ptr [rax]
0xe0    endbr64
0xe4    jmp     0x60
0xe9    nop     dword ptr [rax]
0xf0    push    rbp
0xf1    mov     rbp, rsp
0xf4    mov     dword ptr [rbp - 4], 0
0xfb    mov     dword ptr [rbp - 8], edi
0xfe    mov     qword ptr [rbp - 0x10], rsi
0x102   xor     eax, eax
0x104   pop     rbp
0x105   ret
```
