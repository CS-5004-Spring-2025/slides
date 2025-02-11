# Welcome to CS 5004

*Credit to Mark Miller for much of the content presented in this course!*

---

## Week 6

- Announcements
- Arrays in Java
- Java Generics
- Recursive Data Structures

---

## Announcements

- Quiz on Friday
  * Lists, Streams
- We'll get Project 2 graded as quickly as possible
- Next week: lecture Thursday, visitor on Friday
- Week 8: Sami traveling; stay tuned

---

## Arrays - ints

```java
int[] numbers = new int[10];
// bad style: int numbers[] = new int[10];
int[] withInitializerList = {1, 2, 3};

System.out.println(numbers[9]); // prints 0
System.out.println(numbers[90]); // ArrayIndexOutOfBoundsException
```

---

## Arrays - Objects

```java
Widget[] widgets = new Widget[10];
System.out.println(widgets[0]); // null

widgets[0] = new Widget(1, "cat");
System.out.println(widgets[0]); // Widget{number=1, word='cat'}
```

---

## Array Copy

- There are many ways to copy arrays
- `clone`
- `System.arraycopy`
- These will make a *shallow copy*!
- Creating a deep copy
  * Preferred: use a copy constructor

---

## CS5004SortedList interface

```java
public interface CS5004SortedList<T extends Comparable<T>> {

    void insert(T t);

}
```

---

## Generics

- "Generics allow you to abstract over types."
- We can create a CS5004SortedList of anything, but generics allows us to
  enforce it be one particular thing for a given instantiation. 

--- 

## Let's use TDD!

- What would be some good tests for our List?

---

```java
public CS5004SortedArrayList() {
    elements = (T[]) new Comparable[10];
    size = 0;
}
```

---

```java
public void insert(T element) {
    if (size == elements.length) {
        // TODO: resize!
        return;
    }
    int current = 0;
    while (current < size && element.compareTo(elements[current]) > 0) {
        current++;
    }
    int destination = size;
    while(destination > current) {
        elements[destination] = elements[destination-1];
        destination--;
    }
    elements[destination] = element;
    size++;
}
```