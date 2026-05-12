# Refactoring

## Explain

### What does the term "to refactor" mean in the context of a software project?

• To restructure an existing codebase / source code.

• Without changing the behavior of the code itself.

### Why is it important to have established existing regression or unit tests, before undertaking any refactoring?

• To ensure that the refactoring changes do not introduce bugs / change important behavior of the code in question.

### Discuss the improvements that creating the class would bring to the codebase.

• Separates the current mix of functionality in one module into two dedicated submodules, making the codebase more readable / organized(avoids an un-necessary mixing of separate functionality). 封装（Encapsulation）

• Moves towards an OOP approach to handling paths, which provides a standardized interface / API for interacting with paths, that can be assumed across the rest of the codebase. 继承（Inheritance）