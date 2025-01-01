# Potential Buffer Overflow in Assembly Code
This repository demonstrates a potential buffer overflow vulnerability in a short snippet of assembly code. The vulnerability arises from the lack of bounds checking before accessing memory.  The solution demonstrates how to mitigate this vulnerability using range checks.

## Vulnerability
The `mov eax, [ebx+ecx*4]` instruction is susceptible to buffer overflow if the value in the `ecx` register is not properly validated.  If `ecx` is larger than expected, the instruction will attempt to access memory outside the allocated buffer.

## Mitigation
The solution provided demonstrates how to add bounds checking before accessing memory. This ensures that the code does not attempt to access memory outside the allocated buffer.

## How to reproduce
1. Clone the repository.
2. Assemble the code in the `bug.asm` file.
3. Execute the assembled code with different values in ecx to observe the buffer overflow. 
4. Compare to the solution implemented in `bugSolution.asm` which includes the implemented bounds check.