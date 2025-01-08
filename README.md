# Virtual Machine Project

## Task Description
The project involves implementing a virtual machine that executes Python bytecode using Python. The virtual machine processes bytecode instructions by manipulating a stack, managing variables, and performing arithmetic and logical operations. The provided code skeleton includes the `vm.py` file, which contains the `VirtualMachine` class. The task is to modify this class to pass various test cases from the `test_public.py` file.

The core function of the virtual machine is the `run` method, which serves as the entry point for executing bytecode. This method's interface must remain unchanged to ensure compatibility with the test cases.

## Evaluation Criteria
The final score is the sum of points obtained from all tests. Partial solutions are evaluated, and only the latest submitted solution is considered. Tests are divided into four levels based on the complexity of the bytecode operations they cover. The maximum achievable score for each level is defined in the `LEVEL_SCORES` constant in `vm_scorer.py`, and the corresponding operation levels are defined in the `OPERATION_LEVELS` constant.

The score for each test is calculated as:
```
Test Score = (Points for the Level) / (Number of Tests in the Level)
```

## How to Run Tests
To run a specific test case:
```bash
$ pytest test_public.py::test_all_cases[simple] -vvv
```
For `zsh` users, escape the square brackets:
```bash
$ pytest test_public.py::test_all_cases\[simple\] -vvv
```

To run all tests:
```bash
$ pytest test_public.py -vvv --tb=no
```

To check the operation distribution across tests:
```bash
$ pytest test_stat.py -s
```

To view the total score locally:
```bash
$ pytest test_public.py -s --tb=no
```

## Implementation Steps
The implementation should progress from basic to advanced functionality. The recommended steps are as follows:

### Basic Level:
1. Implement stack operations for print functions, arithmetic operations, and variable management.
2. Handle conditional statements and loops.
3. Add support for strings and string formatting.
4. Implement list, dictionary, tuple operations, list comprehensions, unpacking, and slicing.
5. Support function definitions and calls.

### Advanced Level:
1. Implement closures and decorators.
2. Add support for classes and exception handling.
3. Implement context managers.
4. Support asynchronous functions.

## Prohibited Approaches
The following approaches are not allowed in the implementation:
- Usage of `exec`, `eval`, `inspect`, or `FunctionType`.
- Direct modification of the `__code__` attribute in functions, such as:
  ```python
  def f():
      pass
  f.__code__ = code
  ```
The project requires implementing a custom interpreter and not relying on Python's internal interpreter.

## Useful Resources
1. **Official `dis` module documentation:**
   [https://docs.python.org/release/3.12.5/library/dis.html#module-dis](https://docs.python.org/release/3.12.5/library/dis.html#module-dis)
2. **Academic interpreter project for Python 2.7 and Python 3.3:**
   [https://github.com/nedbat/byterun](https://github.com/nedbat/byterun)
3. **Detailed discussion of `byterun` in a blog post:**
   [http://www.aosabook.org/en/500L/a-python-interpreter-written-in-python.html](http://www.aosabook.org/en/500L/a-python-interpreter-written-in-python.html)
4. **Source code of the CPython interpreter:**
   - [https://github.com/python/cpython/blob/3.12/Python/ceval.c](https://github.com/python/cpython/blob/3.12/Python/ceval.c)
   - [https://github.com/python/cpython/blob/3.12/Python/generated_cases.c.h](https://github.com/python/cpython/blob/3.12/Python/generated_cases.c.h)

## Example Commands for Debugging
Commands for running tests and debugging the virtual machine:
- Run a specific test:
  ```bash
  $ pytest test_public.py::test_all_cases[simple] -vvv
  ```
- Run all tests without traceback:
  ```bash
  $ pytest test_public.py -vvv --tb=no
  ```
- View the current score:
  ```bash
  $ pytest test_public.py -s --tb=no
  ```

