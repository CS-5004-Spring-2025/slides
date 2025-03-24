# Welcome to CS 5004

*Credit to Mark Miller for much of the content presented in this course!*

---

## Week 11

- [Design Patterns](https://refactoring.guru/design-patterns)
  * Iterator
  * Builder
  * Decorator

---

## Design Patterns

- [Design Patterns: Elements of Reusable Object-Oriented
  Software](https://learning.oreilly.com/library/view/design-patterns-elements/0201633612/)
  is the seminal book on design patterns. 
- Often referred to as the "Gang of Four"
- Three categories: Creational, Structural, Behavioral

---

## Iterator

- Behavioral design pattern
- The [`Iterator`](https://docs.oracle.com/en/java/javase/23/docs//api/java.base/java/util/Iterator.html) interface enables traversal through a collection
- [`Iterable`](https://docs.oracle.com/en/java/javase/23/docs//api/java.base/java/lang/Iterable.html) interface that denotes that something can be iterated
- `Iterator` methods: `hasNext`, `next`
- `Iterable` methods: `Iterator<T> iterator()`

---

## Iterable Library

```java
for(LibraryItem li: library) {
    System.out.println(li);
}
```

---

## Iterable Library

- Make `Library` *iterable*
- Create a `LibraryIterator`
  * add `size` and `getItem` to `Library`
- Caution: the underlying collection could change!

---

## The Jackson Library

- [`JsonNode`](https://github.com/FasterXML/jackson-databind/blob/39ac2b668382cf6c28f1b554530d1d93406cf080/src/main/java/com/fasterxml/jackson/databind/node/ObjectNode.java)

---

## Builder 

- Creational design pattern
- [Example of a variation on Builder](https://blogs.oracle.com/javamagazine/post/exploring-joshua-blochs-builder-design-pattern-in-java)
- Consider a `Book` that has many optional data members
- Create a *static inner class*
- Include set methods for optional fields
  * return the Builder!
- Include a `build` method that creates the object

---

## Decorator

- Structural design pattern
- *Wraps* an object to add new behaviors
- An alternative to inheritance
- Consider adding new menu functionality
   * Could use inheritance or a decorator
- Example: Menu class

---

## Decorator: Another example

- Notifier: SMS, Facebook, Slack
- How do you enable many combos?
- Also, java.io library!

*From [Refactoring Guru](https://refactoring.guru/design-patterns/decorator)*
