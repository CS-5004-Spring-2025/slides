# Welcome to CS 5004

*Credit to Mark Miller for much of the content presented in this course!*

---

## Week 2 - Agenda part 1

- Quiz on Friday!
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

## Iteration - foreach

```java

for (TYPE NAME: COLLECTION) {

}

```

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

---

## Exceptions 

- Generated under error conditions
- In Java, there are *checked* and *unchecked* exceptions
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