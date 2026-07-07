# Field Symbols

Field Symbols are pointers that reference existing memory instead of creating copies.

They improve performance when processing large Internal Tables.

---

# Declaration

```abap
FIELD-SYMBOLS <fs_material> TYPE mara.
```

---

# Assign

```abap
READ TABLE gt_material ASSIGNING <fs_material> INDEX 1.
```

---

# Example

```abap
FIELD-SYMBOLS <fs_material> TYPE mara.

LOOP AT gt_material ASSIGNING <fs_material>.

  WRITE / <fs_material>-matnr.

ENDLOOP.
```

---

# Why Use Field Symbols?

Without Field Symbol

```
Internal Table
      ↓
Copy Row
      ↓
Work Area
```

With Field Symbol

```
Internal Table
      ↓
Reference
      ↓
Field Symbol
```

No copy is created.

---

# Modifying Data

```abap
LOOP AT gt_material ASSIGNING <fs_material>.

  <fs_material>-mtart = 'FERT'.

ENDLOOP.
```

The Internal Table is updated immediately.

---

# Best Practices

- Always check if a Field Symbol has been assigned.

```abap
IF <fs_material> IS ASSIGNED.

ENDIF.
```

- Use Field Symbols when processing large tables.