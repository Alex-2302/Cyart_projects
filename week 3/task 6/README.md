# Exploit Development Basics Lab

## Overview

This project demonstrates basic binary analysis and vulnerability identification using reverse engineering tools. A vulnerable C program was analyzed to identify a buffer overflow condition and observe its behavior under different inputs.

---

## Objective

* Analyze a vulnerable binary
* Identify unsafe input handling
* Demonstrate buffer overflow behavior
* Use debugging and reverse engineering tools

---

## Tools Used

* **GDB (GNU Debugger)**
* **radare2**
* **strings**
* **GCC**

---

### Vulnerability

* Buffer size: **20 bytes**
* Input allowed: **100 bytes**
* Result: **Buffer Overflow**

---

## Analysis Steps

### 1. Strings Analysis

```bash
strings vuln
```

* Revealed input/output prompts
* Confirmed user interaction

---

### 2. GDB Analysis

```bash
gdb ./vuln
run
```

#### Observation:

* Small input → normal execution
* Large input → segmentation fault

Example:

```
Program received signal SIGSEGV
```

---

### 3. radare2 Analysis

```bash
r2 vuln
aaa
afl
pdf @ main
```

#### Key Finding:

* Stack allocates ~32 bytes
* `fgets` allows 100 bytes
* Causes memory overwrite

---

## Proof of Concept (PoC)

A buffer overflow was demonstrated by supplying input larger than the allocated buffer:

```
AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
```

### Result:

* Memory corruption
* Program crash (SIGSEGV)

---

## Key Findings

1. The program crashes with segmentation fault under large input.
2. Unsafe input handling allows overflow beyond buffer size.
3. Buffer size mismatch leads to stack corruption.

---

## Behavior Observed

| Input Size | Result             |
| ---------- | ------------------ |
| Small      | Normal execution   |
| Medium     | Undefined behavior |
| Large      | Segmentation fault |

---

## 50-Word Summary

The binary was analyzed using strings, GDB, and radare2. It revealed improper input handling, where the program accepts more data than the allocated buffer size. Large inputs caused segmentation faults, confirming a buffer overflow vulnerability. The program also showed undefined behavior, highlighting risks of memory corruption.

---

## Conclusion

This lab demonstrated how improper input validation leads to buffer overflow vulnerabilities. Static and dynamic analysis confirmed the issue, highlighting the risks of unsafe memory handling in low-level programs.

---
