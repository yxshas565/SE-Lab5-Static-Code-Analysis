# Reflection — Static Code Analysis

## 1. How do static analysis tools help?
Static analysis tools identify potential defects, unsafe coding practices, naming problems, and formatting violations without requiring the program to execute. Using Pylint, Bandit, and Flake8 together provides complementary checks.

## 2. Which issues were most important?
The unsafe use of `eval()`, MD5 hashing, shell command execution, insecure PIN generation, and hard-coded secret were important security concerns. They were addressed by removing dynamic evaluation, using SHA-256 and the `secrets` module, removing shell execution, and removing the embedded secret.

## 3. Do clean reports guarantee that a program is correct and secure?
No. Static analysis can identify known patterns but cannot prove that a program is free from every bug or vulnerability. Functional testing, code review, and appropriate security testing are still necessary.

## 4. What did this exercise teach me?
The exercise showed that maintainable code requires more than making a program run. Clear naming, docstrings, safe file handling, validated inputs, secure APIs, and consistent formatting make software easier to review and maintain. Running the tools again after changes provides evidence that the reported issues were addressed.
