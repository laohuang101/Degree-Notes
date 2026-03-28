# Data Structures - Comprehensive Lecture Notes

## Table of Contents
1. [Module 1: Overview of Data Structure](#module-1-overview-of-data-structure)
2. [Module 2: Overview of C++](#module-2-overview-of-c)
3. [Module 3: Arrays](#module-3-arrays)
4. [Module 4: Class and Struct](#module-4-class-and-struct)
5. [Module 5: Pointer](#module-5-pointer)
6. [Module 6: Linked List Part 1](#module-6-linked-list-part-1)
7. [Module 7: Linked List Part 2](#module-7-linked-list-part-2)
8. [Module 8: Linked List Part 3](#module-8-linked-list-part-3)
9. [Module 9: Stacks](#module-9-stacks)
10. [Module 10: Queues](#module-10-queues)
11. [Module 11: Trees and Binary Trees](#module-11-trees-and-binary-trees)
12. [Module 12: Binary Search Trees](#module-12-binary-search-trees)
13. [Module 13: Graphs](#module-13-graphs)
14. [Module 14: Graph Algorithms](#module-14-graph-algorithms)

---

## Module 1: Overview of Data Structure

### Course Information

| Aspect | Details |
|--------|---------|
| **Course Code** | CT077-3-2-DSTR |
| **Course Title** | Data Structures |
| **Chapter** | Chapter 1 - Fundamental Concepts |

### Learning Outcomes

At the end of this topic, you should be able to:
1. Understand the meaning of data structure
2. Understand the fundamental aspects of an algorithm and its characteristics
3. Understand the relationship between data, data structures, and algorithms

### Program Development Life Cycle

| Step | Description |
|------|-------------|
| 1 | Define the problem statement precisely |
| 2 | Select the best suitable algorithm to solve the problem |
| 3 | Implement the solution (coding) |
| 4 | Test the code |
| 5 | Debug and revise if required |

### Data vs Data Type vs Data Structure vs ADT

| Concept | Definition |
|---------|------------|
| **Data** | Raw facts and figures processed by computers |
| **Data Type** | A classification of data that determines possible values and operations |
| **Data Structure** | Organization of data for efficient algorithm efficiency |
| **Abstract Data Type (ADT)** | Data declaration packaged with meaningful operations |

### Atomic vs Composite Data

| Type | Description | Example |
|------|-------------|---------|
| **Atomic Data** | Single, non-decomposable entity (scalar data) | Integer number 1234 |
| **Composite Data** | Can be broken down into subfields with meaning | Student record: Roll_Number, Name, Branch, Year |

### Simple vs Structured Data Types

| Type | Description | Characteristics |
|------|-------------|-----------------|
| **Simple Type** | Variables store only one value at a time | Also called Primitive or Built-in Types |
| **Structured Type** | Each data item is a collection of other data items | Similar to classes, but without methods |

### Simple Data Types in C++

| Type | Description | Notes |
|------|-------------|-------|
| **int** | Integer values | Can be unsigned (positive only) |
| **float** | Floating-point numbers | Single precision |
| **double** | Double precision floating-point | More precise than float |
| **char** | Character data | Can be unsigned |
| **bool** | Boolean values | Not supported by all C++ compilers |

### Data Structure Definition

A data structure is:
- A collection of atomic and composite data types into a set with defined relationships
- A combination of elements, each of which is either a data type or another data structure
- A set of associations or relationships involving the combined elements

### Abstract Data Type (ADT)

| Aspect | Description |
|--------|-------------|
| **Definition** | Data declaration packaged with operations meaningful for the data type |
| **Features** | Encapsulates data and operations, hides them from user |
| **Components** | Declaration of data, implementation of operations, encapsulation |
| **Example** | Queue - users only need enqueue() and dequeue(), not the implementation |

### ADT Example - Queue

| Structure | Implementation | User Perspective |
|-----------|----------------|------------------|
| Queue | Array | Enqueue, dequeue data |
| Queue | Linked List | Enqueue, dequeue data |
| Queue | File | Enqueue, dequeue data |

Users should NOT be aware of which structure is used. As long as they can enqueue and dequeue, the implementation doesn't matter.

### Classification of Data Structures

| Category | Examples |
|----------|----------|
| **Linear** | Arrays, Linked Lists, Stacks, Queues |
| **Non-Linear** | Trees, Graphs |
| **Homogeneous** | Arrays |
| **Heterogeneous** | Structures, Classes |

### Algorithm Definition

An algorithm is:
- A clearly specified set of simple instructions to be followed to solve a problem
- The steps to be carried out in order to accomplish a particular task

### Relationship Among Data, Data Structures, and Algorithms

**Analogy: Movie Theater Seats**

| Case | Seat Arrangement | Finding Seat? | Time Required |
|------|-----------------|---------------|---------------|
| 1 | Not numbered | No | Impossible |
| 2 | Numbered randomly | Yes | Long time (check each seat) |
| 3 | Numbered sequentially | Yes | Faster than Case 2 |
| 4 | Numbered by row and seat | Yes | Fastest (check specific row) |

**Analysis:**
- Correctness: Can they find their seat?
- Efficiency: How long will it take?

### Measuring Efficiency

| Resource | Description | Goal |
|----------|-------------|------|
| **Time** | How long to complete a process | Minimize |
| **Space** | How much memory used | Minimize |
| **Balance** | Optimum algorithm balances both at lowest possible value | Big O complexity O(n) |

### Big O Notation

| Complexity | Description | Example |
|------------|-------------|---------|
| **O(1)** | Constant time | Array access by index |
| **O(n)** | Linear time | Linear search |
| **O(n²)** | Quadratic time | Nested loops |
| **O(log n)** | Logarithmic time | Binary search |
| **O(n log n)** | Linearithmic time | Merge sort, quicksort |

### Algorithm Complexity Cases

| Case | Definition | Function |
|------|------------|----------|
| **Best-case** | Minimum number of steps on any instance of size n | f(n) = min steps |
| **Worst-case** | Maximum number of steps on any instance of size n | f(n) = max steps |
| **Average-case** | Average number of steps on any instance of size n | f(n) = avg steps |

### Key Terms

| Term | Definition |
|------|------------|
| **Data** | Raw facts and figures |
| **Data Type** | Classification of data |
| **Data Structure** | Organization of data for efficiency |
| **ADT** | Data with operations, implementation hidden |
| **Algorithm** | Set of instructions to solve a problem |
| **Complexity** | Measure of algorithm efficiency |
| **Big O** | Mathematical notation for complexity |

---

## Module 2: Overview of C++

### Course Information

| Aspect | Details |
|--------|---------|
| **Course Code** | CT077-3-2-DSTR |
| **Course Title** | Data Structures |
| **Chapter** | Chapter 2 - Fundamental Concept of Programming (Part 1) |

### Learning Outcomes

At the end of this topic, you should be able to:
1. Understand how to write a simple C++ program and use preprocessor directives
2. Incorporate both basic and advanced control structures appropriately
3. Demonstrate understanding of structure design by implementing programs with functions

### Creating a C++ Program

| Component | Description |
|-----------|-------------|
| **Preprocessor Directives** | Commands to preprocessor (start with #) |
| **Program Statements** | Functions, classes, type definitions |
| **Source Code** | Files with .cpp and .h extensions |
| **Compiler Output** | Object code (.obj files) |
| **Linker Output** | Executable file (.exe) |

### Basic C++ Program Structure

```cpp
#include <iostream>        // Preprocessor directive
using namespace std;       // Namespace declaration

int main() {               // Main function
    // Program statements
    return 0;              // Return statement
}
```

### Preprocessor Directives

| Directive | Purpose | Example |
|-----------|---------|---------|
| `#include` | Include header file | `#include <iostream>` |
| `#define` | Define macro | `#define MAX 100` |

### Common Header Files

| Header | Purpose |
|--------|---------|
| `<iostream>` | Input/output streams (cin, cout) |
| `<string>` | String class |
| `<cmath>` | Mathematical functions |
| `<cstdlib>` | General utilities |

### Input/Output Operations

| Operation | Description | Example |
|-----------|-------------|---------|
| `cin` | Input stream | `cin >> variable;` |
| `cout` | Output stream | `cout << "Hello" << endl;` |
| `endl` | End line and flush | `cout << value << endl;` |

### Control Structures

| Type | Structure | Description |
|------|-----------|-------------|
| **Selection** | One-way, Two-way, Multiple | Control flow based on conditions |
| **Repetition** | while, for, do...while | Loop structures |

### Selection Control

| Structure | Syntax | Use Case |
|-----------|--------|----------|
| **One-way** | `if (condition) statement;` | Execute if condition true |
| **Two-way** | `if (condition) statement1; else statement2;` | Either-or choice |
| **Multiple (nested)** | `if` inside another `if` | Test multiple conditions |
| **Switch** | `switch(expression) { case value: ...; }` | Multiple value comparison |

### One-Way Selection

```cpp
if (condition) {
    // statement to execute if condition is true
}
```

### Two-Way Selection

```cpp
if (condition) {
    // statement1 (if true)
} else {
    // statement2 (if false)
}
```

### Nested If

```cpp
if (condition1) {
    if (condition2) {
        // both conditions true
    }
}
```

### Switch Structure

```cpp
switch (expression) {
    case value1:
        // statements
        break;
    case value2:
        // statements
        break;
    default:
        // default statements
}
```

### Repetition Control

| Loop Type | Syntax | Best Used When |
|-----------|--------|----------------|
| **while** | `while (condition) statement;` | Unknown iterations, may be zero |
| **for** | `for (init; condition; update) statement;` | Known iterations |
| **do...while** | `do { statement; } while (condition);` | Unknown iterations, at least one |

### While Loop

```cpp
while (condition) {
    // statement(s) to repeat
}
```

**Types:**
| Type | Description |
|------|-------------|
| **Counter-controlled** | Known number of iterations |
| **Sentinel-controlled** | Ends when sentinel value encountered |
| **Flag-controlled** | Uses boolean variable to control loop |

### For Loop

```cpp
for (initialization; condition; update) {
    // statement(s) to repeat
}
```

**Control Statements:**
| Statement | Purpose |
|-----------|---------|
| `initialization` | Executed once at start |
| `condition` | Tested before each iteration |
| `update` | Executed after each iteration |

### Do...While Loop

```cpp
do {
    // statement(s) to repeat
} while (condition);
```

**Characteristic:** Always executes at least once

### Choosing the Right Loop

| Situation | Recommended Loop |
|-----------|------------------|
| Known iterations | `for` loop |
| Unknown iterations, may be zero | `while` loop |
| Unknown iterations, at least one | `do...while` loop |

### Functions

| Component | Description |
|-----------|-------------|
| **Function Prototype** | Function heading without body |
| **Function Definition** | Complete function with body |
| **Function Call** | Invoking the function |
| **Return Type** | Type of value returned |
| **Parameters** | Values passed to function |

### Function Syntax

```cpp
returnType functionName(parameterType1 param1, parameterType2 param2) {
    // function body
    return value;  // if returnType is not void
}
```

### Function Prototype

```cpp
returnType functionName(parameterType1, parameterType2);
```

**Purpose:** 
- Provides function signature to compiler
- Not necessary to specify variable names
- Must specify data types

### Passing Parameters

| Method | Description | Effect |
|--------|-------------|--------|
| **By Value** | Copy of value passed | Original unchanged |
| **By Reference** | Address passed | Original can be changed |
| **By Pointer** | Pointer passed | Original can be changed |

### By Value Example

```cpp
void increment(int x) {
    x = x + 1;  // Only affects local copy
}
```

### By Reference Example

```cpp
void increment(int& x) {
    x = x + 1;  // Affects original
}
```

### Key Terms

| Term | Definition |
|------|------------|
| **cin** | Input stream |
| **cout** | Output stream |
| **if...else** | Selection control |
| **switch** | Multiple selection |
| **for** | Counter-controlled loop |
| **while** | Condition-controlled loop |
| **do...while** | Post-test loop |
| **Function Prototype** | Function declaration |
| **Parameter Passing** | By value, by reference |

---

## Module 3: Arrays

### Course Information

| Aspect | Details |
|--------|---------|
| **Course Code** | CT077-3-2-DSTR |
| **Course Title** | Data Structures |
| **Chapter** | Chapter 3 - Fundamental Concept of Programming (Part 2) |

### Learning Outcomes

At the end of this topic, you should be able to:
1. Understand how to declare and manipulate data into arrays
2. Explain the difference between passing parameters by value or by reference
3. Demonstrate how to pass an array to a function

### Arrays

| Characteristic | Description |
|----------------|-------------|
| **Definition** | Collection of fixed number of components with same data type |
| **Arrangement** | Components arranged in list form (1D) or table form (2D) |
| **Memory** | Adjacent memory locations for fast random access |
| **Index** | Starts at 0 |

### 1D Array Declaration

```cpp
dataType arrayName[arraySize];
```

| Example | Description |
|---------|-------------|
| `int num[5];` | Array of 5 integers |
| `double sales[10];` | Array of 10 doubles |
| `char name[20];` | Array of 20 characters |

### Accessing Array Elements

```cpp
arrayName[index];
```

| Example | Description |
|---------|-------------|
| `list[3] = 10;` | Assign 10 to index 3 |
| `cout << list[6];` | Display value at index 6 |
| `list[5] = list[3] + list[6];` | Add values and assign |

**Note:** Index starts at 0, so `list[5]` is the 6th element

### Array Initialization

| Method | Syntax | Description |
|--------|--------|-------------|
| **During Declaration** | `int arr[] = {1, 2, 3};` | Size determined by values |
| **Partial** | `int arr[10] = {8, 5, 12};` | First 3 initialized, rest 0 |
| **All Zero** | `int arr[10] = {0};` | All elements initialized to 0 |

### Array Restrictions

| Operation | Legal? | Solution |
|-----------|--------|----------|
| `cout << arr;` | No (prints address) | Loop through elements |
| `arr1 = arr2;` | No (aggregate assignment) | Element-by-element copy |
| `arr1 == arr2;` | No (compares addresses) | Element-by-element compare |

### 2D Arrays

| Characteristic | Description |
|----------------|-------------|
| **Definition** | Collection of components in two dimensions |
| **Also Called** | Matrices or tables |
| **Declaration** | `dataType arrayName[rows][cols];` |

### 2D Array Declaration

| Example | Description |
|---------|-------------|
| `double sales[10][5];` | 10 rows, 5 columns |
| `int matrix[3][4];` | 3 rows, 4 columns |

### Accessing 2D Array Elements

```cpp
arrayName[rowIndex][colIndex];
```

| Example | Description |
|---------|-------------|
| `sales[5][3] = 25.75;` | Assign to row 5, column 3 |

### 2D Array Initialization

```cpp
int numbers[4][5] = {
    {1, 2, 3, 4, 5},
    {10, 9, 8, 7, 6},
    {11, 12, 13, 14, 15},
    {20, 19, 18, 17, 16}
};
```

### Passing Parameters to Functions

| Method | Syntax | Effect on Original |
|--------|--------|-------------------|
| **By Value** | `void func(int x);` | Unchanged |
| **By Reference** | `void func(int& x);` | Can be changed |

### Value Parameter

- Formal parameter receives copy of actual parameter
- Changes to formal parameter don't affect actual parameter
- Original stays intact

### Reference Parameter

- Formal parameter receives address of actual parameter
- Changes to formal parameter affect actual parameter
- Uses `&` symbol before parameter name

### Reference Parameter Example

```cpp
void grow(int& x) {
    x = x + 1;  // Affects original
}
```

### When to Use Reference Parameters

| Situation | Benefit |
|-----------|---------|
| Change actual parameter | Direct modification |
| Return multiple values | Pass multiple references |
| Save memory/time | No copying of large objects |

### Arrays as Function Parameters

| Characteristic | Description |
|----------------|-------------|
| **Passed By** | Reference (always) |
| **& Symbol** | NOT used |
| **Size** | Usually omitted, ignored if provided |
| **Size Passing** | Must be passed separately |

### Array Parameter Example

```cpp
void processArray(int arr[], int size) {
    // Process array
}
```

### Key Terms

| Term | Definition |
|------|------------|
| **1D Array** | Single-dimensional array |
| **2D Array** | Two-dimensional array (matrix) |
| **Passing by Value** | Copy of value passed |
| **Passing by Reference** | Address passed |

---

## Module 4: Class and Struct

### Course Information

| Aspect | Details |
|--------|---------|
| **Course Code** | CT077-3-2-DSTR |
| **Course Title** | Data Structures |
| **Chapter** | Chapter 4 - Fundamental Concept of Programming (Part 3) |

### Learning Outcomes

At the end of this topic, you should be able to:
1. Explore how to define classes and member functions, and declare objects
2. Examine how constructors and destructor of a class work
3. Understand the concepts between structs, classes, and objects in C++

### Classes and Objects

| Concept | Description |
|---------|-------------|
| **Class** | Category or template for objects |
| **Object** | Instance of a class with specific values |
| **Attributes** | Properties describing the class (data members) |
| **Operations** | Actions the class can perform (member functions) |

### Class Declaration

```cpp
class ClassName {
public:
    // Public members
private:
    // Private members
};
```

### Class Example: Rectangle

```cpp
class Rectangle {
private:
    int width, height;
public:
    void setSize(int, int);
    int area() { return width * height; }
};
```

### Member Functions

| Type | Description | Example |
|------|-------------|---------|
| **Inside Class** | Definition within class | `int area() { return w*h; }` |
| **Outside Class** | Definition outside class | `void Rectangle::setSize(int a, int b) { w=a; h=b; }` |

### Access Specifiers

| Specifier | Accessibility | Default |
|-----------|---------------|---------|
| **public** | Accessible from anywhere | - |
| **private** | Accessible only within class | Class default |
| **protected** | Accessible in class and derived classes | Struct default |

### Creating Objects

| Method | Syntax | Memory Location |
|--------|--------|-----------------|
| **Stack** | `Rectangle rect;` | Stack memory |
| **Heap** | `Rectangle* rect = new Rectangle;` | Heap memory |

### Accessing Members

| Method | Syntax | Example |
|--------|--------|---------|
| **Dot Operator** | `object.member` | `rect.area()` |
| **Arrow Operator** | `pointer->member` | `rectPtr->area()` |

### Object Assignment

| Language | Behavior |
|----------|----------|
| **C++** | Copies values of each data member |
| **Java** | Makes both references point to same object |

### Static Members

| Characteristic | Description |
|----------------|-------------|
| **Declaration** | Use `static` keyword |
| **Access** | Class name and scope resolution (`::`) |
| **Existence** | Exist even if no object exists |
| **Shared** | Shared among all objects |

### Static Member Example

```cpp
class A {
public:
    static int sValue;
};
int A::sValue = 1;  // Initialize outside class
```

### Constructors

| Characteristic | Description |
|----------------|-------------|
| **Purpose** | Initialize object upon creation |
| **Name** | Same as class name |
| **Return Type** | No return type (not even void) |
| **Default** | Provided implicitly if none declared |
| **Overloading** | Multiple constructors with different parameters |

### Constructor Example

```cpp
class Rectangle {
public:
    Rectangle(int a, int b) {
        width = a;
        height = b;
    }
};
```

### Constructor Overloading

```cpp
Rectangle() { width = 5; height = 5; }           // Default
Rectangle(int a, int b) { width = a; height = b; } // Parameterized
Rectangle(int a) { width = a; height = a; }        // Square
```

### Destructors

| Characteristic | Description |
|----------------|-------------|
| **Purpose** | Clean up/delete object |
| **Name** | `~ClassName` |
| **Parameters** | No parameters |
| **Return Type** | No return type |
| **Execution** | Automatically when object goes out of scope or deleted |

### Destructor Example

```cpp
~Rectangle() {
    // Cleanup code
}
```

### Array of Objects

| Characteristic | Description |
|----------------|-------------|
| **Declaration** | `Rectangle rects[ARRAY_SIZE];` |
| **Creation** | Uses default constructor |
| **Access** | `rects[2].setSize(5, 4);` |

### Pointers to Class Objects

| Operation | Syntax |
|-----------|--------|
| **Declaration** | `Rectangle* rectPtr = &rect;` |
| **Access (Dereference)** | `(*rectPtr).area();` |
| **Access (Arrow)** | `rectPtr->area();` |

### "this" Pointer

| Characteristic | Description |
|----------------|-------------|
| **Purpose** | Reference to current object |
| **Type** | Special pointer |
| **Usage** | Inside member functions |
| **Syntax** | `this->member` |

### this Pointer Example

```cpp
void setSize(int width, int height) {
    this->width = width;
    this->height = height;
}
```

### Struct vs Class

| Feature | Struct | Class |
|---------|--------|-------|
| **Default Access** | Public | Private |
| **Security** | Not secure (cannot hide details) | Secure (can hide details) |
| **Usage** | Group heterogeneous data | Model objects with methods |

### Struct Example

```cpp
struct Employee {
    string name;
    int id;
    double salary;
};
```

### Key Terms

| Term | Definition |
|------|------------|
| **Class** | Template for objects |
| **Object** | Instance of a class |
| **Constructor** | Initialization function |
| **Destructor** | Cleanup function |
| **Struct** | Data structure with public members |
| **this Pointer** | Reference to current object |

---

## Module 5: Pointer

### Course Information

| Aspect | Details |
|--------|---------|
| **Course Code** | CT077-3-2-DSTR |
| **Course Title** | Data Structures |
| **Chapter** | Chapter 5 - Fundamental Concept of Programming (Part 4) |

### Learning Outcomes

At the end of this topic, you should be able to:
1. Understand how to declare and manipulate pointer variables
2. Explore the concept of dynamic allocation in memory
3. Use the new and delete operators to manipulate dynamic variables

### Pointers

| Characteristic | Description |
|----------------|-------------|
| **Definition** | Variable whose value is memory address of another variable |
| **Direct Reference** | Variable name directly references value |
| **Indirect Reference** | Pointer indirectly references value |
| **Indirection** | Referencing value through pointer |

### Pointer Declaration

```cpp
dataType *pointerName;
```

| Example | Description |
|---------|-------------|
| `int *countPtr;` | Pointer to integer |
| `double *pricePtr;` | Pointer to double |
| `char *charPtr;` | Pointer to character |

### Pointer Initialization

| Method | Value | Description |
|--------|-------|-------------|
| `0` | 0 | Null pointer (old style) |
| `NULL` | NULL | Null pointer (old style) |
| `nullptr` | nullptr | Null pointer (C++11) |

**Important:** Pointers must be initialized

### Pointer Operators

| Operator | Name | Description |
|----------|------|-------------|
| `&` | Address-of | Returns address of operand |
| `*` | Dereferencing/Indirection | Refers to object pointer points to |

### Pointer Example

```cpp
int i = 11;
int *iPtr;
iPtr = &i;  // iPtr now contains address of i
cout << *iPtr;  // Outputs 11
```

### Pointer Variables

| Characteristic | Description |
|----------------|-------------|
| **Value Stored** | Memory address |
| **Accessing Content** | Requires dereferencing operator `*` |
| **Modification** | Can modify value through pointer |

### Passing Pointers to Functions

| Benefit | Description |
|---------|-------------|
| **Modify Original** | Function can manipulate actual parameter |
| **Similar to Reference** | Same effect as passing by reference |
| **C Language** | Heavily used (no reference concept) |

### Pointer Parameter Example

```cpp
void increment(int *p) {
    *p = *p + 1;  // Affects original value
}

int x = 9;
increment(&x);  // Pass address of x
```

### Pointers and Classes

| Operation | Syntax | Equivalent |
|-----------|--------|------------|
| **Dereference then access** | `(*str).length()` | - |
| **Arrow operator** | `str->length()` | `(*str).length()` |

### Dynamic Memory Allocation

| Memory Area | Description | Management |
|-------------|-------------|------------|
| **Code Segment** | Program code | Static |
| **Data Segment** | Global data | Static |
| **Stack** | Local variables, functions | Automatic |
| **Heap** | Dynamic objects, arrays | Manual (programmer) |

### Stack vs Heap

| Aspect | Stack | Heap |
|---------|-------|------|
| **Memory** | Fixed size, automatic | Dynamic, manual |
| **Management** | System | Programmer |
| **Allocation** | Automatic | `new` operator |
| **Deallocation** | Automatic | `delete` operator |
| **Speed** | Fast | Slower |
| **Lifetime** | Scope-based | Until explicitly deleted |

### new Operator

| Operation | Syntax | Returns |
|-----------|--------|---------|
| **Single Variable** | `int *ptr = new int;` | Pointer to allocated memory |
| **Array** | `int *arr = new int[10];` | Pointer to first element |

### delete Operator

| Operation | Syntax | Purpose |
|-----------|--------|---------|
| **Single Variable** | `delete ptr;` | Free single variable |
| **Array** | `delete[] arr;` | Free array |

### Dynamic vs Static Variables

| Characteristic | Static | Dynamic |
|----------------|--------|---------|
| **Memory** | Stack | Heap |
| **Management** | Automatic | Manual |
| **Size** | Fixed at compile time | Determined at runtime |
| **Lifetime** | Scope-based | Until deleted |
| **Efficiency** | Faster | Slower (but more flexible) |

### Common Pointer Errors

| Error | Description | Solution |
|-------|-------------|----------|
| **Dangling Pointer** | Pointer to deallocated memory | Set to `NULL` after delete |
| **Memory Leak** | Allocated memory not freed | Always use `delete` |
| **Uninitialized Pointer** | Pointer not initialized | Always initialize |

### Memory Leak Example

```cpp
int *p = new int;  // Allocate memory
*p = 5;
p = new int;       // Memory leak! Previous allocation lost
*p = 6;
delete p;          // Only frees second allocation
```

### Key Terms

| Term | Definition |
|------|------------|
| **Pointer** | Variable storing memory address |
| **Dereferencing** | Accessing value through pointer |
| **Indirection** | Referencing value indirectly |
| **Dynamic Allocation** | Runtime memory allocation |
| **Memory Leak** | Unfreed allocated memory |
| **Dangling Pointer** | Pointer to freed memory |

---

## Module 6: Linked List Part 1

### Course Information

| Aspect | Details |
|--------|---------|
| **Course Code** | CT077-3-2-DSTR |
| **Course Title** | Data Structures |
| **Chapter** | Chapter 6 - Linked Lists (Part 1) |

### Learning Outcomes

At the end of this topic, you should be able to:
1. Explain the basic properties of a linked list and its advantages
2. Implement some of the basic operations on linked lists

### Linked List vs Array

| Feature | Array | Linked List |
|---------|-------|-------------|
| **Memory** | Contiguous | Scattered |
| **Size** | Fixed | Dynamic |
| **Access** | Random (O(1)) | Sequential (O(n)) |
| **Insertion** | O(n) | O(1) at beginning |
| **Deletion** | O(n) | O(1) at beginning |
| **Memory Efficiency** | Better | Wastes space for pointers |

### Linked List Structure

| Component | Description |
|-----------|-------------|
| **Node** | Element containing data and link |
| **Data/Info** | Stores relevant information |
| **Link** | Stores address of next node |
| **Head** | Pointer to first node |
| **NULL** | End of list marker |

### Node Structure

```cpp
struct NodeType {
    int info;
    NodeType *link;
};
```

| Field | Type | Purpose |
|-------|------|---------|
| `info` | Various | Stores data |
| `link` | Pointer | Points to next node |

### LinkedList Class

```cpp
class LinkedList {
public:
    NodeType *head;
    int size;
    LinkedList();
    int getSize();
    // Other methods...
};
```

### Traversing a Linked List

```cpp
NodeType *current = head;
while (current != NULL) {
    // Process current->info
    current = current->link;
}
```

### Basic Linked List Operations

| Operation | Description | Complexity |
|-----------|-------------|------------|
| **getSize()** | Count elements | O(n) or O(1) with size field |
| **insertAtBeginning()** | Add element at start | O(1) |
| **insertAtEnd()** | Add element at end | O(n) or O(1) with tail pointer |
| **deleteFirst()** | Remove first element | O(1) |
| **deleteLast()** | Remove last element | O(n) |
| **print()** | Display all elements | O(n) |

### insertAtBeginning()

```cpp
void insertAtBeginning(int value) {
    NodeType *newNode = new NodeType;
    newNode->info = value;
    newNode->link = head;
    head = newNode;
    size++;
}
```

### insertAtEnd()

```cpp
void insertAtEnd(int value) {
    NodeType *newNode = new NodeType;
    newNode->info = value;
    newNode->link = NULL;
    
    if (head == NULL) {
        head = newNode;
    } else {
        NodeType *last = head;
        while (last->link != NULL) {
            last = last->link;
        }
        last->link = newNode;
    }
    size++;
}
```

### Why New Node in Heap?

| Stack Allocation | Problem |
|-----------------|---------|
| Node created in stack | Deleted when function ends |
| Head becomes dangling pointer | Points to freed memory |

### clear()

```cpp
void clear() {
    NodeType *current = head;
    while (head != NULL) {
        current = current->link;
        delete head;
        head = current;
    }
    size = 0;
}
```

### Destructor

```cpp
~LinkedList() {
    cout << "Going to delete all " << size << " elements." << endl;
    NodeType *current = head;
    while (head != NULL) {
        current = current->link;
        delete head;
        head = current;
    }
}
```

### Memory Management

| Operation | Memory Action |
|-----------|---------------|
| **Insert** | Allocate new node with `new` |
| **Delete** | Free node with `delete` |
| **Clear** | Delete all nodes |
| **Destructor** | Automatic cleanup |

### Key Terms

| Term | Definition |
|------|------------|
| **Node** | Data + Link structure |
| **Head** | Pointer to first node |
| **Link** | Pointer to next node |
| **NULL** | End of list marker |
| **Traversal** | Visiting all nodes sequentially |

---

## Module 7: Linked List Part 2

### Course Information

| Aspect | Details |
|--------|---------|
| **Course Code** | CT077-3-2-DSTR |
| **Course Title** | Data Structures |
| **Chapter** | Chapter 7 - Linked Lists (Part 2) |

### Learning Outcomes

At the end of this topic, you should be able to:
1. Implement some of the basic operations on linked lists

### Advanced Linked List Operations

| Operation | Description | Complexity |
|-----------|-------------|------------|
| **search()** | Find if element exists | O(n) |
| **getItemAt()** | Get element at index | O(n) |
| **setItemAt()** | Set element at index | O(n) |
| **deleteFirst()** | Remove first element | O(1) |
| **deleteLast()** | Remove last element | O(n) |
| **deleteItemAt()** | Remove at index | O(n) |
| **insertItemAt()** | Insert at index | O(n) |

### search()

```cpp
bool search(int value) {
    NodeType *current = head;
    while (current != NULL) {
        if (current->info == value) {
            return true;
        }
        current = current->link;
    }
    return false;
}
```

### getItemAt()

```cpp
int getItemAt(int index) {
    if (index < 0 || index >= size) {
        cout << "Index out of bound.\n";
        abort();
    }
    NodeType *current = head;
    for (int i = 0; i < index; i++) {
        current = current->link;
    }
    return current->info;
}
```

### setItemAt()

```cpp
void setItemAt(int value, int index) {
    if (index < 0 || index >= size) {
        cout << "Index out of bound.\n";
        abort();
    }
    NodeType *current = head;
    for (int i = 0; i < index; i++) {
        current = current->link;
    }
    current->info = value;
}
```

### deleteFirst()

```cpp
void deleteFirst() {
    if (size > 0) {
        NodeType *toBeDeleted = head;
        head = head->link;
        delete toBeDeleted;
        size--;
    }
}
```

### deleteLast()

```cpp
void deleteLast() {
    if (size > 0) {
        if (size == 1) {
            delete head;
            head = NULL;
        } else {
            NodeType *beforeLast = head;
            while (beforeLast->link->link != NULL) {
                beforeLast = beforeLast->link;
            }
            delete beforeLast->link;
            beforeLast->link = NULL;
        }
        size--;
    }
}
```

### deleteItemAt()

```cpp
void deleteItemAt(int index) {
    if (index < size) {
        if (index == 0) {
            deleteFirst();
        } else {
            NodeType *prev = NULL, *toDelete = head;
            for (int i = 0; i < index; i++) {
                prev = toDelete;
                toDelete = toDelete->link;
            }
            prev->link = toDelete->link;
            delete toDelete;
            size--;
        }
    }
}
```

### insertItemAt()

```cpp
void insertItemAt(int value, int index) {
    if (index <= size) {
        if (index == 0) {
            insertAtBeginning(value);
        } else if (index == size) {
            insertAtEnd(value);
        } else {
            NodeType *newNode = new NodeType;
            newNode->info = value;
            NodeType *prev = head;
            for (int i = 0; i < index - 1; i++) {
                prev = prev->link;
            }
            newNode->link = prev->link;
            prev->link = newNode;
            size++;
        }
    }
}
```

### Algorithm Complexity Summary

| Operation | Linked List | Array |
|-----------|-------------|-------|
| **Access by Index** | O(n) | O(1) |
| **Search (unsorted)** | O(n) | O(n) |
| **Insert at Beginning** | O(1) | O(n) |
| **Insert at End** | O(1)* or O(n) | O(1)* |
| **Insert at Position** | O(n) | O(n) |
| **Delete at Beginning** | O(1) | O(n) |
| **Delete at End** | O(n) | O(1)* |
| **Delete at Position** | O(n) | O(n) |

*With tail pointer

### Key Terms

| Term | Definition |
|------|------------|
| **Search** | Find element in list |
| **Access** | Get element by position |
| **Delete** | Remove element from list |

---

## Module 8: Linked List Part 3

### Course Information

| Aspect | Details |
|--------|---------|
| **Course Code** | CT077-3-2-DSTR |
| **Course Title** | Data Structures |
| **Chapter** | Chapter 8 - Linked Lists (Part 3) |

### Learning Outcomes

At the end of this topic, you should be able to:
1. Improve implementation of some operations on linked lists
2. Implement reversed traversal using loops and recursion
3. Understand the concept of Doubly Linked Lists
4. Understand the concept of Circular Linked Lists

### Linked List Types

| Type | Description | Advantages |
|------|-------------|------------|
| **Singly Linked** | One-way links | Simple, efficient |
| **Doubly Linked** | Two-way links | Bidirectional traversal |
| **Circular Linked** | Last points to first | Circular operations |
| **Circular Doubly** | Combination of both | Most flexible |

### Tail Pointer Improvement

| Operation | Without Tail | With Tail |
|-----------|--------------|-----------|
| **insertAtEnd()** | O(n) | O(1) |
| **deleteLast()** | O(n) | O(n) |
| **Memory** | Less | Slightly more |

### Updated Constructor with Tail

```cpp
LinkedList() {
    this->size = 0;
    this->head = NULL;
    this->tail = NULL;
}
```

### Updated insertAtBeginning()

```cpp
void insertAtBeginning(int value) {
    NodeType *newNode = new NodeType;
    newNode->info = value;
    newNode->link = head;
    head = newNode;
    size++;
    if (tail == NULL) {
        tail = newNode;
    }
}
```

### Reverse Traversal (Inefficient)

```cpp
void printReverse() {
    for (int limit = size - 1; limit >= 0; limit--) {
        NodeType *current = head;
        for (int i = 0; i < limit; i++) {
            current = current->link;
        }
        cout << current->info << " ";
    }
}
```

### Reverse Traversal (Recursive)

```cpp
void printReverse() {
    printRecursive(head);
}

void printRecursive(NodeType *current) {
    if (current != NULL) {
        printRecursive(current->link);  // Print remaining first
        cout << current->info << " ";  // Then print current
    }
}
```

### Doubly Linked List

| Feature | Description |
|---------|-------------|
| **Node Structure** | Data + next pointer + previous pointer |
| **Traversal** | Can go forward and backward |
| **Efficiency** | Faster for certain operations |
| **Memory** | Uses more memory per node |

### Doubly Linked List Node

```cpp
template <class T>
class DoublyNodeType {
public:
    T info;
    DoublyNodeType<T> *next;
    DoublyNodeType<T> *prev;
};
```

### Doubly Linked List Class

```cpp
template <class T>
class DoublyLinkedList {
public:
    DoublyNodeType<T> *head;
    DoublyNodeType<T> *tail;
    int size;
};
```

### Doubly Linked List: insertAtEnd()

```cpp
void insertAtEnd(T value) {
    DoublyNodeType<T> *newNode = new DoublyNodeType<T>;
    newNode->info = value;
    newNode->next = NULL;
    newNode->prev = tail;
    tail = newNode;
    
    if (head == NULL) {
        head = newNode;
    } else {
        newNode->prev->next = newNode;
    }
    size++;
}
```

### Circular Linked List

| Feature | Description |
|---------|-------------|
| **Structure** | Last node points to first |
| **Traversal** | Natural circular iteration |
| **Applications** | Round-robin, games, playlists |
| **Implementation** | Similar to regular, with NULL check changes |

### Circular Linked List Node

```cpp
template <class T>
class CircularLinkedList {
public:
    NodeType<T> *head;
    NodeType<T> *tail;
    int size;
};
```

### Circular Linked List: insertAtBeginning()

```cpp
void insertAtBeginning(T value) {
    NodeType<T> *newNode = new NodeType<T>;
    newNode->info = value;
    
    if (tail == NULL) {
        tail = newNode;
        tail->link = tail;  // Points to itself
    } else {
        newNode->link = tail->link;
        tail->link = newNode;
    }
    size++;
}
```

### Circular Doubly Linked List

```cpp
template <class T>
class CircularDoublyLinkedList {
public:
    DoublyNodeType<T> *tail;  // Only need tail
    int size;
};
```

### Choosing: Array vs Linked List

| Situation | Recommendation | Reason |
|-----------|----------------|--------|
| **Known number of elements** | Array | Fixed size efficient |
| **Dynamic addition/expansion** | Linked List | No size limit |
| **Deletion at any position** | Linked List | Efficient insertion/deletion |
| **Lots of random access** | Array | O(1) access |
| **Searching unsorted** | Both | Same O(n) complexity |
| **Searching sorted** | Array | Binary search O(log n) |

### Key Terms

| Term | Definition |
|------|------------|
| **Tail Pointer** | Pointer to last node |
| **Reverse Traversal** | Visit nodes from end to beginning |
| **Doubly Linked List** | Two-way linked list |
| **Circular Linked List** | Last node points to first |

---

## Module 9: Stacks

### Course Information

| Aspect | Details |
|--------|---------|
| **Course Code** | CT077-3-2-DSTR |
| **Course Title** | Data Structures |
| **Chapter** | Chapter 9 - Stacks |

### Learning Outcomes

At the end of this topic, you should be able to:
1. Understand the concept of a stack data structure
2. Discover applications where stacks are useful
3. Examine and implement stack operations

### Stack Definition

| Characteristic | Description |
|----------------|-------------|
| **Type** | Linear structure |
| **Access** | Only one end (top) |
| **Operations** | LIFO (Last In First Out) |
| **Elements** | Homogeneous (same type) |

### Stack Operations

| Operation | Description | Effect |
|-----------|-------------|--------|
| **push()** | Add element to top | Increases size |
| **pop()** | Remove from top | Decreases size, returns element |
| **top() / peek()** | View top element | No removal |
| **isEmpty()** | Check if empty | Returns boolean |

### Stack Analogy

| Real-world Example | Stack Behavior |
|-------------------|---------------|
| **Stack of plates** | Remove from top only |
| **Stack of books** | Add on top only |
| **Coin pile** | Last coin added, first removed |

### Stack Applications

| Application | Description |
|-------------|-------------|
| **Function calls** | Call stack for return addresses |
| **Expression evaluation** | Infix to postfix conversion |
| **Parentheses matching** | Check balanced parentheses |
| **Undo/Redo** | Track operations |
| **Back/Forward buttons** | Browser navigation |

### Stack Implementation: Array

```cpp
class Stack {
    char *list;
    int stackTop;
    int maxStackSize;
public:
    Stack(int maxSize);
    ~Stack();
    void push(char elem);
    char pop();
    char top();
    bool isEmpty();
};
```

### Stack Implementation: Linked List

```cpp
class Stack {
    NodeType *head;  // Top of stack
public:
    Stack();
    ~Stack();
    void push(char elem);
    char pop();
    char top();
    bool isEmpty();
};
```

### Array Stack: Constructor

```cpp
Stack::Stack(int maxSize) {
    list = new char[maxSize];
    maxStackSize = maxSize;
    stackTop = -1;  // Empty stack
}
```

### Array Stack: push()

```cpp
void push(char elem) {
    if (stackTop < maxStackSize) {
        list[++stackTop] = elem;
    }
    // else: error or expand
}
```

### Array Stack: pop()

```cpp
char pop() {
    if (stackTop >= 0) {
        return list[stackTop--];
    }
    // else: error
}
```

### Linked List Stack: push()

```cpp
void push(char elem) {
    NodeType *newNode = new NodeType;
    newNode->info = elem;
    newNode->link = head;
    head = newNode;
}
```

### Linked List Stack: pop()

```cpp
char pop() {
    if (head != NULL) {
        NodeType *temp = head;
        char elem = temp->info;
        head = head->link;
        delete temp;
        return elem;
    }
    // else: error
}
```

### Application: Parentheses Matching

| Algorithm | Steps |
|-----------|-------|
| 1 | Scan expression left to right |
| 2 | Push position when '(' encountered |
| 3 | Pop and print pair when ')' encountered |
| 4 | Error if ')' and stack empty |
| 5 | Error if expression ends and stack not empty |

### Parentheses Matching Example

| Expression | Output |
|------------|--------|
| `((a+b)*c+d-e)/(f+g)-(h+j)*(k-l))/(m-n)` | (2,6), (1,13), (15,19), (21,25), (27,31), (0,32), (34,38) |
| `(a+b))*((c+d)` | Error: right parenthesis at 5 has no match |
| `((c+d)` | Error: left parenthesis at 7 has no match |

### Application: Infix to Postfix Conversion

| Algorithm | Steps |
|-----------|-------|
| 1 | Scan infix expression left to right |
| 2 | If operand, output it |
| 3 | If operator, compare precedence with stack top |
| 4 | Push if higher precedence, pop if lower or equal |
| 5 | If '(', push to stack |
| 6 | If ')', pop until '(' encountered |
| 7 | Pop remaining operators at end |

### Operator Precedence

| Operator | Precedence |
|----------|------------|
| `^` | Highest |
| `*`, `/` | High |
| `+`, `-` | Low |
| `(` | Special |

### Infix to Postfix Example

| Expression | Stack | Output |
|------------|-------|--------|
| `A` | - | A |
| `A+` | + | A |
| `A+B` | + | AB |
| `A+B*` | +* | AB |
| `A+B*C` | +* | ABC |
| `A+B*C-` | - | ABC*+ |
| `A+B*C-D` | - | ABC*+D |
| `A+B*C-D/` | -/ | ABC*+D |
| `A+B*C-D/E` | -/ | ABC*+DE |
| **End** | - | ABC*+DE/- |

### Postfix Result: `ABC*+DE/-`

### Key Terms

| Term | Definition |
|------|------------|
| **LIFO** | Last In First Out |
| **push()** | Add to top |
| **pop()** | Remove from top |
| **top/peek()** | View top element |

---

## Module 10: Queues

### Course Information

| Aspect | Details |
|--------|---------|
| **Course Code** | CT077-3-2-DSTR |
| **Course Title** | Data Structures |
| **Chapter** | Chapter 10 - Queues |

### Learning Outcomes

At the end of this topic, you should be able to:
1. Understand the concept of a queue data structure
2. Discover applications where queues are useful
3. Examine and implement queue operations
4. Explore how to build a circular queue using Array

### Queue Definition

| Characteristic | Description |
|----------------|-------------|
| **Type** | Linear structure |
| **Access** | Two ends (front and rear) |
| **Operations** | FIFO (First In First Out) |
| **Elements** | Homogeneous (same type) |

### Queue vs Stack

| Feature | Queue | Stack |
|---------|-------|-------|
| **Access** | Two ends | One end |
| **Order** | FIFO | LIFO |
| **Insert** | At rear | At top |
| **Delete** | From front | From top |

### Queue Operations

| Operation | Description | Effect |
|-----------|-------------|--------|
| **enqueue()** | Add element to rear | Increases size |
| **dequeue()** | Remove from front | Decreases size, returns element |
| **front()** | View front element | No removal |
| **rear()** | View rear element | No removal |
| **isEmpty()** | Check if empty | Returns boolean |

### Queue Applications

| Application | Description |
|-------------|-------------|
| **Waiting lines** | Bank, library, printer queue |
| **Operating systems** | Process scheduling |
| **Network** | Server request handling |
| **Priority queues** | Hospital triage, airline boarding |

### Queue Implementation: Array

```cpp
class Queue {
    char *list;
    int maxQueueSize;
    int queueFront;
    int queueRear;
public:
    Queue(int maxSize);
    ~Queue();
    void addQueue(char elem);
    char deleteQueue();
    bool isEmpty();
};
```

### Array Queue: Initialization

```cpp
queueRear = -1;
queueFront = 0;
```

### Array Queue: enqueue()

```cpp
void addQueue(char elem) {
    queueRear++;
    list[queueRear] = elem;
}
```

### Array Queue: dequeue()

```cpp
char deleteQueue() {
    char elem = list[queueFront];
    queueFront++;
    return elem;
}
```

### Array Queue Problem

| Issue | Description |
|-------|-------------|
| **Overflow** | Rear reaches end, but front has free space |
| **Solution 1** | Shift all elements (slow) |
| **Solution 2** | Circular queue |

### Circular Queue

| Concept | Description |
|---------|-------------|
| **Structure** | Array treated as circular |
| **Index Update** | `(index + 1) % maxQueueSize` |
| **Advantage** | Efficient space utilization |

### Circular Queue: enqueue()

```cpp
queueRear = (queueRear + 1) % maxQueueSize;
list[queueRear] = elem;
```

### Circular Queue: dequeue()

```cpp
elem = list[queueFront];
queueFront = (queueFront + 1) % maxQueueSize;
```

### Empty vs Full Problem

| Condition | queueFront == queueRear | lastOpAddQ |
|-----------|------------------------|-------------|
| **Empty** | True | False |
| **Full** | True | True |

### Solution 1: lastOpAddQ Flag

```cpp
bool lastOpAddQ;

// In addQueue:
lastOpAddQ = true;

// In deleteQueue:
lastOpAddQ = false;

// isEmpty:
return (queueRear == queueFront - 1) && !lastOpAddQ;

// isFull:
return (queueRear == queueFront - 1) && lastOpAddQ;
```

### Solution 2: count Variable

```cpp
int count;

// In addQueue:
count++;

// In deleteQueue:
count--;

// isEmpty:
return count == 0;

// isFull:
return count == maxQueueSize;
```

### Queue Implementation: Linked List

```cpp
class Queue {
    NodeType *queueFront;
    NodeType *queueRear;
    int count;
public:
    Queue();
    ~Queue();
    void addQueue(char elem);
    char deleteQueue();
    bool isEmpty();
};
```

### Linked List Queue: enqueue()

```cpp
void addQueue(char elem) {
    NodeType *newNode = new NodeType;
    newNode->info = elem;
    newNode->link = NULL;
    
    if (queueFront == NULL) {
        queueFront = queueRear = newNode;
    } else {
        queueRear->link = newNode;
        queueRear = newNode;
    }
    count++;
}
```

### Linked List Queue: dequeue()

```cpp
char deleteQueue() {
    if (queueFront != NULL) {
        NodeType *temp = queueFront;
        char elem = temp->info;
        queueFront = queueFront->link;
        if (queueFront == NULL) {
            queueRear = NULL;
        }
        delete temp;
        count--;
        return elem;
    }
}
```

### Queue vs Array Implementation

| Aspect | Array | Linked List |
|--------|-------|-------------|
| **Size** | Fixed | Dynamic |
| **Efficiency** | O(1) with circular | O(1) |
| **Memory** | Pre-allocated | Per node |
| **Overflow** | Possible | No (theoretically) |

### Key Terms

| Term | Definition |
|------|------------|
| **FIFO** | First In First Out |
| **enqueue()** | Add to rear |
| **dequeue()** | Remove from front |
| **Circular Queue** | Array with wrap-around |

---

## Module 11: Trees and Binary Trees

### Course Information

| Aspect | Details |
|--------|---------|
| **Course Code** | CT077-3-2-DSTR |
| **Course Title** | Data Structures |
| **Chapter** | Chapter 11 - Trees |

### Learning Outcomes

At the end of this topic, you should be able to:
1. Understand concepts and terminologies related to trees
2. Discover applications where trees are useful
3. Examine Binary Trees structure representation
4. Apply and implement Binary Trees traversal algorithms

### Tree Definition

| Characteristic | Description |
|----------------|-------------|
| **Structure** | Non-linear, hierarchical |
| **Components** | Nodes connected by edges |
| **Relationship** | Parent-child relationships |
| **Top** | Single root node |
| **Bottom** | Leaf nodes |

### Tree Terminology

| Term | Definition |
|------|------------|
| **Node** | Basic unit of tree |
| **Root** | Top node, no parent |
| **Edge** | Connection between nodes |
| **Parent** | Node with children |
| **Child** | Node with parent |
| **Sibling** | Nodes with same parent |
| **Leaf** | Node with no children |
| **Ancestor** | Parent, grandparent, etc. |
| **Descendant** | Child, grandchild, etc. |
| **Level** | Distance from root (starts at 0 or 1) |
| **Height** | Longest path from root to leaf |
| **Depth** | Distance from root to node |
| **Degree** | Number of children |
| **Path** | Sequence of nodes |
| **Subtree** | Tree rooted at child node |

### Tree vs List

| Feature | List | Tree |
|---------|------|------|
| **Structure** | Linear | Hierarchical |
| **Relationships** | Serial | Ancestor-descendant |
| **Applications** | Ordered data | Organized data |

### Tree Applications

| Application | Example |
|-------------|---------|
| **Family Trees** | Parent-child relationships |
| **Organization Charts** | Management hierarchy |
| **File Systems** | Directory structure |
| **HTML DOM** | Document structure |
| **Decision Trees** | Classification |
| **Game Trees** | Move sequences |

### Binary Tree

| Characteristic | Description |
|----------------|-------------|
| **Maximum Children** | 2 (left and right) |
| **Subtrees** | Left subtree (L_T) and Right subtree (R_T) |
| **Recursive** | Subtrees are binary trees themselves |
| **Empty Tree** | Possible (NULL) |

### Binary Tree Cases

| Case | Description |
|------|-------------|
| **Empty Tree** | No nodes |
| **Single Node** | Root only |
| **Two Nodes** | Root with one child |
| **Full** | Every node has 0 or 2 children |
| **Complete** | All levels filled except possibly last, left-filled |

### Binary Tree Properties

| Property | Formula | Description |
|----------|---------|-------------|
| **Min Nodes (height h)** | h + 1 | Tree with minimum nodes |
| **Max Nodes (height h)** | 2^(h+1) - 1 | Full binary tree |
| **Min Height (n nodes)** | ⌈log₂(n+1)⌉ - 1 | Minimum height for n nodes |
| **Max Height (n nodes)** | n - 1 | Right/left skewed tree |

### Full Binary Tree

| Characteristic | Value |
|----------------|-------|
| **Definition** | Every node has 0 or 2 children |
| **Nodes (height h)** | Exactly 2^(h+1) - 1 |
| **Numbering** | 1 to 2^h - 1 |
| **Order** | Level by level, left to right |

### Binary Tree Representation

| Method | Description | Efficiency |
|--------|-------------|------------|
| **Array** | Store in array | O(1) access, may waste space |
| **Linked** | Pointers to children | Flexible, uses more memory |

### Array Representation

| Index | Left Child | Right Child | Parent |
|-------|------------|-------------|--------|
| i | 2i + 1 | 2i + 2 | ⌊(i-1)/2⌋ |

### Linked Representation

```cpp
struct TreeNode {
    char data;
    TreeNode *left;
    TreeNode *right;
};

class BinaryTree {
public:
    TreeNode *root;
    // Operations...
};
```

### Binary Tree Operations

| Operation | Description | Complexity |
|-----------|-------------|------------|
| **isEmpty()** | Check if empty | O(1) |
| **height()** | Calculate height | O(n) |
| **nodeCount()** | Count nodes | O(n) |
| **insert()** | Insert node | O(n) |
| **delete()** | Delete node | O(n) |
| **search()** | Find node | O(n) |

### Binary Tree Traversals

| Traversal | Order | Visit Order |
|-----------|-------|------------|
| **Pre-order** | MLR | Node → Left → Right |
| **In-order** | LMR | Left → Node → Right |
| **Post-order** | LRM | Left → Right → Node |
| **Level-order** | BFS | Level by level |

### Pre-order Traversal

```cpp
void preOrder() {
    preOrder(root);
}

void preOrder(TreeNode *node) {
    if (node != NULL) {
        cout << node->data << " ";
        preOrder(node->left);
        preOrder(node->right);
    }
}
```

### In-order Traversal

```cpp
void inOrder(TreeNode *node) {
    if (node != NULL) {
        inOrder(node->left);
        cout << node->data << " ";
        inOrder(node->right);
    }
}
```

### Post-order Traversal

```cpp
void postOrder(TreeNode *node) {
    if (node != NULL) {
        postOrder(node->left);
        postOrder(node->right);
        cout << node->data << " ";
    }
}
```

### Level-order Traversal

```cpp
void levelOrder() {
    Queue<TreeNode*> q;
    q.addQueue(root);
    
    while (!q.isEmpty()) {
        TreeNode *node = q.deleteQueue();
        cout << node->data << " ";
        
        if (node->left != NULL)
            q.addQueue(node->left);
        if (node->right != NULL)
            q.addQueue(node->right);
    }
}
```

### Traversal Example

```
        A
       / \
      B   C
     / \   \
    D   E   G
```

| Traversal | Result |
|-----------|--------|
| **Pre-order** | A B D E C G |
| **In-order** | D B E A C G |
| **Post-order** | D E B G C A |
| **Level-order** | A B C D E G |

### Key Terms

| Term | Definition |
|------|------------|
| **Root** | Top node |
| **Leaf** | Node with no children |
| **Degree** | Number of children |
| **Full Tree** | Every node has 0 or 2 children |
| **Complete Tree** | All levels filled except last (left-filled) |
| **Pre-order** | Node-Left-Right |
| **In-order** | Left-Node-Right |
| **Post-order** | Left-Right-Node |
| **Level-order** | Breadth-first |

---

## Module 12: Binary Search Trees

### Course Information

| Aspect | Details |
|--------|---------|
| **Course Code** | CT077-3-2-DSTR |
| **Course Title** | Data Structures |
| **Chapter** | Chapter 12 - Binary Search Trees |

### Learning Outcomes

At the end of this topic, you should be able to:
1. Understand the concepts of Binary Search Trees
2. Discover how to organize data in a BST
3. Apply and implement search and delete operations

### Binary Search Tree (BST)

| Property | Description |
|----------|-------------|
| **Left Subtree** | Contains only nodes with keys < node's key |
| **Right Subtree** | Contains only nodes with keys > node's key |
| **No Duplicates** | No duplicate keys allowed |
| **Efficiency** | O(log n) for balanced tree |

### BST vs Regular Binary Tree

| Feature | Binary Tree | BST |
|---------|-------------|-----|
| **Order** | No specific order | Ordered property |
| **Search** | O(n) | O(log n) average |
| **Insertion** | No restriction | Must maintain order |
| **Use Cases** | General hierarchy | Search operations |

### BST Insertion

| Step | Description |
|------|-------------|
| 1 | Search for key in tree |
| 2 | If found, do nothing (no duplicates) |
| 3 | If not found, insert as leaf at end of search path |
| 4 | Link to parent as left or right child |

### BST Insertion Example

```
Insert: 5, 3, 7, 2, 4, 6, 8

        5
       / \
      3   7
     / \ / \
    2  4 6  8
```

### BST Insertion Algorithm

```cpp
void insert(int key) {
    TreeNode *newNode = new TreeNode;
    newNode->data = key;
    newNode->left = NULL;
    newNode->right = NULL;
    
    if (root == NULL) {
        root = newNode;
    } else {
        TreeNode *parent = NULL, *node = root;
        while (node != NULL) {
            parent = node;
            if (node->data == key) {
                cout << "Duplicates not allowed." << endl;
                return;
            } else if (key < node->data) {
                node = node->left;
            } else {
                node = node->right;
            }
        }
        if (key < parent->data) {
            parent->left = newNode;
        } else {
            parent->right = newNode;
        }
    }
}
```

### BST Search

| Step | Description |
|------|-------------|
| 1 | Start at root |
| 2 | If key matches, return node |
| 3 | If key < node, search left subtree |
| 4 | If key > node, search right subtree |
| 5 | If NULL, key not found |

### BST Search Algorithm

```cpp
TreeNode* find(int key) {
    return find(key, root);
}

TreeNode* find(int key, TreeNode *node) {
    if (node == NULL) {
        return NULL;
    } else {
        if (key == node->data) {
            return node;
        } else if (key < node->data) {
            return find(key, node->left);
        } else {
            return find(key, node->right);
        }
    }
}
```

### Finding Min and Max

| Operation | Description | Complexity |
|-----------|-------------|------------|
| **Min** | Leftmost node | O(log n) average |
| **Max** | Rightmost node | O(log n) average |

### BST Deletion Cases

| Case | Description | Complexity |
|------|-------------|------------|
| **1: Leaf** | Delete node, set parent link to NULL | O(log n) |
| **2: No left subtree** | Replace with right child | O(log n) |
| **3: No right subtree** | Replace with left child | O(log n) |
| **4: Both subtrees** | Replace with max of left or min of right | O(log n) |

### BST Deletion Algorithm

```cpp
void delete(int key) {
    TreeNode *parent = NULL, *node = root;
    
    while (node != NULL) {
        parent = node;
        if (node->data == key) {
            // Handle 4 cases
            // Update root if necessary
        } else if (key < node->data) {
            node = node->left;
        } else {
            node = node->right;
        }
    }
    cout << "Key was not found, cannot delete!" << endl;
}
```

### BST vs Array

| Feature | BST | Array |
|---------|-----|-------|
| **Search** | O(log n) average | O(n) linear, O(log n) binary if sorted |
| **Insertion** | O(log n) average | O(n) (shift elements) |
| **Deletion** | O(log n) average | O(n) (shift elements) |
| **Size** | Dynamic | Fixed (or costly to resize) |
| **Memory** | Pointers overhead | Compact |

### BST Shape

| Shape | Efficiency | Height |
|-------|------------|-------|
| **Balanced** | O(log n) | ⌈log₂(n+1)⌉ - 1 |
| **Skewed** | O(n) | n |
| **Random** | O(log n) average | ≈ 1.39 log₂ n |

### AVL Trees

| Feature | Description |
|---------|-------------|
| **Self-balancing** | Maintains balance property |
| **Rotations** | Used to rebalance |
| **Height Balanced** | Left and right subtrees differ by at most 1 |
| **Efficiency** | Guarantees O(log n) operations |

### Key Terms

| Term | Definition |
|------|------------|
| **BST** | Binary Search Tree |
| **Ordered Property** | Left < Node < Right |
| **Search** | Find node by key |
| **Insertion** | Add maintaining order |
| **Deletion** | Remove maintaining order |
| **Balanced Tree** | Near-equal subtrees |
| **AVL Tree** | Self-balancing BST |

---

## Module 13: Graphs

### Course Information

| Aspect | Details |
|--------|---------|
| **Course Code** | CT077-3-2-DSTR |
| **Course Title** | Data Structures |
| **Chapter** | Chapter 13 - Graphs |

### Learning Outcomes

At the end of this topic, you should be able to:
1. Explore different applications utilizing graphs
2. Understand concepts and terminologies related to graphs
3. Examine how to represent graphs in memory

### Graph Definition

| Characteristic | Description |
|----------------|-------------|
| **Structure** | Set of vertices and edges |
| **Notation** | G = (V, E) |
| **V** | Set of vertices |
| **E** | Set of edges (E ⊆ V × V) |
| **Vertices** | Also called nodes |
| **Edges** | Also called links or arcs |

### Graph Types

| Type | Description | Edges |
|------|-------------|-------|
| **Undirected** | Edges have no direction | (u, v) = (v, u) |
| **Directed (Digraph)** | Edges have direction | (u, v) ≠ (v, u) |
| **Weighted** | Edges have values | Weight attached to edge |
| **Unweighted** | Edges have no values | Just connections |

### Graph Terminology

| Term | Definition |
|------|------------|
| **Adjacent** | Connected by edge |
| **Path** | Sequence of vertices connected by edges |
| **Simple Path** | All vertices distinct (except possibly first/last) |
| **Cycle** | Simple path where first = last |
| **Connected** | Path exists between any two vertices |
| **Strongly Connected** | Digraph where every pair reachable in both directions |
| **Weakly Connected** | Digraph becomes connected when edges made undirected |
| **Complete** | Every vertex connected to every other |
| **Degree-in** | Number of edges entering a vertex |
| **Degree-out** | Number of edges leaving a vertex |
| **Loop** | Edge from vertex to itself |

### Graph Applications

| Application | Description |
|-------------|-------------|
| **Social Networks** | Friend connections |
| **Maps** | Cities and roads |
| **Computer Networks** | Devices and connections |
| **Course Prerequisites** | Dependencies |
| **Project Planning** | Task dependencies |
| **Web** | Pages and hyperlinks |

### Graph Representations

| Method | Space | Edge Check | Best For |
|--------|-------|------------|----------|
| **Adjacency Matrix** | O(|V|²) | O(1) | Dense graphs |
| **Adjacency List** | O(|V| + |E|) | O(degree) | Sparse graphs |

### Adjacency Matrix

| Characteristic | Description |
|----------------|-------------|
| **Size** | |V| × |V| matrix |
| **Value A[i][j]** | 1 if edge exists, 0 otherwise (unweighted) |
| **Value A[i][j]** | Weight of edge (weighted) |
| **Symmetric** | A[i][j] = A[j][i] for undirected graphs |
| **Diagonal** | 0 for simple graphs (no loops) |

### Adjacency Matrix Example

```
     0  1  2  3
  0 [0, 1, 1, 0]
  1 [1, 0, 1, 1]
  2 [1, 1, 0, 1]
  3 [0, 1, 1, 0]
```

### Adjacency List

| Characteristic | Description |
|----------------|-------------|
| **Structure** | Array of linked lists |
| **Each Vertex** | Has list of adjacent vertices |
| **Space** | O(|V| + |E|) |
| **Efficiency** | Better for sparse graphs |

### Adjacency List Example

```
Vertex 0: 1, 2
Vertex 1: 0, 2, 3
Vertex 2: 0, 1, 3
Vertex 3: 1, 2
```

### Matrix vs List Comparison

| Feature | Adjacency Matrix | Adjacency List |
|---------|-----------------|----------------|
| **Space** | |V|² | |V| + |E| |
| **Edge Check** | O(1) | O(degree) |
| **Add Vertex** | O(|V|²) | O(1) |
| **Add Edge** | O(1) | O(1) |
| **Remove Edge** | O(1) | O(|E|) |
| **Best For** | Dense graphs | Sparse graphs |

### Degree Calculations

| Vertex | d⁺(v) | d⁻(v) |
|--------|--------|--------|
| **Out-degree** | Number of outgoing edges | - |
| **In-degree** | - | Number of incoming edges |

### Example: Degree Calculations

```
V = {1, 2, 3, 4, 5}
E = {(1,2), (1,3), (2,3), (2,5), (3,4), (3,5), (4,2), (4,5)}
```

| Vertex | d⁺(v) | d⁻(v) |
|--------|--------|--------|
| 1 | 2 | 0 |
| 2 | 2 | 2 |
| 3 | 2 | 2 |
| 4 | 2 | 1 |
| 5 | 0 | 3 |

### Graph Operations

| Operation | Description |
|-----------|-------------|
| **Create Graph** | Initialize structure |
| **Add Vertex** | Add new node |
| **Add Edge** | Connect two vertices |
| **Remove Edge** | Disconnect vertices |
| **Check Edge** | Verify connection exists |
| **Get Neighbors** | Find adjacent vertices |
| **Print Graph** | Display graph data |

### Key Terms

| Term | Definition |
|------|------------|
| **Vertex/Node** | Basic unit |
| **Edge/Arc** | Connection |
| **Undirected** | Two-way connections |
| **Directed** | One-way connections |
| **Weighted** | Edges have values |
| **Adjacency Matrix** | 2D representation |
| **Adjacency List** | Linked list representation |
| **Degree** | Number of connections |

---

## Module 14: Graph Algorithms

### Course Information

| Aspect | Details |
|--------|---------|
| **Course Code** | CT077-3-2-DSTR |
| **Course Title** | Data Structures |
| **Chapter** | Chapter 14 - Graph Algorithms |

### Learning Outcomes

At the end of this topic, you should be able to:
1. Examine and apply graph traversal algorithms
2. Examine and apply shortest path algorithms
3. Examine and apply minimal spanning tree algorithms
4. Examine and apply topological sort algorithm in directed acyclic graph

### Graph Traversal Algorithms

| Algorithm | Data Structure | Description |
|-----------|---------------|-------------|
| **Depth First Search (DFS)** | Stack | Explore deep first |
| **Breadth First Search (BFS)** | Queue | Explore level by level |

### Depth First Traversal

| Step | Description |
|------|-------------|
| 1 | Mark node as visited |
| 2 | Visit node |
| 3 | For each unvisited neighbor, recursively traverse |

### DFS Algorithm

```cpp
void depthFirstTraversal() {
    bool visited[MAX_VERTICES] = {false};
    depthFirstTraversal(root, visited);
}

void depthFirstTraversal(int vertex, bool visited[]) {
    visited[vertex] = true;
    cout << vertex << " ";
    
    for (int i = 0; i < MAX_VERTICES; i++) {
        if (adjacencyMatrix[vertex][i] && !visited[i]) {
            depthFirstTraversal(i, visited);
        }
    }
}
```

### DFS Example

```
Graph:
    0
   /|\
  1 2 3
     / \
    4   5

Starting from 0: 0 1 2 4 5 3
```

### Breadth First Traversal

| Step | Description |
|------|-------------|
| 1 | Add root to queue |
| 2 | While queue not empty: |
| 3 | Dequeue and visit node |
| 4 | Add unvisited neighbors to queue |

### BFS Algorithm

```cpp
void breadthFirstTraversal() {
    bool visited[MAX_VERTICES] = {false};
    Queue<int> q;
    
    q.addQueue(0);
    visited[0] = true;
    
    while (!q.isEmpty()) {
        int vertex = q.deleteQueue();
        cout << vertex << " ";
        
        for (int i = 0; i < MAX_VERTICES; i++) {
            if (adjacencyMatrix[vertex][i] && !visited[i]) {
                visited[i] = true;
                q.addQueue(i);
            }
        }
    }
}
```

### BFS Example

```
Graph:
    0
   /|\
  1 2 3
     / \
    4   5

Starting from 0: 0 1 2 3 4 5
```

### DFS vs BFS

| Feature | DFS | BFS |
|---------|-----|-----|
| **Data Structure** | Stack (or recursion) | Queue |
| **Traversal** | Deep first | Level by level |
| **Memory** | O(h) where h is height | O(w) where w is width |
| **Applications** | Topological sort, path finding | Shortest path (unweighted), connectivity |
| **Completeness** | May get stuck in cycles | Finds shortest path in unweighted |

### Shortest Path Algorithms

| Algorithm | Graph Type | Weights | Complexity |
|-----------|------------|---------|------------|
| **Dijkstra's** | Any (directed/undirected) | Non-negative | O(|V|²) or O(|E| + |V| log |V|) |
| **Bellman-Ford** | Directed acyclic | Can be negative | O(|V| × |E|) |
| **Floyd-Warshall** | Any | Positive/negative | O(|V|³) |

### Dijkstra's Algorithm

| Purpose | Description |
|---------|-------------|
| **Goal** | Find shortest path from source to all vertices |
| **Weights** | Non-negative only |
| **Cycles** | Can handle cycles |
| **Output** | Shortest distance to each vertex |

### Dijkstra's Algorithm Steps

| Step | Description |
|------|-------------|
| 1 | Initialize distance array |
| 2 | Set source distance to 0, others to ∞ |
| 3 | Create visited array |
| 4 | Repeat until all vertices visited: |
| 5 | Find unvisited vertex with minimum distance |
| 6 | Mark as visited |
| 7 | Update distances to neighbors |

### Dijkstra's Example

```
Graph with weights:
    0 --3--> 1
    |        |
    6        1
    v        v
    2 --2--> 3

Source: 0

Step 1: distances = [0, ∞, ∞, ∞]
Step 2: Visit 0, update neighbors
       distances = [0, 3, 6, ∞]
Step 3: Visit 1, update neighbors
       distances = [0, 3, 6, 4]
Step 4: Visit 3, update neighbors
       distances = [0, 3, 6, 4]
Step 5: Visit 2
       distances = [0, 3, 6, 4]

Shortest paths from 0:
  to 1: 0 → 1 (3)
  to 2: 0 → 2 (6)
  to 3: 0 → 1 → 3 (4)
```

### Minimal Spanning Tree (MST)

| Characteristic | Description |
|----------------|-------------|
| **Definition** | Spanning tree with minimum total weight |
| **Spanning Tree** | Tree containing all vertices |
| **Weight** | Sum of edge weights |
| **Uniqueness** | May not be unique |

### MST Algorithms

| Algorithm | Approach | Complexity |
|-----------|----------|------------|
| **Prim's** | Grow tree from starting vertex | O(|E| + |V| log |V|) |
| **Kruskal's** | Add edges in increasing order | O(|E| log |E|) |

### Prim's Algorithm

| Step | Description |
|------|-------------|
| 1 | Start with arbitrary vertex |
| 2 | Mark as visited |
| 3 | Repeat until all vertices visited: |
| 4 | Find minimum weight edge connecting visited to unvisited |
| 5 | Add edge to MST |
| 6 | Mark new vertex as visited |

### Kruskal's Algorithm

| Step | Description |
|------|-------------|
| 1 | Sort all edges by weight |
| 2 | Initialize empty forest |
| 3 | For each edge in sorted order: |
| 4 | If adding edge doesn't create cycle: |
| 5 | Add edge to forest |
| 6 | Stop when |V|-1 edges added |

### Kruskal's Example

```
Edges sorted by weight:
  (0, 1): 10
  (2, 4): 12
  (3, 5): 14
  (1, 2): 16
  (3, 4): 22
  (2, 5): 25
  (0, 3): 28

MST edges: (0,1), (2,4), (3,5), (1,2), (3,4)
Total weight: 10 + 12 + 14 + 16 + 22 = 74
```

### Topological Sort

| Characteristic | Description |
|----------------|-------------|
| **Graph Type** | Directed Acyclic Graph (DAG) |
| **Purpose** | Linear ordering of vertices |
| **Property** | For every edge (u, v), u comes before v |
| **Applications** | Task scheduling, dependency resolution |

### Topological Sort Algorithm

| Step | Description |
|------|-------------|
| 1 | Calculate in-degree for all vertices |
| 2 | Add vertices with in-degree 0 to queue |
| 3 | While queue not empty: |
| 4 | Remove vertex, add to result |
| 5 | Decrease in-degree of neighbors |
| 6 | Add neighbors with in-degree 0 to queue |

### Topological Sort Example

```
Graph:
  0 → 1 → 2 → 3
       ↓   ↓
       4 → 5

Ordering: 0, 1, 4, 2, 5, 3
```

### Travelling Salesman Problem (TSP)

| Characteristic | Description |
|----------------|-------------|
| **Problem** | Find shortest route visiting all cities once and returning |
| **Complexity** | NP-hard (computationally difficult) |
| **Solutions** | Heuristics, approximation algorithms |
| **Applications** | Logistics, routing, scheduling |

### Graph Algorithms Summary

| Algorithm | Purpose | Complexity |
|-----------|---------|------------|
| **DFS** | Traversal, path finding | O(|V| + |E|) |
| **BFS** | Shortest path (unweighted) | O(|V| + |E|) |
| **Dijkstra's** | Shortest path (weighted, non-negative) | O(|E| + |V| log |V|) |
| **Prim's** | MST | O(|E| + |V| log |V|) |
| **Kruskal's** | MST | O(|E| log |E|) |
| **Topological Sort** | Linear ordering | O(|V| + |E|) |

### Key Terms

| Term | Definition |
|------|------------|
| **DFS** | Depth First Search |
| **BFS** | Breadth First Search |
| **Dijkstra's** | Shortest path algorithm |
| **MST** | Minimal Spanning Tree |
| **Prim's** | MST algorithm |
| **Kruskal's** | MST algorithm |
| **Topological Sort** | Linear ordering of DAG |
| **TSP** | Travelling Salesman Problem |

---

## Summary

### Course Learning Outcomes Achievement

| Module | Topic | Key Skills |
|--------|-------|------------|
| 1 | Overview | Data structures, algorithms, efficiency |
| 2 | C++ | Programming, control structures, functions |
| 3 | Arrays | 1D/2D arrays, parameter passing |
| 4 | Class/Struct | OOP, constructors, destructors |
| 5 | Pointers | Memory management, dynamic allocation |
| 6-8 | Linked Lists | Singly, doubly, circular lists |
| 9 | Stacks | LIFO operations, applications |
| 10 | Queues | FIFO operations, circular queues |
| 11 | Trees | Binary trees, traversals |
| 12 | BST | Search trees, insertion, deletion |
| 13 | Graphs | Graph concepts, representations |
| 14 | Graph Algorithms | Traversal, shortest path, MST, topological sort |

### Data Structures Comparison

| Structure | Access | Insert | Delete | Search | Use Case |
|-----------|--------|--------|--------|--------|----------|
| **Array** | O(1) | O(n) | O(n) | O(n) | Random access |
| **Linked List** | O(n) | O(1)* | O(1)* | O(n) | Dynamic size |
| **Stack** | O(1) | O(1) | O(1) | O(n) | LIFO operations |
| **Queue** | O(1) | O(1) | O(1) | O(n) | FIFO operations |
| **BST** | O(log n) | O(log n) | O(log n) | O(log n) | Ordered data |
| **Graph** | O(1) | O(1) | O(1) | O(|V|+|E|) | Relationships |

*At beginning/end

### Algorithm Complexity Summary

| Complexity | Growth | Example |
|------------|--------|---------|
| **O(1)** | Constant | Array access |
| **O(log n)** | Logarithmic | BST search |
| **O(n)** | Linear | List traversal |
| **O(n log n)** | Linearithmic | Merge sort |
| **O(n²)** | Quadratic | Nested loops |
| **O(2ⁿ)** | Exponential | Recursive Fibonacci |

---

*End of Comprehensive Lecture Notes for CT077-3-2 Data Structures*