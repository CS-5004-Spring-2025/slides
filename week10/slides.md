# Welcome to CS 5004

*Credit to Mark Miller for much of the content presented in this course!*

---

## Week 10

- Next week
  * Tuesday - panel in NSB 215
  * Thursday - Interactive grading 

- Refactoring and code smells

*Much of this material comes from Refactoring: Improving the Design of Existing
Code by Martin Fowler.*

---

## Refactoring

*Refactoring (noun): a change made to the internal structure of software to
make it easier to understand and cheaper to modify without changing its
observable behavior.*

---

## When to refactor

*The Rule of Three: The first time you do something, you just do it. The second time you do something similar, you wince at the duplication, but you do the duplicate thing anyway. The third time you do something similar, you refactor.*

---

## When to refactor

- Preparatory Refactoring - Making It Easier to Add a Feature
  * Moving to MVC makes it easier to add a new View feature
- Comprehension Refactoring: Making Code Easier to Understand
  * Renaming variables, simplifying logic, decomposing a long function
- Litter-Pickup Refactoring
  * Identical functions that can be simplified
- Refactoring should make programming *faster*

---

*It's also a common error to see refactoring as something people do to fix past
mistakes or clean up ugly code. Certainly you have to refactor when you run into
ugly code, but excellent code needs plenty of refactoring too. Whenever I write
code, I'm making tradeoffs-how much do I need to parameterize, where to draw the
lines between functions? The tradeoffs I made correctly for yesterday's feature
set may no longer be the right ones for the new features I'm adding today. The
advantage is that clean code is easier to refactor when I need to change those
tradeoffs to reflect the new reality.*

---

## When not to refactor

- Code that doesn't need to be modified (and can be treated as an API)
- If it is easier to just rewrite

---

## Code smells

- Mysterious Name
- Duplicated Code *
- Long Function
- Long Parameter List *
    * Data Clumps
- Global Data/Mutable Data
    * Avoid references to mutable data
- Large Class
- Dead Code

---

## Code smells

- Divergent Change *
  * A module is often changed for different reasons
  * Indicates a violation of SRP
- User class
  * first_name, last_name
  * street_address, city, state
  * list of saved credit cards

---

## Code smells

- Shotgun Surgery *
  * A change in one place requires a bunch of other small changes
- Bank account
  * withdraw -- if balance < MIN
  * transfer -- if balance < MIN

---

## Code smells

- Primitive Obsession
  * Wrap primitive types in objects as appropriate
- Speculative Generality
  * YAGNI
- Temporary Field
  * A field set in only some circumstances