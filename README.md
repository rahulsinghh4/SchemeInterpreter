# Scheme Interpreter in Python

A feature-rich implementation of a Scheme language interpreter written in Python, supporting core Scheme functionality including special forms, procedures, environments, and tail recursion optimization.

## Overview

This interpreter implements a subset of the Scheme programming language, following the read-eval-print loop (REPL) pattern common to interactive programming environments. It provides support for:

- Basic Scheme data types and primitives
- Special forms (if, cond, let, quote, etc.)
- User-defined procedures using lambda
- Proper lexical scoping
- Tail call optimization (optional)
- Built-in procedures and environment frames

## Core Components

### 1. Evaluation Engine

The interpreter's core consists of two main functions:

- `scheme_eval`: Evaluates Scheme expressions in a given environment
- `scheme_apply`: Applies Scheme procedures to arguments

These functions work together to handle:
- Self-evaluating expressions (numbers, booleans)
- Symbol lookup in environments
- Special form evaluation
- Procedure application

### 2. Special Forms

The interpreter supports various special forms including:

- `define`: Variable and procedure definitions
- `lambda`: Function creation
- `if`: Conditional execution
- `cond`: Multi-way conditionals
- `let`: Local variable bindings
- `quote`: Symbol and list quotation
- `and`/`or`: Logical operations
- `begin`: Sequential execution

### 3. Environment Model

The environment model is implemented through the `Frame` class, which provides:

- Hierarchical scope chains
- Variable binding and lookup
- Support for nested environments
- Proper closure creation

### 4. Procedure Types

The interpreter implements several procedure types:

- `BuiltinProcedure`: Python functions exposed to Scheme
- `LambdaProcedure`: User-defined procedures
- `MuProcedure`: Procedures with dynamic scope (if implemented)
- `MacroProcedure`: Macro support (if implemented)

### 5. Additional Features

The interpreter includes support for:

- Stream operations (delay, cons-stream)
- Error handling and validation
- Interactive REPL environment
- File loading and evaluation
- Built-in procedures (map, filter, reduce)

## Usage

### Basic Usage

1. Start the interpreter:
```bash
python3 scheme.py
```

2. Enter Scheme expressions at the prompt:
```scheme
scm> (+ 2 3)
5
scm> (define (square x) (* x x))
square
scm> (square 4)
16
```

### Loading Files

You can load Scheme files using the `-load` flag:
```bash
python3 scheme.py -load file.scm
```

### Interactive Mode

The interpreter supports an interactive mode with the following features:
- Command history
- Error reporting
- Expression continuation
- File loading during session

## Error Handling

The interpreter provides comprehensive error checking for:
- Syntax errors
- Type mismatches
- Undefined variables
- Improper list structure
- Invalid procedure applications

## Implementation Details

### Evaluation Process

1. **Reading**: Converts text input into Scheme expressions
2. **Evaluation**: Processes expressions according to Scheme rules
3. **Printing**: Displays results in proper Scheme format

### Scoping Rules

- Implements proper lexical scoping
- Supports closures and environment chains
- Handles nested procedure definitions
- Proper variable shadowing

## Extensions

The interpreter can be extended with:

- Tail call optimization (by uncommenting relevant code)
- Macro system implementation
- Dynamic scope through mu special form
- Additional built-in procedures
- Custom special forms

## Requirements

- Python 3.6 or higher

## Testing

The interpreter includes comprehensive testing capabilities:
- Unit tests for core functionality
- Integration tests for special forms
- Environmental testing
- Error handling verification

## Limitations

Current implementation limitations:
- No support for continuations
- Limited macro system
- No garbage collection
- Subset of standard Scheme procedures
- No support for complex numbers

## Contributing

To extend or modify the interpreter:

1. Understand the core evaluation cycle
2. Follow existing patterns for new features
3. Maintain proper error handling
4. Add appropriate tests
5. Document new functionality
