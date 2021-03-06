# LuauDisassembler
A disassembler for Roblox's new bytecode format. This is still in development and does not support all op-codes.

# Example output
```c
local constantPool = {
    'print',
    'warn'
}
[0005]  CLEARSTACK  { 0, 0, 0 }         \   R = {}
[0009]  LOADNUMBER  { 2, 1, 0 }         \   R[2] = 1
[000D]  LOADNUMBER  { 0, 10, 0 }            \   R[0] = 10
[0011]  LOADNUMBER  { 1, 1, 0 }         \   R[1] = 1
[0015]  FORPREP { 0, 9, 0 }         \   R[0] -= R[0 + 2]
[0019]  OGETENV { 3, 1, 0 }         \   R[3] = print
[0021]  MOVE    { 4, 2, 0 }         \   R[4] = R[2]
[0025]  CALL    { 3, 2, 1 }         \   R[3](R[4] to R[4])
[0029]  OGETENV { 3, 3, 0 }         \   R[3] = warn
[0031]  MOVE    { 4, 2, 0 }         \   R[4] = R[2]
[0035]  CALL    { 3, 2, 1 }         \   R[3](R[4] to R[4])
[0039]  FORLOOP { 0, 247, 255 }         \   R[0] += R[0 + 2]
[003D]  RETURN  { 0, 1, 0 }         \   return
```

# [1.1.2] - 27 May 2021
- [x] OP_ADD is supported
- [x] OP_SUB is supported
- [x] OP_MUL is supported
- [x] OP_DIV is supported
- [x] OP_POW is supported
- [x] OP_MOD is supported
- [x] OP_LEN is supported

## [1.1.1] - 27 May 2021
- [x] Function number displayed in output
- [x] Function information displayed in output

## [1.1.0] - 26 May 2021
- [x] Added OP_CONCAT
- [x] Fixed OP_CALL return registry names

# Supported op codes

- [x] OGETENV / GETGLOBAL
- [x] LOADNUMBER
- [x] LOADK
- [x] MOVE
- [x] FORPREP
- [x] FORLOOP
- [x] CLEARSTACK
- [x] CALL
- [x] RETURN
- [x] LOADNIL
- [x] CONCAT
- [x] LEN
- [x] ADD
- [x] SUB
- [x] MUL
- [x] DIV
- [x] POW
- [x] MOD
- [x] NOT
- [x] GETUPVAL
- [x] SETUPVAL
- [x] NEWTABLE
- [x] LOADBOOL
- [ ] VARARG
- [ ] LT
- [ ] TEST
- [ ] JMP
- [ ] EQ
- [ ] NEQ
- [ ] CLOSURE
- [ ] SETENV / SETGLOBAL
- [ ] GETTABLEK
- [ ] LE
- [ ] SETTABLEK
- [ ] NLT
- [ ] CLOSE
- [ ] ADDK
- [ ] MULK
- [ ] TESTOR
- [ ] TESTAND
- [ ] SELF
- [ ] POWK
- [ ] UNM
