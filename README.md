# Virtual Machine Project

## Task Description
In this assignment, you are required to implement a virtual machine that can execute Python bytecode, using Python itself. We have provided a basic skeleton for you to start with. Your goal is to modify and expand the code in `vm.py` to ensure it passes as many test cases as possible from the provided `test_public.py` file.

**Note:** The interface of the `run` method in the `VirtualMachine` class must remain unchanged, as it is directly called in the tests. You are free to modify the rest of the code in any way you see fit.

---

## Important Notes

- The task intentionally lacks a complete specification of the virtual machine's functionality. You are expected to explore and understand how the stack-based execution of Python bytecode works.
- Feel free to research online, read documentation, and discuss any unclear points with others. There are numerous resources available on the topic of Python bytecode and virtual machine implementation.
- The project includes instructions on how to run specific test cases directly from PyCharm.

---

## Evaluation Criteria
Your final score will be the sum of points obtained from all the tests. Partial solutions will be evaluated and awarded points accordingly. Only the last submitted solution will be considered.

Tests are divided into four levels based on the complexity of the bytecode operations they cover. The maximum achievable score for each level is defined in `vm_scorer.py` under the `LEVEL_SCORES` constant. The corresponding operation levels are defined in the `OPERATION_LEVELS` constant.

The score for each test is calculated as:
```
Test Score = (Points for the Level) / (Number of Tests in the Level)
```

---

## How to Run a Specific Test Case
To run a specific test case, use the following command:
```bash
$ pytest test_public.py::test_all_cases[simple] -vvv
```
If you are using `zsh`, escape the square brackets as follows:
```bash
$ pytest test_public.py::test_all_cases\[simple\] -vvv
```

---

## How to Run All Tests
To execute all the tests:
```bash
$ pytest test_public.py -vvv --tb=no
```

---

## How to Check the Operation Distribution Across Tests
To see which operations are covered by each test case:
```bash
$ pytest test_stat.py -s
```

---

## How to View the Total Score Locally
To check your current score:
```bash
$ pytest test_public.py -s --tb=no
```
The total score will be displayed in the line before:
```
== short test summary info ==
```

---

## Recommended Implementation Steps
To approach the task systematically, implement the following features in the suggested order, progressing from basic to advanced functionality:

### **Basic Level:**
1. Print function, arithmetic operations, variables, and logical types
2. Conditions and loops
3. Strings and string formatting
4. Lists, dictionaries, tuples, list comprehensions, unpacking, and slicing
5. Functions

### **Advanced Level:**
1. Closures and decorators
2. Classes and exceptions
3. Context managers
4. Asynchronous functions

---

## Prohibited Approaches
You are **not allowed** to use the following in your implementation:
- `exec`
- `eval`
- `inspect`
- `FunctionType`
- Direct modification of the `__code__` attribute in functions, for example:
  ```python
  def f():
      pass
  f.__code__ = code
  ```
The task specifically requires you to implement your own interpreter rather than relying on Python's internal interpreter.

---

## Useful Resources
1. **Official `dis` module documentation:**
   [https://docs.python.org/release/3.12.5/library/dis.html#module-dis](https://docs.python.org/release/3.12.5/library/dis.html#module-dis)
   - This documentation outlines all the existing Python bytecode operations.

2. **Academic interpreter project for Python 2.7 and Python 3.3:**
   [https://github.com/nedbat/byterun](https://github.com/nedbat/byterun)
   - Although it contains some issues, it is a detailed and insightful project.

3. **Detailed discussion of `byterun` in a blog post:**
   [http://www.aosabook.org/en/500L/a-python-interpreter-written-in-python.html](http://www.aosabook.org/en/500L/a-python-interpreter-written-in-python.html)

4. **Source code of the CPython interpreter:**
   - [https://github.com/python/cpython/blob/3.12/Python/ceval.c](https://github.com/python/cpython/blob/3.12/Python/ceval.c)
   - [https://github.com/python/cpython/blob/3.12/Python/generated_cases.c.h](https://github.com/python/cpython/blob/3.12/Python/generated_cases.c.h)

---

## Example Commands for Debugging
Take a look at the commented-out code in `vm_runner.py` for helpful debugging tips.

- Run a specific test:
  ```bash
  $ pytest test_public.py::test_all_cases[simple] -vvv
  ```
- Run all tests without traceback:
  ```bash
  $ pytest test_public.py -vvv --tb=no
  ```
- View your current score:
  ```bash
  $ pytest test_public.py -s --tb=no
  ```

---

## Summary
By following the steps outlined in this document, you will build a virtual machine capable of interpreting Python bytecode. The project will enhance your understanding of low-level Python internals, including stack-based execution and bytecode interpretation. Good luck!

