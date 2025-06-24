# 🧮 Saimon's Arithmetic Formatter
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

def arithmetic_arranger(problems, display_answers=False):
    if len(problems) > 5:
        return 'Error: Too many problems.'

    first_lines = []
    second_lines = []
    dashes = []
    results = []

    for problem in problems:
        parts = problem.split()
        if len(parts) != 3:
            return "Error: Invalid format."

        operand1, operator, operand2 = parts

        if operator not in ['+', '-']:
            return "Error: Operator must be '+' or '-'."

        if not (operand1.isdigit() and operand2.isdigit()):
            return "Error: Numbers must only contain digits."

        if len(operand1) > 4 or len(operand2) > 4:
            return "Error: Numbers cannot be more than four digits."

        width = max(len(operand1), len(operand2)) + 2

        first_lines.append(operand1.rjust(width))
        second_lines.append(operator + operand2.rjust(width - 1))
        dashes.append('-' * width)

        if display_answers:
            if operator == '+':
                answer = str(int(operand1) + int(operand2))
            else:
                answer = str(int(operand1) - int(operand2))
            results.append(answer.rjust(width))

    arranged_problems = '    '.join(first_lines) + '\n' + '    '.join(second_lines) + '\n' + '    '.join(dashes)

    if display_answers:
        arranged_problems += '\n' + '    '.join(results)

    return arranged_problems


print(arithmetic_arranger(["32 + 698", "3801 - 2", "45 + 43", "123 + 49"], True))

