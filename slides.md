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

- Q: How might regular variables (ex: "hello") be arranged in memory?
- Q: In C, what are the 2 possible values we can output for any variable in memory?
- Q: How are arrays arranged in memory?
- Q: What was the catch in C when declaring an array?
- Potential issue: What if we wanted to insert an element in the array?
   - Q: List alternative solutions to this issue?


<!--
- 2 possible values = address of memory cell, value written in memory cell
- trade off = takes more time when copying original array into bigger array
-->

---
transition: slide-left
---

# Linked Lists

- We'd like a way to have an array-like structure, but without the downsides of contiguous memory when inserting a new element
<img src="/assets/llist.png">
- Each node contains: 
   - a value (data)
   - a reference (pointer) to the next node
- Q: Does inserting a new element in our list solve the problem we originally had with contiguous memory




---
layout: image-right
transition: slide-left
image: /assets/danny.png
backgroundSize: 400px 120px
class: text-left
---

# 10 minute break

🍦 Cool Tips, Trends and Resources:
- 💻 [leetcode](https://leetcode.com/)
- 🕵️ [hackerrank](https://www.hackerrank.com/)
- 🚦[codeSignal](https://codesignal.com/)
- 📡 [interviewBit](https://codesignal.com/)
- 🏫 [Harvard Algorithms Lecture](https://www.youtube.com/watch?v=iCx3zwK8Ms8)
- 🏫 [Harvard Data Structures Lecture](https://www.youtube.com/watch?v=0euvEdPwQnQ&list=PLhQjrBD2T381WAHyx1pq-sBfykqMBI7V4&index=6)
- 🧮 [THE classic CS Textbook](https://edutechlearners.com/download/Introduction_to_algorithms-3rd%20Edition.pdf)

<br>
<hr>
<br>

- 🧪 [Enter anonymous lab questions](https://docs.google.com/forms/d/e/1FAIpQLSevvGARdHQikso-uLqFCO481MABKE5HofuSrlzEPMNQ2ZLykw/viewform?usp=dialog)
- ℹ️ [Course feedback survey](https://circuitstream.typeform.com/to/ZoyYk7px#course_id=SoftwareAN&instructor=9514)

---
transition: slide-left
---

# Homework

- Work on your "Note-taking" midterm app due June 15 midnight EST