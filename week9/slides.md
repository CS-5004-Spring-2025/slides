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

## Project 3 Notes

- Jar files
- Returning multiple items

---

## Jar files

- Recall, java files get compiled into class files
- If you build a library you want to allow others to use, you want to hand off
  your class files
- Class files get packaged together in a *jar* file, like a zip file

---

## Running a program relying on a jar

- Option 1: add the jar to your classpath
- Option 2: create a "fat jar" for your program including dependencies

---

## Returning multiple items

- Avoid `Object` in pretty much all cases
- Create a specialized type!

---

## Tic Tac Toe

- Let's play!
- Design -- start with model, view, or controller?
