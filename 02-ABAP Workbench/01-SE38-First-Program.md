# First ABAP Program (SE38)

## Objective

In this chapter, you will create your first ABAP executable program using Transaction Code **SE38**.

---

## Step 1

Open Transaction Code:

```
SE38
```

---

## Step 2

Enter a program name.
![Creating First Program](https://i.imgur.com/5YXkVqE.png) 
Example:

```
Z_HELLO_WORLD
```

> Customer-developed programs should begin with `Z` or `Y`.

Click **Create**.

---

## Step 3

Choose

- Executable Program

Click **Save**.

---

## Step 4

Enter:

- Title
- Development Class (Package)

or choose

```
Local Object ($TMP)
```

if this is only for learning.

---

## Step 5

Write the following code.

```abap
REPORT z_hello_world.

WRITE 'Hello World!'.
```

Activate (**Ctrl + F3**).

Execute (**F8**).

---

## Output

```
Hello World!
```

Congratulations! You have created your first ABAP program.

---

# Understanding the code

```abap
REPORT z_hello_world.
```

Defines the program name.

```abap
WRITE 'Hello World!'.
```

Displays text on the output screen.

---

# Exercise

Modify the program to display:

```
Hello World!
Welcome to ABAP.
```


# WRITE Statement

```abap
REPORT z_write.

WRITE 'Hello'.

WRITE 'World'.
```

Output

```
HelloWorld
```

---

## New Line

```abap
WRITE / 'Hello'.

WRITE / 'World'.
```

Output

```
Hello
World
```

---

## Multiple Lines

```abap
WRITE: / 'Apple',
       / 'Orange',
       / 'Banana'.
```

---

## Skip Line

```abap
WRITE 'Hello'.

SKIP.

WRITE 'World'.
```

---

## Horizontal Line

```abap
ULINE.
```

---

## Position Cursor

```abap
WRITE AT 20 'SAP'.
```