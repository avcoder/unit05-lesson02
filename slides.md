---
# You can also start simply with 'default'
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: /assets/intro.jpg
# some information about your slides (markdown enabled)
title: Software Development | Foundations
info: |
  ## Software Development | Foundations
# apply unocss classes to the current slide
class: text-left
drawings:
  persist: false
transition: slide-left
mdc: true
---

# Algorithms and Data Structures
Algorithms and Structural Foundations - part 2/8

- [ ] Linked Lists
- [ ] Dictionaries
- [ ] Recursion

<div class="abs-br m-6 text-xl">
  <a href="https://github.com/slidevjs/slidev" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

<!--
-->

---
transition: slide-left
layout: center
class: text-center
---

# In ASCII, the capital `A` has value 65.  Yet in C, I can set an int variable to 65
How does the computer know how to interpret `01000001`?

---
transition: slide-left
---

# Recap (pg.1)

```c
char ch = 65;     // or 'A'
int num = 65;
```

- At the binary level, both ch and num may store the same value (01000001), but:
   - char ch is interpreted as a character → 'A'
   - int num is interpreted as a number → 65
- They're both just bytes in memory. The difference lies in how the C compiler and standard library interpret or print them.

| Declared As | Meaning         | Output with `printf`      |
| ----------- | --------------- | ------------------------- |
| `char ch`   | ASCII character | `printf("%c", ch);` → A   |
| `int num`   | Integer value   | `printf("%d", num);` → 65 |
| `char ch`   | Integer value   | `printf("%d", ch);` → 65  |


---
transition: slide-left
---

# Recap (pg.2)
- Q: How is an array arranged in memory?

<img src="/assets/memory.jpg" width="500px">

---
transition: slide-left
---

# Recap (pg.3)

