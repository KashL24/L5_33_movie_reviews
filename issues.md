
cat > issues.md <<'EOF'
# Lab 5: Static Code Analysis

| Issue | Type | Line(s) | Description | Fix Approach |
|---|---|---|---|---|
| Hardcoded bind-all address | Security | 4 | `0.0.0.0` allows the service to listen on all network interfaces. | Changed the host to `127.0.0.1` to restrict access to the local machine. |
| Hardcoded password | Security | 6 | The moderator password is stored directly in the source code. | Replaced the hardcoded password with an environment variable. |
| Insecure random generator | Security | 41 | `random.choice()` was flagged by Bandit as unsuitable for security-sensitive randomness. | Replaced `random.choice()` with `secrets.choice()`. |
| Weak MD5 hash | Security | 46 | MD5 was flagged as a weak hashing algorithm. | Replaced MD5 with SHA-256 for generating the review identifier. |
| Missing module docstring | Code Quality | 1 | The Python module had no description of its purpose. | Added a module-level docstring. |
| Incorrect naming conventions | Code Quality | 8, 11, 16, 26, 34, 39, 45, 48, 54 | Function and variable names did not follow Python naming conventions. | Renamed functions and variables to follow snake_case conventions. |
| Missing function docstrings | Code Quality | 11, 16, 26, 34, 39, 45, 48, 54 | Functions did not explain their purpose. | Added descriptive docstrings to functions. |
| Unnecessary else after return | Code Quality | 28 | An else block followed a return statement unnecessarily. | Removed the else block and returned the default value directly. |
| Use of global statement | Code Quality | 40 | The function modified a global variable using the global statement. | Removed the global variable mutation and returned the selected movie directly. |
| Inefficient loop style | Code Quality | 50 | The loop used range() and len() to access list elements by index. | Replaced the loop with enumerate(). |
| Missing whitespace around operator | Style | 35 | An operator did not have the required surrounding whitespace. | Added the required whitespace around the operator. |
| Incorrect blank lines | Style | 48 | A top-level function did not have the required blank-line separation. | Added the required blank lines before the function. |
| Incorrect inline comment spacing | Style | 70 | The inline comment did not have sufficient whitespace before the comment marker. | Added at least two spaces before the inline comment. |
| Missing whitespace after comma | Style | 72 | A comma was not followed by the required whitespace. | Added a space after the comma. |
| Missing final newline | Style | 118 | The file did not end with a newline character after editing. | Added a newline at the end of the file. |

EOF
