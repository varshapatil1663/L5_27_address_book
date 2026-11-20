\# Lab 5: Static Code Analysis - Issue Table



| Issue | Tool | Type | Line(s) | Description | Fix approach |

|---|---|---|---|---|---|

| Weak MD5 hash (B324) | Bandit | Security (High) | 19 | MD5 is cryptographically weak | Switched to SHA-256 |

| Unsafe pickle.load (B301) | Bandit | Security (Medium) | 67 | Unpickling can execute arbitrary code | Replaced pickle with JSON |

| import pickle (B403) | Bandit | Security (Low) | 3 | Pickle module has security risks | Removed import, used json |

| Hardcoded password (B105) | Bandit | Security (Low) | 6 | Secret stored in source code | Removed the unused constant |

| Missing whitespace (E225, E231) | Flake8 | Style | 23, 84 | No space around = and after comma | Added spaces |

| Too many blank lines (E303) | Flake8 | Style | 47 | 3 blank lines instead of 2 | Removed one |

| Line too long (E501) | Flake8 | Style | 85 | 86 characters (limit 79) | Shortened the message text |

| Broad exception (W0718) | Pylint | Quality | 34 | except Exception hides unrelated bugs | Changed to KeyError |

| Range/len loop (C0200) | Pylint | Quality | 49 | Unpythonic index loop | Used enumerate |

| No file encoding (W1514) | Pylint | Quality | 54 | open() without encoding | Added encoding="utf-8" |

| Missing docstrings (C0114/C0116) | Pylint | Quality | many | No documentation | Added docstrings |

| camelCase names (C0103) | Pylint | Style | many | Violates PEP 8 naming | Renamed to snake\_case |



Results: Pylint 5.47 -> 10.00, Bandit 4 issues -> 0, Flake8 4 errors -> 0.

