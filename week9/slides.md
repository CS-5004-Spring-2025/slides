# Welcome to CS 5004

*Credit to Mark Miller for much of the content presented in this course!*

---

## Week 8

- Project 3 check-in
- Next lab and project coming soon!
- MVC overview
- Tic Tac Toe Design

---

## Model, View, Controller

- Developed for Smalltalk in the 1970s
- A pattern for architecting applications
- Often used in some form for web applications

---

<img src="https://upload.wikimedia.org/wikipedia/commons/a/a0/MVC-Process.svg" style="background-color:white;"
/>

---

## Web applications

<img src="https://docs.aws.amazon.com/images/whitepapers/latest/serverless-multi-tier-architectures-api-gateway-lambda/images/image2.png"/>

---

## Key Principles

- Separation of presentation and model
  * Focus on UI independent of data and logic
  * View same information in different ways
  * Allows easier testing of non-visual objects
- Presentation depends on model, but not vice versa

---

## Key Principles

- Separation of controller from view
  * Most GUI frameworks combine view and controller
- [Fowler](https://learning.oreilly.com/library/view/patterns-of-enterprise/0321127420/)
  recommends separating only when helpful, e.g., systems are complex

---

## Model

- The primary focus of much of our prior work
- Stores data and behavior
- Examples: `TimeCard`, `NutritionRecord`

---

## View

- Display of the model
- We've used `ConsoleView` in most projects
- We'll start developing GUI views as well

---

## Controller

- Updates the model
- Example: instruct model to add new workout record
- Arguably, a menu should be part of the controller

---

## Tic Tac Toe

- Let's play!
- Design -- start with model, view, or controller?
