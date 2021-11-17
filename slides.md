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

# Ubiquitous languages is the lexique of the domain

### Uh, but what's the domain dude ?

---
layout: quote
---

# "A sphere of knowledge or influence. The subject area to which the user applies a program is the domain of the software"
Eric Evans

<!-- 

Knowledge : Concept that pre-exist and used by the used in his subject area

Influence : Concept invented by "us" in order to help the user in his subject area

 -->

---
layout: statement
---

# Ubiquitous languages is the lexique of the domain

### We already saw this one

---
layout: bullets
---

* The ubiquitous language is rigorous, one word refer to one concept (bijective != surjective)

* The ubiquitous language can't be translated

* The ubiquitous language must be used when interacting with domain expert

* The ubiquitous language evolve has you descover the domain

* The ubiquitous language helps the transmission of knowledge


---
layout: statement
---


## An **INPUT** is a video flux that comes from a **SOURCE**

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

* Code isn't sufficent because it's **too detailed**

* Domain mapping is coupled with the code but **less detailed**


---
layout: intro-image
image: 'https://docs.microsoft.com/fr-fr/azure/architecture/microservices/images/ddd1.svg'
---



---
layout: section
---
# Crunching Knowledge 🧑‍💻

---
layout: statement
---

# Crunching Knowledge is the activity of discussing domain with domain expert

### You'r gonna argue a lot !


---
layout: bullets
---

* Crunching Knowledge is an attitude to adopt when you'r looking for domain information

* Don't assume behavior or definition, force domain expert to provide explanation

* Start with use case, look for requirements, understand intent of use case, explore scenarios

* It's about going deep enough to truly understand a subject


---
layout: section
---
# Smart UI VS Layered Architecture 🤹

---
layout: statement
---

# Smart UI Architecture : Fast, Simple, Rigid

### Release next week !

---
layout: quote
---

# "The situation where a smart UI is called for is if the application is dominated by data entry and display with any business logic being simple enough that it can be readily encoded in the UI."
Levis Ramsey

<!-- 

Knowledge : Concept that pre-exist and used by the used in his subject area

Influence : Concept invented by "us" in order to help the user in his subject area

 -->

---
layout: bullets
---

* Smart UI, doesn't have layers (application, domain, infrastructure)

* A good choice if you don't expect modification in business rules

* Refactoring is gonna be hard

---
layout: statement
---

# Layered Architecture : Slow, Complexe, Flexible

### Build to last !

---
layout: quote
---

# "Layered architecture is all about the organization of code for the separation of concerns. Each layer contains logic related to a particular concern."
Me, inspired by ThinkToCode [layered Architecture](https://www.thinktocode.com/2018/07/05/layered-architecture/)

<!-- 

Knowledge : Concept that pre-exist and used by the used in his subject area

Influence : Concept invented by "us" in order to help the user in his subject area

 -->

---
layout: bullets
---

* Isolating the Domain layer is a pré-réquisit to DDD

* Layered Architecture simplify domain refactoring

* Common layers are  UI / Application / Domain / Infrastructure 

* The more layer, the more burden to implement a feature

* Each layer communicate only with Layer +  1  and Layer - 1

---
layout: intro-image
image: 'https://user.oc-static.com/upload/2020/05/05/15886650000516_Layered_High_Level.png'
---

---
layout: section
---
# Entities VS Value Object 🎥

---
layout: statement
---

# SPI Vs Stéphane

### Narcissism at it's upmost

---
layout: bullets
---

```ts
// Seat and Ticket are Value Object
function getMyCinemaTicket(money: Number, movie: String): Ticket {
  
  if (!cinemaManager.isSeatAvailable(movie)) {
    return `Sorry no more seat available for ${movie}`
  }
  
  if (cinemaManager.takePayement(money))  {
    let Ticket = cinemaManager.giveTicket(movie) 
  } else {
    return `Sorry there is not enough money`
  }
  
  return ticket
}
```
---
layout: bullets
---q

```ts 
// Seat and Ticket are Entities
function getMyCinemaTicket(money: Number, movie: String, seat: Number): Ticket {
  
  if (!cinemaManager.isSeatAvailable(movie, seat)) {
    return `Sorry no more seat available for ${movie}`
  }
  
  if (cinemaManager.takePayement(money))  {
    let Ticket = cinemaManager.giveTicket(movie, seat) 
  } else {
    return `Sorry there is not enough money`
  }
  
  return ticket
}
```


---
layout: intro-image
image: 'https://khorikov.org/images/2021/2021-02-09-entity-vs-value-object.png'
---

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

---
layout: section
---
# Conclusion 🚀

---
layout: bullets
---

The Blue book has it his is outdated (2004 & hard POO). But the concept inside are still relevant

* Domain Driven Architecture need a Domain

* Need to be implemented at the beginning of a project and refactored during the lifetime of the project

* Give **Flexibility** at the cost of **Layering** 

* Is Hard

* Is not bound to POO, but might be harder to implement without it

---
layout: section
---
# Action 👮‍♂️

---
layout: bullets
---

* (re)Discover our Domain

* Find our Ubiquitous Language

* Create a "soft" Domain mapping

* Learn about different approach of DDD distant from POO [Domain modeling made functional](https://pragprog.com/titles/swdddf/domain-modeling-made-functional/)

* Find a way to link new language/framework with Layered architecture
