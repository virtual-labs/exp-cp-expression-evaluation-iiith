Evaluating an expression is one of the most common tasks in programming. 
For example, `a + b + c` is an expression where `+` is an operator, and `a`, `b`, and `c` are operands. The value of the expression is the sum of `a`, `b`, and `c`. Expressions are often evaluated to assign a variable a new value or to verify the truthfulness of a test condition. Operators can be **unary** (e.g., `~`, `++`), **binary** (e.g., `+`, `*`), or **ternary** (e.g., `(a > b) ? p : q`).

#### Examples of expressions:

1. To compute the area of a triangle from base *b* and height *h*
    <p style="text-align: center;">Area = 1/2.0 * base * height</p>
    Note that this expression will be evaluated left to right. The division operator will be evaluated first, followed by two multiplication operators. The `2.0` ensures that the division is carried out as a floating point operation.

2. To compute the area of a triangle from the three sides, *a*, *b*, and *c*
    <p style="text-align: center;">s = (a + b + c) / 2.0</p>
    <p style="text-align: center;">area = s * (s - a) * (s - b) * (s - c)</p>
    Here, the area is calculated in two steps:

    - Compute `s` from the three sides `a`, `b`, and `c`. The parenthesis ensures that the evaluation within the parenthesis takes place first. Without parenthesis, we would have obtained the value of `s` as the sum of `a`, `b`, and half of `c`.
    - Compute the area using the value of `s`. Parentheses are very important in evaluating this expression.

3. To find the n<sup>th</sup> term of an arithmetic progression
    <p style="text-align: center;">t<sub>n</sub> = a + (n - 1) * d</p>
    where `a` is the first term and `d` is the common difference. Here, the use of parentheses helps in evaluating the expression as needed.

Expressions in a computer program are similar to algebraic expressions. When many operators are specified in an expression, the evaluation takes place according to the precedence of operators. Parentheses can be used to override the precedence of operators and force the evaluation of a sub-expression within an expression. Expressions are evaluated according to the associativity of the operator, which determines how operators of the same precedence are grouped in the absence of parentheses. The objective in evaluating an expression is to consider the precedence and associativity of the individual operators and compute the value of the sub-expressions.

Evaluating an expression involves repeatedly solving the sub-expressions in the lowest level parentheses and substituting its value to solve the bigger expression. If an expression or sub-expression does not have parentheses, we can directly compute its value based on the precedence and associativity of the operators present in the expression. The sub-expression involving the operator with higher precedence is evaluated before other sub-expressions. The following table gives the precedence order of all the operators:

<img src="images/table.png">

Operators can be broadly categorized as:

1. **Arithmetic Operators:** These operators are used for arithmetic operations like addition, subtraction, and multiplication. Examples: DIVISION(`/`), MODULUS OR REMAINDER (`%`).
2. **Relational Operators:** These operators are typically used for comparison of two operands. Examples: GREATER THAN (`>`), GREATER THAN OR EQUAL TO (`>=`).
3. **Logical Operators:** These operators are used for conducting logical operations like AND, OR. Examples: LOGICAL AND (`&&`), LOGICAL OR (`||`).
4. **Bitwise Operators:** These operators are used to perform operations on bits. Examples: BITWISE AND (`&`), BITWISE OR (`|`).