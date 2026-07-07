# Inline Declaration

Inline Declaration was introduced in newer ABAP releases to reduce boilerplate code.

Instead of declaring variables separately, they can be created automatically where needed.

---

# Traditional Syntax

```abap
DATA lv_count TYPE i.

lv_count = 100.
```

---

# Inline Variable

```abap
DATA(lv_count) = 100.
```

---

# SELECT Example

Traditional

```abap
DATA gt_mara TYPE TABLE OF mara.

SELECT *
  FROM mara
  INTO TABLE gt_mara.
```

Modern

```abap
SELECT *
  FROM mara
  INTO TABLE @DATA(gt_mara).
```

---

# LOOP Example

Traditional

```abap
DATA ls_mara TYPE mara.

LOOP AT gt_mara INTO ls_mara.

ENDLOOP.
```

Modern

```abap
LOOP AT gt_mara INTO DATA(ls_mara).

ENDLOOP.
```

---

# READ TABLE

Traditional

```abap
DATA ls_mara TYPE mara.

READ TABLE gt_mara
INTO ls_mara
INDEX 1.
```

Modern

```abap
READ TABLE gt_mara
INTO DATA(ls_mara)
INDEX 1.
```

---

# Benefits

- Less code
- Better readability
- Variable scope is limited
- Encourages modern ABAP style

---

# Best Practices

✔ Use Inline Declaration whenever the variable is only needed locally.

✔ Keep variable scope as small as possible.

✔ Combine with modern Open SQL syntax.