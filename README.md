# 🛠️ Assembler Project

A two-pass assembler written in C for a class assignment. This program processes assembly language source files, supports macros, and translates instructions into machine code.

## 📚 Overview

This assembler is designed to:
- 📝 Parse and preprocess assembly source files
- 🔄 Expand macros using a preprocessor
- 🏷️ Perform symbol resolution and error checking in two passes
- 🧾 Generate machine code output and auxiliary files

### ✨ Key Features

- 🧩 **Macro Expansion:** Detects and expands macros in the source.
- 🔄 **Two-Pass Assembly:**  
  - _First pass:_ Builds symbol tables, checks syntax, processes labels, directives, and instructions.  
  - _Second pass:_ Resolves symbols, encodes instructions, and generates output files.
- 🚨 **Error Handling:** Reports syntax errors, invalid operands, memory overflows, and more.
- 🛠️ **Instruction Set:** Supports commands such as `mov`, `cmp`, `add`, `sub`, `not`, `clr`, `lea`, `inc`, `dec`, `jmp`, `bne`, `red`, `prn`, `jsr`, `rts`, and `stop`.
- 📦 **Supported Directives:** Handles `.data`, `.string`, `.entry`, `.extern`.
- 📄 **Output Formats:** Generates output files including `.ob` (machine code), `.ent` (entry points), and `.ext` (external references).

## 🚀 Usage

### 🏗️ Building

Use the provided Makefile:
```bash
make
```
This compiles `assembler.c` and all dependencies into an executable named `assembler`.

### ▶️ Running

```bash
./assembler <file1.as> <file2.as> ...
```
- Accepts one or more `.as` assembly source files as arguments
- Generates output files for each input

## 📝 Example Assembly

```assembly
; Example program
MCRO m1
    mov r1, r2
ENDMCRO

.entry START
START: mov r3, r4
       add r3, r5
       stop
```

## 🗂️ Project Structure

- `assembler.c/h`: Main assembler logic and entry point
- `preprocessor.c/h`: Macro expansion
- `first_pass.c/h`, `second_pass.c/h`: Two-pass assembly implementation
- `commands.c/h`: Instruction set definitions
- `parser.c/h`: String and line parsing utilities
- `link_list.c/h`: Linked list utilities for symbol tables
- `export_files.c/h`: Output file generation
- `statement.c/h`: Statement parsing and validation
- `tables.c/h`: Internal tables for macros, symbols, etc.

## ⚠️ Error Handling

The assembler provides descriptive error and warning messages for:
- Incorrect command-line usage
- Invalid file names or line lengths
- Syntax errors and invalid operands
- Memory overflow and reserved word usage

## 👤 Author

- Elior Levian ([GitHub](https://github.com/elior-levian))
