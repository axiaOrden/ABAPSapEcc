# Variables

Variables are used to store values during program execution.

---

# Declaration

Variables are declared using the `DATA` keyword.

```abap
DATA gv_name TYPE string.
DATA gv_age  TYPE i.
```

---

# Assigning Values

```abap
DATA gv_name TYPE string.

gv_name = 'Patrick'.
```

---

# Output

```abap
REPORT z_variables.

DATA gv_name TYPE string.
DATA gv_age  TYPE i.

gv_name = 'Patrick'.
gv_age = 28.

WRITE: / 'Name:', gv_name.
WRITE: / 'Age :', gv_age.
```

Output

```
Name: Patrick
Age : 28
```

---

# Naming Convention

| Prefix | Description |
|---------|-------------|
| gv_ | Global Variable |
| lv_ | Local Variable |
| cv_ | Changing Variable |
| iv_ | Importing Variable |
| ev_ | Exporting Variable |
| rv_ | Returning Variable |

Example

```abap
DATA lv_total TYPE i.
```

---

# Best Practices

- Use meaningful variable names.
- Avoid single-letter variable names.
- Always choose the correct data type.

Good

```abap
DATA lv_invoice_total TYPE p LENGTH 8 DECIMALS 2.
```

Bad

```abap
DATA x TYPE i.
```