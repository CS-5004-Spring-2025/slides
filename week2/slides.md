# Welcome to CS 5004

*Credit to Mark Miller for much of the content presented in this course!*

---

## Week 2 - Agenda part 1

- Quiz on Friday!
    * Design
    * Testing
    * Types 
    * Syntax
    * Methods
- Conditionals and Iteration
- Collections part 1 (Lists and ArrayList)
- Exceptions
- Static

---

## Conditionals

```java
if (CONDITION) {

} else if (CONDITION) {

} else {

}
```

---

## Math operators

```java
+ - * / % ++ --
```

---

## Logical operators

```java
&& || !
```

*Careful to use double && or ||! Single is a bitwise operator.*

---

## Iteration - while

```java
while (CONDITION) {

}

```
---
## Iteration - dowhile

```java

do {

} while (CONDITION);

```

---

## Iteration - for

```java
for (INITIALIZATION; CONDITION; UPDATE) {

}
```
---

## Iteration - enhanced for

Enhanced for loop or for-each loop

```java

for (TYPE NAME: ITERABLE) {

}

```

---

<img height=600px src="https://ih1.redbubble.net/image.307874987.8434/flat,750x,075,f-pad,750x1000,f8f8f8.u3.jpg"/>

---

## Collections part 0 - Lists

- *"A collection is an object that represents a group of objects (such as the classic ArrayList class)."*
- The [Collections
  Framework](https://docs.oracle.com/en/java/javase/23/docs/api/java.base/java/util/doc-files/coll-index.html)
  includes is a framework for representing collections, e.g., lists and maps.

---

## List

- `List` is an *interface* that specifies the operations performed on an ordered collection.
- `ArrayList` is an implementation of the `List` interface that uses an array.
- [*Generics*](https://www.baeldung.com/java-generics) provide a layer of
  abstraction that allows using the same implementation to hold different types
  of objects.


---

## Creating a List

```java
List<String> names = new ArrayList<String>();
```

- Must use object types in pointy brackets
- Use primitive type wrappers, e.g., `Integer`

---

<img height=600px src="https://www.memecreator.org/static/images/memes/5466706.jpg"/>

---


## Exceptions 

- Generated under error conditions
- In Java, there are *checked* and *unchecked* exceptions
  * Checked *must* be caught
  * Try to *avoid* unchecked
- Unchecked e.g. divide by zero, arrayindexoutofbounds
- Checked e.g., filenotfound

---

## Exceptions - syntax


```java

try {

} catch (EXCEPTION_TYPE NAME) {


}

```

---

## Java I/O

[Useful tutorial](https://www.geeksforgeeks.org/java-io-tutorial/)

<img
src="https://media.geeksforgeeks.org/wp-content/uploads/20210913171831/TypesofJavaIOStreams.png"/>

---

## Java I/O - example

- `FileReader` reads characters from a file
- `BufferedReader` can read a line of text from a file
  * Constructor requires a `FileReader`

```java
BufferedReader br = new BufferedReader(new FileReader(fileName));
```

---

## Scanner

[`Scanner`](https://www.w3schools.com/java/java_user_input.asp) can read other types

```java
Scanner scanner = new Scanner(System.in);
System.out.println("Enter a number: ");
int result = scanner.nextInt();
```

---

## try-with-resources

Ensure the resource is closed!

```java
try (Scanner scanner = new Scanner(new File(fileName))) {
  while (scanner.hasNextLine()) {
    System.out.println(scanner.nextLine());
  }
} catch(FileNotFoundException fnf) {

}
```

---

## Propagating exceptions

If you don't know how to handle the exception, throw it to the caller!


```java
public void readFile(String fileName) throws FileNotFoundException {
```

---

## Custom exceptions

- You can create your own exceptions!
- We'll learn more later...

```java
throw new ExceptionType("message...");
```

---

<img height=600px src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSznfwPxsx0OxLaD11ixVY_W2DQgfVG6mEBLA&s"/>

---

## == vs .equals

- `==` used for primitive types and to compare references
- `.equals` compares object *values*
- You must implement `.equals`!

---

# static

- Allocated memory space only once
- Accessible without object instantiation
- Associated with the class, not objects
- Cannot access non-static members
- Cannot be overridden

*https://www.geeksforgeeks.org/static-keyword-java/*

---

## static - rules of thumb

- **Do not** make things static because your IDE recommends it!
- Static methods generally standalone
  * Operate only on parameters and save no state
- Static data shared across all objects!

---

## Example: `Math`

[`Math` API](https://docs.oracle.com/en/java/javase/23/docs/api/java.base/java/lang/Math.html)


```java
Math.abs(-4.5);
```

*Note: method is called using classname.*

---

## static Data Members

- Constants
- Number of instances created

---

<img height=600px src="https://europe1.discourse-cdn.com/arduino/optimized/4X/c/f/3/cf3c7aa57676663791370a60b173e6a3c8c9f124_2_669x500.jpeg"/>