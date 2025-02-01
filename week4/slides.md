# Welcome to CS 5004

*Credit to Mark Miller for much of the content presented in this course!*

---

## Week 4

- Quiz on Friday
  * Switch/Enum
  * Inheritance
- Abstraction
  * `Predicate`
  * Stream API
  * `Comparable` and `Comparator`
- `Map` 
- Abstract Data Types (time permitting)

---

## Project 1

- GitHub auto-grading feedback was not set up correctly
- We will run ./gradlew test and ./gradlew check on your solution

---

## Library Application

- *Refactored* our solution
  * Made `Library` a class to manage the item collection
  * Created a `LibraryDriver` to instantiate `Library`
  * Created a `LibraryFactory` to construct a `Library`

---

## Factory Pattern

- *Creational* software pattern
- [...replace direct object construction calls (using the new operator) with calls to a special factory method](https://refactoring.guru/design-patterns/factory-method)
- Subtly different from [Builder](https://refactoring.guru/design-patterns/builder)
- More later in the semester...

---

## Library Methods

- `checkoutPublication`
- `countAvailableItems`
- `countAvailableBooks`
- `getAvailableBooks`
- `getCheckedOutMagazines`

---

## Abstracting the Predicate

- `getAvailableBooks` and `getCheckedoutMagazines` look very similar
- Create a `filterLibrary` method and pass the filter as a parameter

---

## Pseudocode

```java
create a result set
for each item
  if it passes the filter test
    add it to the result set
return the result set
```

---

## Code

```java
public List<LibraryItem> filterLibrary(Predicate<LibraryItem> predicate) {
    List<LibraryItem> filteredItems = new ArrayList<>();
    for (LibraryItem item : items) {
        if (predicate.test(item)) {
            filteredItems.add(item);
        }
    }
    return filteredItems;
}
```

---

## Predicate

- [`Predicate`](https://docs.oracle.com/javase/8/docs/api/java/util/function/Predicate.html)
  is an interface 
- When implemented, the programmer specifies a method that will evaluate to true
  or false
- See `CheckedOutMagazinesPredicate`

---

## Anonymous Classes

- Class without a name
- Declare and instantiate at the point of use
- [Use them if you need to use a local class only once](https://docs.oracle.com/javase/tutorial/java/javaOO/anonymousclasses.html)

[Anonymous Classes](https://www.baeldung.com/java-anonymous-classes)

---

```java
List<LibraryItem> result = library.filterLibrary(
        new Predicate<LibraryItem>() {
            @Override
            public boolean test(LibraryItem libraryItem) {
                return libraryItem instanceof Book b && !b.isCheckedOut();
            }
        }
);
```

---

## Lambda Expressions

- [...a short block of code which takes in parameters and returns a value](https://www.w3schools.com/java/java_lambda.asp)

```java
Predicate<LibraryItem> availableBooks = 
            item -> (item instanceof Book b) && (!b.isCheckedOut());
```

---

## Higher-Order Functions

- Takes a function as a parameter or returns a function as a result

```java
library.filterLibrary(item -> item instanceof Book b && !b.isCheckedOut());
```

---

## Streams API

- Supports ["functional-style" operations on streams of elements](https://docs.oracle.com/javase/8/docs/api/java/util/stream/package-summary.html), e.g., our List
  of LibraryItem
- `items.stream()`, works for any `Collection`
- Operations: filter, map, reduce (there are more) 

[SitePoint Tutorial](https://www.sitepoint.com/java-8-streams-filter-map-reduce/)

---

## map

- Apply an operation to all items in the stream
- Pass the operation to be performed as the map parameter
- Operation is *lazy* 

```java
// Option 1
items.stream().map(i -> i.returnItem()).toList()

// Option 2
items.stream().map(LibraryItem::returnItem).toList()

```

---

## filter

- Create a new collection that is a subset of the old
- Pass a boolean expression as the filter parameter

```java
items.stream().filter(i -> i instanceof Publication).toList();
```

---


## `checkoutPublication` with streams

```java
List<LibraryItem> result =
        items.stream()
        .filter(item -> (
                (item instanceof Publication p) && p.getTitle().equals(title) && !p.isCheckedOut()
                )
        ).toList();
if (result.size() != 1) {
    return false;
}
return result.getFirst().checkoutItem();
```

---

# How about a `count` method?

---

## Comparable

- An interface to allow comparing two objects
- Used by `Collections.sort`
- Must implement the `compareTo` method
- Step 1: compare `BookDemo` objects by title

---

## Comparator

- Allows custom sorting logic
- What if we want to sort `BookDemo` objects in different ways depending on the
  specific application? 
- Books may be naturally compared using title, but a separate comparator may
  provide the ability to sort by author name

---

## Map

- Maps key to value

```java
public Map<String, List<Book>> $$booksByAuthor() {
    Map<String, List<Book>> result = new HashMap<>();
    for (LibraryItem item : items) {
        if (item instanceof Book b) {
            List<Book> books = result.get(b.getAuthor());
            if (books == null) {
                books = new ArrayList<>();
            }
            books.add(b);
            result.put(b.getAuthor(), books);
        }
    }
}

```

---

## ...better...

```java
// The List is a reference!
if (item instanceof Book b) {
    result.computeIfAbsent(b.getAuthor(), k -> new ArrayList<>()).add(b);
}
```

---

## But also

```java$$

$$
Map<String, List<Book>> result =
        items.stream()
                .filter(Book.class::isInstance)
                .map(Book.class::cast)
                .collect(Collectors.groupingBy(Book::getAuthor));
return result;

```