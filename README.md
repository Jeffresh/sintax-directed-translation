# Sintax directed translate

Design translation scheme (offset parameters Pascal style. That is, the parameters are put on the stack form left ro right)

### Grammar:

```
Def -> ID ID Resto
Resto -> ‘,’ Tipo ID Resto
Resto -> epsilon
Tipo -> INT
Tipo -> CHAR
Tipo -> FLOAT
```

### Example:

**Input:**

`f(int a, float b, char c)`

**Output:**

```
Offset de c = 4
Offset de b = 4 + sizeof(char)
Offset de a = 4 + sizeof(char) + sizeof(float)

```


Implement using SLY the grammar tha represent binary numbers, this definition supports binary floating point numbers and calculates its value. **Example:**
`10011.101`

### Grammar:

| Sintactic rules     | Semantic rules                                      |
|---------------------|-----------------------------------------------------|
| num → sec1 ‘.’ sec2 | num.v := sec1.v + sec2.v/2^sec2.lon                 |
| sec → sec1 dig      | sec.v := sec1.v * 2 + dig.v sec.lon := sec1.lon + 1 |
| sec → dig           | sec.v := dig.v sec.lon := 1                         |
| dig → ‘0’           | dig.v := 0                                          |
| dig → ‘1’           | dig → ‘1’ dig.v := 1                                |

### Used attributes

| Used attributes                         |
|-----------------|-----------------------|
| num.v           | Number value          |
| sec.v           | Digit sequence value  |
| sec.lon         | Digit sequence length |
| dig.v           | Digit value           |
