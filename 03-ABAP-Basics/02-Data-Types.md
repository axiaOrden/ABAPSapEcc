# Data Types

A data type defines the kind of value that a variable can store.

ABAP provides many built-in data types that can be used without creating Data Elements.

---

# Declaring Variables

Variables are declared using the `DATA` keyword.

```abap
DATA lv_name TYPE string.
```

---

# Character (`c`)

Stores fixed-length text.

```abap
DATA lv_name TYPE c LENGTH 20.

lv_name = 'Patrick'.

WRITE lv_name.
```

---

# String (`string`)

Stores variable-length text.

```abap
DATA lv_message TYPE string.

lv_message = 'Hello ABAP!'.

WRITE lv_message.
```

Unlike `c`, a `string` automatically grows as needed.

---

# Integer (`i`)

Stores whole numbers.

```abap
DATA lv_age TYPE i.

lv_age = 25.

WRITE lv_age.
```

---

# Packed Number (`p`)

Used for decimal values, especially financial calculations.

```abap
DATA lv_price TYPE p LENGTH 8 DECIMALS 2.

lv_price = '1250.75'.

WRITE lv_price.
```

Output

```
1250.75
```

---

# Floating Point (`f`)

Stores floating-point numbers.

```abap
DATA lv_pi TYPE f.

lv_pi = '3.14159265'.

WRITE lv_pi.
```

Generally, use `TYPE p` for currency and business calculations to avoid floating-point precision issues.

---

# Date (`d`)

Stores calendar dates in the format `YYYYMMDD`.

```abap
DATA lv_date TYPE d.

lv_date = '20260707'.

WRITE lv_date.
```

Output

```
20260707
```

---

# Time (`t`)

Stores time in the format `HHMMSS`.

```abap
DATA lv_time TYPE t.

lv_time = '143015'.

WRITE lv_time.
```

Output

```
143015
```

---

# Byte (`x`)

Stores hexadecimal (binary) data.

```abap
DATA lv_hex TYPE x LENGTH 4.
```

This type is commonly used when working with files, encryption, or binary data.

---

# Boolean

ABAP does not have a native Boolean type.

Instead, SAP commonly uses `abap_bool`.

```abap
DATA lv_success TYPE abap_bool.

lv_success = abap_true.
```

Possible values:

| Constant | Value |
|----------|-------|
| `abap_true` | X |
| `abap_false` | (space) |

---

# Complete Example

```abap
REPORT z_datatypes.

DATA lv_name    TYPE string.
DATA lv_age     TYPE i.
DATA lv_salary  TYPE p LENGTH 8 DECIMALS 2.
DATA lv_date    TYPE d.
DATA lv_time    TYPE t.

lv_name   = 'Patrick'.
lv_age    = 28.
lv_salary = '3500.50'.
lv_date   = sy-datum.
lv_time   = sy-uzeit.

WRITE: / 'Name   :', lv_name,
       / 'Age    :', lv_age,
       / 'Salary :', lv_salary,
       / 'Date   :', lv_date,
       / 'Time   :', lv_time.
```

---

# Summary

| Type | Description | Example |
|------|-------------|---------|
| `c` | Fixed-length text | Name |
| `string` | Variable-length text | Message |
| `i` | Integer | Quantity |
| `p` | Decimal number | Price |
| `f` | Floating-point number | Scientific calculations |
| `d` | Date | `20260707` |
| `t` | Time | `143015` |
| `x` | Hexadecimal | Binary data |

---

# Best Practices

- Use `string` for text with variable length.
- Use `c` only when a fixed length is required.
- Use `p` for currency and financial values.
- Avoid `f` for business calculations due to floating-point precision.
- Prefer meaningful variable names over short abbreviations.