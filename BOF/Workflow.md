# GDB

- set disassembly-flavor intel -> 
- disassemble main - get all instructions from a function
- x win / p win -> get address of the "win" function
- r < <(echo -ne "\x41\x41\x41\x41\x41\x41\x41\x41\x41\x41\x41\x41\x41\x41\x67\x05\x40") -> run program with input interpreted as hex. !ATTENTION! little endian vs big endian


