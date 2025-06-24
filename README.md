# arithmetic-formatter-
A Python program that formats arithmetic problems vertically and side-by-side, mimicking the way they're written in elementary school.

---

## ✅ Features

- Accepts up to **five** arithmetic problems
- Supports **addition (`+`) and subtraction (`-`)** only
- Validates input:
  - Only numeric operands
  - Maximum of **four digits** per number
  - Only `+` and `-` operators allowed
- Outputs problems with correct spacing and alignment
- Optionally shows the **results**

---

## 💡 Example Usage

```python
from main import arithmetic_arranger

print(arithmetic_arranger(["32 + 698", "3801 - 2", "45 + 43", "123 + 49"], True))

📂 **Source Code:** [main.py](main.py)
