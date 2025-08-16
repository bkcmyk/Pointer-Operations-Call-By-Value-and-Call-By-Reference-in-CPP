# Pointer Operations (Call by Value and Call by Reference)

---

## Aim  
To study and implement **Pointer Operations** using *Call by Value* and *Call by Reference* in C++.  

---

## Tools Used  
-   VS Code or any other Online C++ Compiler

---

## Theory  

### What are Pointers?  

A **pointer** is a variable that stores the memory address of another variable. Instead of storing data directly, a pointer “points” to the location in memory where the data is stored.  

**Syntax:**  
```cpp
int a = 10;
int *p = &a; // p stores the address of a
```

- `&` → Address-of operator (gives memory location)  
- `*` → Dereference operator (accesses the value stored at that memory location)  

Pointers allow **indirect access** and manipulation of variables. They are widely used in dynamic memory allocation, arrays, strings, and function arguments.  

---

## Function Call Mechanisms in C++  

Functions can receive arguments in **two major ways**:  

---

### 1. Call by Value  

In **Call by Value**, a copy of the actual parameter is passed to the function.  
Changes made inside the function **do not affect** the original variable, since the function works only on the local copy.  
This makes it safe because the actual data remains unchanged, but it is less efficient for large data structures because copies must be made.  

**Function Definition:**  
```cpp
void callByValue(int x) {
    x = x + 10;  
    cout << "Inside callByValue: " << x << endl;
}
```

**Function Call Statement:**  
```cpp
int num = 20;
callByValue(num);   // Call by Value
```

---

### 2. Call by Reference  

In **Call by Reference**, instead of passing a copy, the **address of the variable** is passed to the function.  
This allows the function to operate on the actual variable, so any modifications inside the function **directly affect the original value**.  
It is more memory-efficient because no extra copies are created, but requires care since it can change the original data unintentionally.  

**Function Definition:**  
```cpp
void callByReference(int *x) {
    *x = *x + 10;  
    cout << "Inside callByReference: " << *x << endl;
}
```

**Function Call Statement:**  
```cpp
int num = 20;
callByReference(&num);   // Call by Reference
```

---

### Comparison of Call by Value vs Call by Reference  

| Feature                  | Call by Value                     | Call by Reference                   |
|--------------------------|-----------------------------------|--------------------------------------|
| Data Passed              | Copy of actual value              | Address of actual variable          |
| Effect on Original Value | Unchanged                         | Can be modified                     |
| Memory Usage             | Requires extra memory for copies  | More efficient (no copies made)     |
| Safety                   | Safer, no accidental modification | Less safe, may change original data |
| Speed                    | Slower for large objects          | Faster, as no copies are created    |

---

### Why Use Call by Reference with Pointers?  

1. To **modify actual variables** in the calling function.  
2. To **save memory and processing time** by avoiding unnecessary copies (important in large arrays, objects, or structures).  
3. To implement advanced concepts like **dynamic memory allocation, linked lists, trees, and graphs**.  

---

## Algorithms for Programs  

### A. Swap Two Integers — Call by Reference (Pointers)  
1. Start  
2. Initialize two integers `a` and `b`  
3. Display values before swap  
4. Call `swap(&a, &b)`  
5. Inside `swap`:  
   - Store `*x` in `temp`  
   - Assign `*x = *y`  
   - Assign `*y = temp`  
6. Return to `main` and display values after swap  
7. Stop  

---

### B. Swap Two Integers — Call by Value  
1. Start  
2. Initialize two integers `a` and `b`  
3. Display values before swap  
4. Call `swap(a, b)` (copies are passed)  
5. Inside `swap`:  
   - Store `x` in `temp`  
   - Assign `x = y`  
   - Assign `y = temp`  
6. Return to `main` and display values after swap (unchanged)  
7. Stop  

---

### C. Bonus Eligibility Program  
1. Start  
2. Input: `years_completed`, `project`, `new_project`, `profit`  
3. Initialize `count = 0`  
4. Increment count if criteria met:  
   - years ≥ 1  
   - project completed  
   - new project started  
   - profit ≥ 100000  
5. If `count ≥ 3`:  
   - Input `salary`  
   - Call `bonus(salary)` → returns updated salary (20% increase)  
   - Print new salary  
6. Else: Display how many more criteria needed  
7. Stop  

---

### D. Reverse a String (Char Array)  
1. Start  
2. Input string `text`  
3. Find length until `'\0'`  
4. For `i = 0 to length/2 - 1`:  
   - Swap `str[i]` with `str[length - i - 1]`  
5. Display reversed string  
6. Stop  

---

## Applications  

- **Call by Reference (pointers):** swapping values, sorting algorithms, modifying arrays and linked lists.  
- **Call by Value:** safe for mathematical computations where the original must remain unchanged.  
- **Bonus Program:** HR/payroll logic, eligibility and appraisal systems.  
- **String reversal:** palindrome checking, encoding/decoding, text processing.  

---

## Outcomes  

- Differentiated between **Call by Value** and **Call by Reference**.  
- Understood how pointers allow in-place modification of data.  
- Implemented algorithms for swapping, decision-making, and string manipulation.  
- Learned practical applications of function call mechanisms.  

---

## Conclusion  

- **Call by Value** passes a copy → original variable unchanged.  
- **Call by Reference** passes an address → original variable is modified.  
- Pointers make functions more powerful and efficient but need careful handling.  
- Practical examples (swap, salary bonus, string reverse) show clear applications of pointer operations.  
