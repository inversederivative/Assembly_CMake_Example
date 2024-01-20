# Assembly CMake Example

---

### Introduction

This is a simple project, which demonstrates how to build a NASM source project, using CMake. 


---

### System V AMD64 ABI vs Windows ABI

The different Application Binary Interfaces, determine how the assembly language will be converted to binary machine 
code. This is important to consider, because there are different standards for Windows vs. virtually everything else, 
i.e. Linux, Mac, etc.

The Calling Convention determines which registers are used for passing function parameters, among other things.

System V AMD64 ABI:

Calling Registers:
- Integer/Pointer Arguments: RDI, RSI, RDX, RCX, R8, R9
- Integer/Pointer Return Value: RAX
- Floating-Point Arguments: XMM0, XMM1, XMM2, XMM3, XMM4, XMM5, XMM6, XMM7
- Floating-Point Return Value: XMM0
- Stack: Additional parameters are passed on the stack, and the callee cleans the stack.

Callee-saved Registers:
- RBX, RBP, R12, R13, R14, R15
- XMM6-XMM15

Windows x64 ABI:

Calling Registers:
- Integer/Pointer Arguments: RCX, RDX, R8, R9
- Integer/Pointer Return Value: RAX
- Floating-Point Arguments: XMM0, XMM1, XMM2, XMM3, XMM4, XMM5, XMM6, XMM7
- Floating-Point Return Value: XMM0
- Stack: Parameters are passed on the stack, and the stack is cleaned by the caller.

Callee-saved Registers:
- RBX, RBP, RDI, RSI, R12, R13, R14, R15
- XMM6-XMM15