- Q: What is [Big O notation](https://www.bigocheatsheet.com/)?
- Q: What's the Big O notation for accessing an element in the array?
- Q: What's the Big O notation for inserting a new element?
- Q: What's the Big O notation for deleting a new element?
- Q: Are arrays growable?
- Q: In C, what are the 2 possible values we can output for any variable in memory?
   - in JS, how can we access the value of a variable?
   - in JS, how can we access the address of a variable?
- Q: What was the catch in C when declaring an array?
   - Potential issue: What if we wanted to insert an element in the array?
   - Q: List alternative solutions to this issue?


<!--
- char str[] = "Hello";
- char str[] = { 'H', 'e', 'l', 'l', 'o', '\0' };
- Big O = if space not available O(n)
- 2 possible values = address of memory cell, value written in memory cell
- in JS you cannot access the memory address of a variable directly.
- catch = size must be known at compile time.  Can't resize. 
- issue = takes time array to bigger array; can't accidentally overwrite 'h' for 'hello'
-->

---
transition: slide-left 
layout: center
class: text-center
---

# What if we could structure our data, such that we can connect random allocated memory blocks  instead of contiguous memory blocks?
Like: connect-the-dots

---
transition: slide-left
---

# Data Structure: Linked Lists 
Can we solve the problem of copying an entire array to a new location in memory when inserting?

<img src="/assets/llist.png">

- Each node contains: 
   - a value (data, whose value can be anything. ex: int)
   - a reference (pointer) to the next node (whose value is the address of the next node in memory)
- Q: Does inserting a new element in our list solve the problem we originally had with contiguous memory
- Q: What is the Big O notation for inserting/deleting a new element at the beginning of a linked list?
- Q: What is the Big O notation for inserting/deleting a new element at the end of a linked list?
   - How might we do better for inserting/deleting at end?
- Q: What is the Big O notation for accessing an element in a linked list?

<!--
- O(1) for inserting a new element at beginning of a linked list
- O(n) for inserting a new element at end of a linked list
- Unless you have tail node then it's O(1) for inserting at end
- O(n) for accessing an element in a linked list since you must traverse
-->

---
transition: slide-left
---

# Exercise: Arrays vs Linked Lists

| Feature                       | **Array**                                         | **Linked List**                                   |
| ----------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| **Memory Layout**             | Contiguous memory                                 | Non-contiguous memory                             |
| **Access Time**               | `O(?)` random access via index              | `O(?)` traversal needed                     |
| **Insertion/Deletion (middle)**        | `O(?)` elements need shifting             | `O(?)`                    |
| **Memory Per element Overhead**           | Low (just data)                                   | High (extra pointer per node)                     |
| **Implementation Simplicity** | Simpler                                           | More complex (especially for doubly linked lists) |
| **Use Case Suitability**      | Best for random access and known-size collections | Best for frequent insertions/deletions            |

<!-- 
- Access Time: O(1) vs O(n)
- Insertion/Deletion (middle): O(n) vs O(1)

-->

---
class: text-center
layout: center
transition: slide-left
---

# Which DS could be implemented using Linked Lists?

<img src="/assets/ds1.gif" width="400px" style="display: inline-block">

---
transition: slide-left
---

# Static Memory Allocation in C - Arrays

```c
#include <stdio.h>

int main(void) {
    int list[3];

    list[0] = 1;
    list[1] = 2;
    list[2] = 3;

    for (int i = 0; i < 3; i++) {
        printf("%d at %p\n", list[i], (void*)&list[i]);
    }
}
```

---
transition: slide-left
---

# Dynamic Memory Allocation in C - Arrays

```c
#include <stdio.h>
#include <stdlib.h>

int main(void) {
    int list[3] = {1, 2, 3}; // static memory allocation
    int *list2 = malloc(4 * sizeof(int)); // allocate memory for 4 integers

    if (list2 == NULL) { 
      return 1; // Memory allocation failed
    } 

    for (int i = 0; i < 3; i++) {
      list2[i] = list[i]; // copy values from static array to dynamic array
    }
    list2[3] = 4; // add a new element

    for (int i = 0; i < 4; i++) {
        printf("%d at %p\n", list2[i], (void*)&list2[i]);
    }

    free(list2); // free the dynamically allocated memory
}
```

---
transition: slide-left
---

# Equivalent in JS
JS doesn't have memory allocation like malloc/free.  Rather arrays are dynamic and managed automatically

```js
function main() {
    const list = [1, 2, 3];  // Static array equivalent
    const list2 = new Array(4); // Dynamic array with extra space - just create a new array

    // Copy first 3 elements from list to list2
    for (let i = 0; i < 3; i++) {
        list2[i] = list[i];
    }

    // Add new element
    list2[3] = 4;

    // Print values with their indices (JS has no direct access to memory addresses)
    for (let i = 0; i < 4; i++) {
        console.log(`Value: ${list2[i]}, Index: ${i}`);
    }
    // No need to free memory in JS, garbage collector handles it
}

main();
```

---
transition: slide-left
---

# Dictionaries


---
layout: image-right
transition: slide-left
image: /assets/addy.png
backgroundSize: 400px 300px
class: text-left
---

# 10 minute break

🍦 Cool Tips, Trends and Resources:
- 🖇️ [Linked Lists](https://www.geeksforgeeks.org/linked-list-data-structure/)
- 👩‍💻 [NeetCode](https://www.freecodecamp.org/news/prepare-for-technical-interviews-using-neetcode-150)

<br>
<hr>
<br>

- 🧪 [Enter anonymous lab questions](https://docs.google.com/forms/d/e/1FAIpQLSevvGARdHQikso-uLqFCO481MABKE5HofuSrlzEPMNQ2ZLykw/viewform?usp=dialog)
- ℹ️ [Course feedback survey](https://circuitstream.typeform.com/to/ZoyYk7px#course_id=SoftwareAN&instructor=9514)

---
transition: slide-left
---

# Recursion

---
transition: slide-left
---

# Homework

- Work on your "Note-taking" midterm app due June 15 midnight EST