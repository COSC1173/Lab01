# Lab 01 — Welcome Banner

| | |
|---|---|
| **Course** | COSC 1173 Programming Lab |
| **Week** | 1 |
| **Textbook** | Liang, *Introduction to Java Programming and Data Structures* — **Chapter 1** |
| **Time budget** | 60 minutes |
| **Points** | 100 |

---

## Learning Objectives

By the end of this session you will be able to:

1. Compile a Java source file with `javac` and execute it with `java`.
2. Explain the required relationship between a public class name and its file name.
3. Print text with `System.out.println`.
4. Use the escape sequence `\"` to place a double quotation mark inside a string literal.
5. Explain why `259 / 3` and `259 / 3.0` produce different answers.

---

## Files
Download the source code from Blackboard

| Path | Who edits it | Purpose |
|---|---|---|
| `./src/Lab01Welcome.java` | **You** | The program you complete |

---

## Background

A Java program lives inside a class, and execution begins in `main`:

```java
public class Lab01Welcome {          // the class name MUST match the file name Lab01Welcome.java
    public static void main(String[] args) {   // the JVM starts here
        System.out.println("text");  // println prints the text, then moves to a new line
    }
}
```

Two details that cost students points every term:

**Escape sequences.** A double quote ends a string literal, so to print one you must escape it:

```java
System.out.println("She said \"hello\" loudly.");   // prints: She said "hello" loudly.
```

**Integer versus floating-point division.** Java looks at the *operands*, not at what you intended:

```java
System.out.println((88 + 92 + 79) / 3);     // prints 86    — both operands are int, so the remainder is discarded
System.out.println((88 + 92 + 79) / 3.0);   // prints 86.33333333333333 — 3.0 is a double, so the result is a double
```

---

## Instructions

### Step 0 — Set up (5 minutes)

Create a new Project in Eclipse, name as Lab01Welcome
Import the downloaded source into the project


Open the folder in Eclipse, then open `lab01Welcome/src/Lab01Welcome.java`.

### Step 1 — Fill in your identity block

Replace the two placeholders at the top of the file with your name and today's date.

### Step 2 — The course line

Step 1 of the file is already written for you as an example. Replace the `"REPLACE ME"` in Step 2 so the program prints exactly:

```
COSC 1173 Programming Lab
```

Capitalisation and spacing are compared exactly.

### Step 3 — Your name line

Print your own name in this form (use your real name, not the example):

```
Student: Jane Doe
```

### Step 4 — The escaped quotation marks

Print this line, **including** the quotation marks around the book title:

```
Welcome to "Introduction to Java Programming"
```

Write each interior quotation mark as `\"`. If you type a bare `"`, the compiler reports
`unclosed string literal` — that error message is telling you exactly this.

### Step 5 — The computed average

Print the average of the three scores 88, 92, and 79 in this form:

```
Average score: 86.33333333333333
```

**The number must be computed by an arithmetic expression inside the `println`.** Typing the
answer as a literal earns zero for this step, and the test driver detects it, because dividing by
`3` instead of `3.0` yields `86` and fails the check.

### Step 6 — Close the banner

Print the same 40-asterisk line used in Step 1. Copy and paste it so the two banners match exactly.

### Step 7 — Comment every line

See the commenting standard below. Do this before you run out of time, not after.

---

## Commenting Standard (20 of 100 points)

Every executable statement needs a comment that explains **what the statement accomplishes and
why**. A comment that merely restates the syntax earns nothing.

```java
// WEAK — restates the code in English, adds no information
System.out.println("Average score: " + (88 + 92 + 79) / 3.0); // prints a line

// STRONG — explains the reasoning
// Divides by 3.0 rather than 3 so the compiler performs floating-point division;
// integer division would discard the fractional part and report 86.
System.out.println("Average score: " + (88 + 92 + 79) / 3.0);
```


---

## Compile, Run, and Test

To run your program by itself and see its output:
from Eclipse or any IDE

```bash
javac Lab01Welcome.java
java  Lab01Welcome
```

---

## Expected Output

```
****************************************
COSC 1173 Programming Lab
Student: Jane Doe
Welcome to "Introduction to Java Programming"
Average score: 86.33333333333333
****************************************
```

---

## Grading Rubric

| Criterion | Points |
|---|---|
| All 10 checks in the test driver pass | 60 |
| Line comments explain every statement | 20 |
| Naming, indentation, identity block completed | 10 |
| Committed and pushed before the deadline with a meaningful message | 10 |

---

## Submission Checklist

- [ ] Your source code, the .java file
- [ ] The screenshoot of your output after program run correctly
- [ ] Your name and date appear at the top of the file.
- [ ] No `REPLACE ME` text remains.

---

## Stretch Goal

Make the banner width adjustable: declare `int width = 40;` and build the asterisk line without
typing 40 asterisks. You have not covered loops yet — investigate `"*".repeat(width)`.

---

## Troubleshooting

| Symptom | Cause | Fix |
|---|---|---|
| `class Lab01Welcome is public, should be declared in a file named Lab01Welcome.java` | File renamed | Restore the original file name |
| `unclosed string literal` | A bare `"` inside a string | Write it as `\"` |
| Average prints `86` | Integer division | Divide by `3.0` |
| `javac: command not found` | JDK not on the PATH | Reinstall the JDK; a JRE alone is not enough |
| Test says "First line is a 40-asterisk banner: false" | Wrong asterisk count | Copy the banner from Step 1 |
