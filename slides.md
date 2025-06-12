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
---

# Recap

- Q: What is Big O notation?
- Q: How is an array arranged in memory?
- Q: How might regular characters (ex: "hello") be arranged in memory?
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

# Dynamically Allocating Memory in C

---
transition: slide-left
---

# Dynamically Allocating Memory in JS

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