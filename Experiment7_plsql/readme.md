# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

### PROGRAM

```
DECLARE
    a NUMBER := 25;
    b NUMBER := 40;
BEGIN
    IF a > b THEN
        DBMS_OUTPUT.PUT_LINE('Greatest number is: ' || a);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Greatest number is: ' || b);
    END IF;
END;
/
```

**Expected Output:**  
<img width="733" height="828" alt="image" src="https://github.com/user-attachments/assets/39b67fd7-9fe4-45ba-9750-c5b1d8cdc642" />


## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

### PROGRAM:
```
DECLARE
    n NUMBER := 10;
    sum NUMBER := 0;
BEGIN
    FOR i IN 1..n LOOP
        sum := sum + i;
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;
/
```


**Expected Output:**

<img width="1917" height="916" alt="image" src="https://github.com/user-attachments/assets/0ae7a36c-1b23-4393-97cb-711ae0dffe21" />

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

### PROGRAM:

```
DECLARE
    n NUMBER := 10;
    a NUMBER := 0;
    b NUMBER := 1;
    c NUMBER;
BEGIN
    DBMS_OUTPUT.PUT_LINE('Fibonacci Series:');

    FOR i IN 1..n LOOP
        DBMS_OUTPUT.PUT(a || ' ');
        c := a + b;
        a := b;
        b := c;
    END LOOP;

    DBMS_OUTPUT.NEW_LINE;
END;
/
```

**Expected Output:**  

<img width="1916" height="913" alt="image" src="https://github.com/user-attachments/assets/8bd1c9cf-c771-4512-8ecf-03dd8dd814de" />


## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

### PROGRAM:
```
DECLARE
    n NUMBER := 12345;
    rev NUMBER := 0;
    rem NUMBER;
BEGIN
    WHILE n > 0 LOOP
        rem := MOD(n, 10);
        rev := rev * 10 + rem;
        n := TRUNC(n / 10);
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Reversed Number: ' || rev);
END;
/

```

**Expected Output:**  

<img width="1916" height="915" alt="image" src="https://github.com/user-attachments/assets/60b4d94b-a64c-40f9-b422-e67dac96981a" />



## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

###PROGRAM:

```
DECLARE
    a NUMBER := 25;
    b NUMBER := 40;
    c NUMBER := 30;
    max_num NUMBER;
BEGIN
    IF a > b AND a > c THEN
        max_num := a;
    ELSIF b > a AND b > c THEN
        max_num := b;
    ELSE
        max_num := c;
    END IF;

    DBMS_OUTPUT.PUT_LINE('Largest number is: ' || max_num);
END;
/
```

**Expected Output:**  

<img width="1916" height="912" alt="image" src="https://github.com/user-attachments/assets/2739b7ff-0048-4276-8cc2-c32b12b007be" />


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
