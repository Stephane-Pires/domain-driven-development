---
# try also 'default' to start simple
theme: apple-basic
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Presentation about DDD for developers

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false

colorSchema: 'light'

layout:  intro

---

# Domain Driven Development

An introduction  to software craftmanship

<div class="absolute bottom-10">
  <span class="font-700">
    Stéphane Pires
  </span>
</div>




---
layout: intro-image
image: 'https://khalilstemmler.com/img/blog/ddd-intro/ddd-diagram.svg'
---


---

# What is Domain Driven Development ?

## Key concepts

-  Ubiquitous Language 📝 - What is it ?
-  Domain Mapping 🎨 - A map of what we do ?
-  Crunching Knowledge 🧑‍💻 - There is no bad question only bad answers
-  Smart UI VS Layered Architecture 🤹 - Garden's hut VS Cathedral
-  Entities VS Value Object 🎥 - SPI VS Stéphane
-  Services 📤 - How to modelise something that's not an object
-  Modules 📦 - (What is it ?)
-  Aggregates 🛒 - Un vélo, (roue, guidon, transmission, cadre, etc...)
-  Refactoring 🛠 - Domain modification => Code modification
-  Specification & Predicate 📇 - Rules and Fact
-  Conceptual contour 🏘 - What's the boundaries of my city ?
-  Side Effect Free Function & Closure over domain 🥴 - Clean Architecture, needs clean code

<br>
<br>



---

# So what's the plan ?

```md {all|1}
-  1) Ubiquitous Language 📝 - What is it ?

-  2) Domain Mapping 🎨 - A map of what we do ?

-  3) Crunching Knowledge 🧑‍💻 - There is no bad question only bad answers

-  4) Smart UI VS Layered Architecture 🤹 - Garden's hut VS Cathedral

-  5) Entities VS Value Object 🎥 - SPI VS Stéphane

-  6) Services 📤 - How to modelise something that's not an object

-  7) Modules 📦 - (What is it ?)

-  8) Aggregates 🛒 - Un vélo, (roue, guidon, transmission, cadre, etc...)

-  9) Refactoring 🛠 - Domain modification => Code modification

-  10) Specification & Predicate 📇 - Rules and Fact

-  11) Conceptual contour 🏘 - What's the boundaries of my city ?

-  12) Side Effect Free Function & Closure over domain 🥴 - Clean Architecture, needs clean code
```

---
layout: section
---
# Ubiquitous Language 📝

---
layout: statement
---

# Ubiquitous langages is the lexique of the domain

### Uh, but what's the domain dude ?

---
layout: quote
---

# "A sphere of knowledge or influence. The subject area to which the user applies a program is the domain of the software"
Eric Evans

<!-- 

Knowledge : Concept that pre-exist and used by the used in his subject area

Influence : Concept invented by "us" in order to help the user in his subject area

Activity : 

 -->

---
layout: statement
---

# Ubiquitous langages is the lexique of the domain

### We already saw this one

---
layout: bullets
---

* The ubiquitous langage is rigorous, one word refer to one concept (bijective != surjective)

* The ubiquitous langage can't be translated

* The ubiquitous langage must be used when interacting with domain expert

* The ubiquitous langage evolve has you descover the domain


---
layout: statement
---


## An **INPUT** is an video flux that comes from a **SOURCE**

### Exemple

<!--

INPUT / SOURCE are locked words that refer to concept

We have made an abstraction

-->

---
layout: section
---
# Domain Mapping 🎨

---
layout: statement
---

# Domain mapping is a representation of the structure and interaction of the domain

### It's just a schema ?

---
layout: bullets
---

* Domain mapping aim to abstract technical details

* Domain mapping is a "soft" mapping, not a "hard" mapping 

* Domain mapping is a document shared between stackholders

* Domain mapping must be updated has you disover the domain


---
layout: intro-image
image: 'https://docs.microsoft.com/fr-fr/azure/architecture/microservices/images/ddd1.svg'
---



---
layout: section
---
# Crunching Knowledge 🧑‍💻

---
layout: section
---
# Smart UI VS Layered Architecture 🤹

---
layout: section
---
# Entities VS Value Object 🎥

---
layout: section
---
# Services 📤


---
layout: section
---

# Modules 📦

---
layout: section
---
# Aggregates 🛒
---
layout: section
---
# Refactoring 🛠
---
layout: section
---
# Specification & Predicates 📇
---
layout: section
---
# Conceptual Contour 🏘
---
layout: section
---
# Side Effect Free Function & Closure over domain 🥴