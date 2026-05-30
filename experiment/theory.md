Evaluating expressions is a fundamental task in programming. An expression consists of operands (such as variables or constants) and operators (such as +, \*, %, etc.). The process of evaluation involves parsing the expression, determining the precedence and associativity of operators, and computing the result step by step.

### Types of Operators

1. **Arithmetic Operators**: Used for mathematical calculations.
   - Examples: `+` (addition), `-` (subtraction), `*` (multiplication), `/` (division), `%` (modulus)
   - Example: `a + b * c`
2. **Relational Operators**: Used to compare values.
   - Examples: `>`, `<`, `>=`, `<=`, `==`, `!=`
   - Example: `x > y`
3. **Logical Operators**: Used to combine or invert logical conditions.
   - Examples: `&&` (logical AND), `||` (logical OR), `!` (logical NOT)
   - Example: `a && b`
4. **Bitwise Operators**: Used to perform bit-level operations.
   - Examples: `&` (AND), `|` (OR), `^` (XOR), `~` (NOT), `<<` (left shift), `>>` (right shift)
   - Example: `a | b`
5. **Ternary Operator**: A shorthand for if-else.
   - Syntax: `(condition) ? expr1 : expr2`
   - Example: `(a > b) ? p : q`

### Operator Precedence and Associativity

Operator precedence determines the order in which different operators in an expression are evaluated. Associativity determines the order in which operators of the same precedence are evaluated (left-to-right or right-to-left).

**Example of Precedence:**

- In `a + b * c`, multiplication (_) has higher precedence than addition (+), so `b _ c` is evaluated first.

**Example of Associativity:**

- In `a - b - c`, subtraction is left-associative, so it is evaluated as `(a - b) - c`.
- In `a = b = c`, assignment is right-associative, so it is evaluated as `a = (b = c)`.

Parentheses can be used to override default precedence and force evaluation of sub-expressions first.

The following table shows the precedence order of operators:

<img src="images/table.png">

### Step-by-Step Expression Evaluation Example

Consider the expression: `int result = 2 + 3 * 4 > 10 && 5 < 8 || 7 == 6;`

Let's break it down:

1. Multiplication first: `3 * 4 = 12`
2. Addition: `2 + 12 = 14`
3. Relational: `14 > 10` is `true` (1)
4. Relational: `5 < 8` is `true` (1)
5. Logical AND: `1 && 1` is `true` (1)
6. Relational: `7 == 6` is `false` (0)
7. Logical OR: `1 || 0` is `true` (1)

So, `result` will be assigned the value `1` (true).

### Summary

To evaluate an expression:

1. Parse the expression and identify operands and operators.
2. Apply operator precedence and associativity rules.
3. Compute the value step by step, solving sub-expressions as needed.

Understanding how expressions are evaluated is essential for writing correct and efficient code.
