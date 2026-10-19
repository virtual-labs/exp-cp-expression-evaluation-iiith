Expression evaluation is the process of computing the final value of an expression by following operator precedence, associativity, and parentheses.

### 1) What is an expression?

An expression is made of:

- **Operands**: constants, variables, or function-call results
- **Operators**: symbols such as `+`, `*`, `%`, `&&`, `|`, `? :`

Example: `a + b * c`

### 2) Operator categories (quick recap)

1. **Arithmetic**: `+`, `-`, `*`, `/`, `%`
2. **Relational**: `>`, `<`, `>=`, `<=`, `==`, `!=`
3. **Logical**: `&&`, `||`, `!`
4. **Bitwise**: `&`, `|`, `^`, `~`, `<<`, `>>`
5. **Conditional (ternary)**: `condition ? expr1 : expr2`
6. **Assignment**: `=`, `+=`, `-=`, `*=`, `/=`, `%=`, `&=`, `^=`, `|=`, `<<=`, `>>=`

### 3) Precedence and associativity

- **Precedence** decides _which_ operator is evaluated first.
- **Associativity** decides direction when operators are on the same precedence level.
- **Parentheses** always have priority and can override default order.

#### Example

- `a + b * c` -> `b * c` first (higher precedence of `*`)
- `a - b - c` -> `(a - b) - c` (left to right)
- `a = b = c` -> `a = (b = c)` (right to left)

### 4) Operator precedence table

<table>
  <thead>
    <tr>
      <th>Level</th>
      <th>Operators</th>
      <th>Description</th>
      <th>Associativity</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>1</td><td><code>[]</code>, <code>.</code>, <code>()</code>, <code>++</code>, <code>--</code></td><td>Postfix/member/call</td><td>Left to Right</td></tr>
    <tr><td>2</td><td><code>++</code>, <code>--</code>, <code>+</code>, <code>-</code>, <code>!</code>, <code>~</code></td><td>Unary operators</td><td>Right to Left</td></tr>
    <tr><td>3</td><td><code>()</code> (cast), <code>new</code></td><td>Cast/object creation</td><td>Right to Left</td></tr>
    <tr><td>4</td><td><code>*</code>, <code>/</code>, <code>%</code></td><td>Multiplicative</td><td>Left to Right</td></tr>
    <tr><td>5</td><td><code>+</code>, <code>-</code></td><td>Additive</td><td>Left to Right</td></tr>
    <tr><td>6</td><td><code>&lt;&lt;</code>, <code>&gt;&gt;</code></td><td>Shift</td><td>Left to Right</td></tr>
    <tr><td>7</td><td><code>&lt;</code>, <code>&lt;=</code>, <code>&gt;</code>, <code>&gt;=</code></td><td>Relational</td><td>Left to Right</td></tr>
    <tr><td>8</td><td><code>==</code>, <code>!=</code></td><td>Equality</td><td>Left to Right</td></tr>
    <tr><td>9</td><td><code>&amp;</code></td><td>Bitwise AND</td><td>Left to Right</td></tr>
    <tr><td>10</td><td><code>^</code></td><td>Bitwise XOR</td><td>Left to Right</td></tr>
    <tr><td>11</td><td><code>|</code></td><td>Bitwise OR</td><td>Left to Right</td></tr>
    <tr><td>12</td><td><code>&amp;&amp;</code></td><td>Logical AND</td><td>Left to Right</td></tr>
    <tr><td>13</td><td><code>||</code></td><td>Logical OR</td><td>Left to Right</td></tr>
    <tr><td>14</td><td><code>?:</code></td><td>Conditional</td><td>Right to Left</td></tr>
    <tr><td>15</td><td><code>=</code>, <code>+=</code>, <code>-=</code>, <code>*=</code>, <code>/=</code>, <code>%=</code>, <code>&amp;=</code>, <code>^=</code>, <code>|=</code>, <code>&lt;&lt;=</code>, <code>&gt;&gt;=</code></td><td>Assignment</td><td>Right to Left</td></tr>
  </tbody>
</table>

### 5) Common mistakes to avoid

1. **Ignoring precedence**
   - Writing `2 + 3 * 4` and assuming `(2 + 3) * 4`.
   - Correct order: `3 * 4` first, then `2 + 12`.

2. **Confusing associativity with precedence**
   - In `a - b - c`, some learners try `a - (b - c)`.
   - Correct due to left associativity: `(a - b) - c`.

3. **Missing parentheses in mixed logical/relational expressions**
   - Expression like `a > b && c == d || e < f` can be hard to read.
   - Even if rules are known, add parentheses for clarity:
     `(a > b && c == d) || (e < f)`.

### 6) Quick self-check

Try these mentally before moving ahead:

1. `8 - 3 - 2 = ?`
2. `2 + 3 * 5 = ?`
3. `(2 + 3) * 5 = ?`
4. `7 > 3 && 2 == 2 = ?` (use `1` for true, `0` for false)

Answers:

1. `3`
2. `17`
3. `25`
4. `1`

### 7) Step-by-step solved example

Consider:

`int result = 2 + 3 * 4 > 10 && 5 < 8 || 7 == 6;`

Evaluation:

1. `3 * 4 = 12`
2. `2 + 12 = 14`
3. `14 > 10` -> `1` (true)
4. `5 < 8` -> `1` (true)
5. `1 && 1` -> `1`
6. `7 == 6` -> `0` (false)
7. `1 || 0` -> `1`

So, `result = 1`.

### 8) Note on logical results (0 and 1)

In C-style evaluation:

- `true` is represented as `1`
- `false` is represented as `0`

So relational and logical parts of expressions typically reduce to `0` or `1`, which can then participate in further operations.

### 9) Practical checklist

When evaluating any expression:

1. Resolve parentheses first.
2. Apply precedence levels from high to low.
3. For same-level operators, apply associativity.
4. Reduce sub-expressions one step at a time.
