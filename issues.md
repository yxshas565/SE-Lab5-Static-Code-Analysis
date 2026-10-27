# Static Code Analysis — Issues Found

| Issue | Type | Line(s) | Description | Fix Approach |
|---|---|---|---|---|
| MD5 hashing | Security — High | 46 | MD5 is unsuitable for security-sensitive hashing. | Replaced MD5 with SHA-256. |
| Shell command execution | Security — High | 57 | `os.system()` with a filename can enable command injection. | Removed shell execution and used a normal status message. |
| Unsafe `eval()` | Security — Medium | 42 | Evaluating an expression as code can execute unintended operations. | Removed `eval()` and accept a validated numeric discount rate. |
| Insecure PIN generation | Security — Low | 50 | `random.randint()` is not intended for security-sensitive random values. | Used `secrets.randbelow()`. |
| Hard-coded secret | Security — Low | 66 | A secret embedded in source code can be exposed. | Removed the hard-coded secret and its output. |
| Mutable default argument | Code quality | 14 | A default list is shared between function calls. | Changed the default to `None` and initialized behavior conditionally. |
| Bare `except` | Code quality | 24–27 | Hides errors and makes debugging difficult. | Removed the broad exception handling and used dictionary operations safely. |
| Unused imports and variables | Code quality | 4–6, 31, 41 | Unused code reduces readability. | Removed unused imports and variables. |
| Missing file encoding and context manager | Code quality | 55–57 | File handling should close resources reliably and specify encoding. | Used `with open(..., encoding="utf-8")`. |
| Flake8 line-length violations | Style | 10–18 | Long lines reduce readability and violate the configured limit. | Split long expressions and dictionaries across lines. |
| Missing docstrings and naming issues | Code quality | Multiple | Inconsistent naming and missing documentation reduce maintainability. | Used descriptive snake_case names and added docstrings. |
| Comparison to `None` | Style | 32 | Equality comparison with `None` is discouraged. | Used explicit identity checks or dictionary lookups. |

