# Internal Tables

Internal Tables are in-memory tables used to store multiple records.

Unlike database tables, Internal Tables exist only while the program is running.

---

# Declaration

```abap
DATA gt_material TYPE TABLE OF mara.
```

---

# Work Area

```abap
DATA gs_material TYPE mara.
```

---

# Append Data

```abap
gs_material-matnr = 'MAT001'.

APPEND gs_material TO gt_material.
```

---

# Loop

```abap
LOOP AT gt_material INTO gs_material.

  WRITE: / gs_material-matnr.

ENDLOOP.
```

---

# Modern Syntax

```abap
LOOP AT gt_material INTO DATA(ls_material).

  WRITE / ls_material-matnr.

ENDLOOP.
```

---

# Common Operations

| Statement | Description |
|-----------|-------------|
| APPEND | Add new row |
| INSERT | Insert row |
| MODIFY | Update row |
| DELETE | Remove row |
| SORT | Sort data |
| READ TABLE | Read one row |
| LOOP AT | Iterate rows |

---

# Best Practices

- Prefer Standard Table unless another type is required.
- Sort data before using Binary Search.
- Use LOOP instead of repeatedly calling READ TABLE when processing all records.