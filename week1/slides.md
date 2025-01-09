# Welcome to CS 5004

*Credit to Mark Miller for much of the content presented in this course!*

---

## Week 1 - Agenda

- Overview of 5004
- Intros
- Syllabus and policies
- First OOD program (in Java)

---

This course is about object-oriented design! It is not a "Java" course.

---

# Why OOD?

- Produce software that is...
  * robust
  * maintainable
  * reusable

---

*How do you build a piece of software large enough that you can't fit all if it your head at the same time?*

---

# OOD Principles

- Encapsulation: bundling data and methods together
- Information hiding: exposing *behavior*, not how it works
- Abstraction: managing complexity by supressing low-level details
- Polymorphism: same concept taking many forms
- Inheritance: hierarchical relationship between objects

---

# Other Themes

- Test-Driven Development (TDD)
- Avoiding repetitive code
- Documentation
- Design patterns
  * Model/View/Controller
- Reading code
- Understanding *why*

---

Syllabus Review 

---

# Java Features

- Compiled language
- Strongly typed 
- Whitespace doesn't matter (to the compiler)

---

## Java Compilation

<img src="https://media.geeksforgeeks.org/wp-content/uploads/java.jpg"/>

---

Hello, World!

---

Setting up your environment

---

<!-- .slide: data-background-color="white" -->

<img src = 'slido.png'/>

---

# Tools we'll use

- IntelliJ (or VS code, or another IDE)
- git
- gradle
- checkstyle

---

# gradle

- Build tool
- One step build/test of your project
- For now, helps with auto-grading tests
- Later, helps manage dependencies

---

# checkstyle

- Make sure your code adhere to style guidelines

---

# Cloning from GitHub - IntelliJ

- File > New > Project from Version Control
- Enter repo URL

---

### Project structure

- `.github`: auto-grading stuff
- `.idea`: IntelliJ stuff 
- `config`: style checking stuff
- `gradle`: gradle wrapper stuff
- `.gitignore`: files not added to your repo
- `build.gradle.kts`: build scripts -- *ignore*
- `gradlew/.bat`: wrapper scripts -- *ignore*
- `settings.gradle.kts`: settings -- *ignore*
- `build`: class files
- `README.md`: assignment instructions
- `src`: YOUR CODE HERE

---

# `src`

`main > java > classes/packages`
- all of your source code will be here

`test > java > classes/packages`
- all of the test cases will be here

---

# Program Compilation

- IntelliJ mostly does this automagically
- Build > Build Project
  * Produces class files in `build`

---

# Program execution

- Green "play" button on top right
- Right-click on class with main method > Run

---

# Terminal

- `java classname`
  * Works if the *class* files are in the same directory
- Specify *classpath*
- `java -cp build/classes/java/main ClassName`
  * Must specify *package*

---

# Lab 1

- Fill in a ```Car``` class
- Create a *driver*
- Fill in five unit tests

---

## Necessary concepts

- Packages
- Variable declaration
- Method declaration
- Javadoc
- `this` keyword
- Object instantiation
- Unit tests