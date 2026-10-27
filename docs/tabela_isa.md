# Tabela da ISA implementada (MIPS32)

| Mnemônico | Formato | Opcode | Funct  | Operação (RTL) |
|-----------|---------|--------|--------|----------------|
| add       | R       | 000000 | 100000 | R[rd] <- R[rs] + R[rt] |
| sub       | R       | 000000 | 100010 | R[rd] <- R[rs] - R[rt] |
| and       | R       | 000000 | 100100 | R[rd] <- R[rs] & R[rt] |
| or        | R       | 000000 | 100101 | R[rd] <- R[rs] \| R[rt] |
| slt       | R       | 000000 | 101010 | R[rd] <- (R[rs] < R[rt]) ? 1 : 0 |
| addi      | I       | 001000 | -      | R[rt] <- R[rs] + SignExt(imm) |
| lw        | I       | 100011 | -      | R[rt] <- M[R[rs] + SignExt(imm)] |
| sw        | I       | 101011 | -      | M[R[rs] + SignExt(imm)] <- R[rt] |
| beq       | I       | 000100 | -      | se R[rs] = R[rt]: PC <- PC + 4 + (SignExt(imm) << 2); senão PC <- PC + 4 |
| break     | -       | 000000 | 001101 | encerra o programa (não conta como instrução útil no CPI) |