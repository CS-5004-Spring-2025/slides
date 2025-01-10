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
- `this` keyword
- Object instantiation
- Unit tests
- Javadoc

---

## Packages

- Group classes with similar functionality
- In many place, must use *fully qualified* class name
  * `car.CarDriver`

---

## Variables

- Must specify *type*
- There are **eight** *primitive* types
- `String` is an object type

```java
int x;
int y = 15;
String className = "CS 5004";
```

---

## Data members

- Variables associated with an object
- Include *access modifier*

```java
private String make;
```

---

## Methods

- Operations to be performed on an object.
- Method header:
  * access_modifier return_type name(params) 
- Parameters are `type name` and comma separated

```java
public String getMake() {


}
```

---

# `this` keyword

- Used to refer to the data member associated with the object
- Like `self`!
- Unlike `self` it doesn't need to be specified if there is no variable with the
  same name in the local scope

---

## Object instantiation and calling methods

- Invoke the constructor to create a new instance of the class
- type name = `new` type(actual_parameters)
- object_name.method_name(parameters)

```java
Car c = new Car("Smart", "forTwo", 2016);
c.getMake();
c.drive(50);
```

---

## Unit tests

- Ensure that one small piece, e.g., a method, of your program works as expected
- Classes in test/java
- We'll use the JUnit 5 library

```java
@Test // annotation that indicates this is a test method
public void testGetItem() { // looks like a regular method
  InventoryItem ii = new InventoryItem("Apples", 10);
  assertEquals("Apples", ii.getItem()); // assertEquals(expected, actual)
}
```


