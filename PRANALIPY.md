# PranaliPy – Bytecode Insight Mode

A customised CPython 3.12 flavour developed as a Python Flavour assignment.

## Custom Feature

PranaliPy adds a diagnostic message inside the `BINARY_OP` bytecode execution logic.

## Modified Source

`Python/bytecodes.c`

```c
PySys_WriteStderr("[PranaliPy] Executing BINARY_OP\n");
```

## Generated Source

`Python/generated_cases.c.h`

The generated execution code was updated after modifying the bytecode definition.

## Demonstration

```python
A = type('A', (), {'__add__': lambda self, other: 42})
print(A() + A())
```

Output:

```text
42
```

The diagnostic message is displayed during execution.

## Build

```cmd
PCbuild\build.bat -p x64
```

## Test

```cmd
PCbuild\amd64\python.exe -c "A=type('A',(),{'__add__':lambda self,other:42}); print(A()+A())"
```

## Author

Pranali Debnath  
B.Tech Computer Science and Engineering  
ICFAI University, Tripura

## Original CPython

https://github.com/python/cpython
