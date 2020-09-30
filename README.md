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

Input:

`f(int a, float b, char c)`

Output:

```
Offset de c = 4
Offset de b = 4 + sizeof(char)
Offset de a = 4 + sizeof(char) + sizeof(float)

```
