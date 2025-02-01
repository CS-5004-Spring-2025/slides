# Welcome to CS 5004

*Credit to Mark Miller for much of the content presented in this course!*

---

## Week 5

- `Comparable` and `Comparator` continued
- Lab/Project questions
- `Map` and `HashMap`
- Design exercise - inheritance vs. composition

---

## Comparable

- An interface to allow comparing two objects
- Used by `Collections.sort`
- Must implement the `compareTo` method
- Step 1: compare `BookDemo` objects by title

---

```java
// in BookDemo
public class BookDemo implements Comparable<BookDemo> {}

// a method of BookDemo
public int compareTo(BookDemo o) {
  return this.title.compareTo(o.title);
}

// in Driver
List<BookDemo> books = new ArrayList<>();
// add books

// sort by the natural order of the books
// uses compareTo from BookDemo
Collections.sort(books);

```

---

## Comparator

- Observation: `compareTo` only allows us to sort in one way
- `Comparator` allows custom sorting logic
- What if we want to sort `BookDemo` objects in different ways depending on the
  specific application? 
- Books may be naturally compared using title, but a separate comparator may
  provide the ability to sort by page count

---

```java
// in Driver
Collections.sort(books, (b1, b2) -> b1.getPageCount() - b2.getPageCount());

// or, using an anonymous class
Collections.sort(books,
        new Comparator<BookDemo>() {
            public int compare(BookDemo o1, BookDemo o2) {
                return o1.getPageCount() - o2.getPageCount();
            }
        });
```

---

# Lab/Project questions?

---

## Map

- Maps key to value
- `get` and `put` are common methods
- Task: implement a method `booksByAuthor` that returns a Map of author name to
  list of Book by that author

---

```java
public Map<String, List<Book>> booksByAuthor() {
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

```java

Map<String, List<Book>> result =
        items.stream()
                .filter(Book.class::isInstance)
                .map(Book.class::cast)
                .collect(Collectors.groupingBy(Book::getAuthor));
return result;

```

---

## Inheritance vs. Composition

- Inheritance allows us to define an "is a" relationship
  * A `Book` *is a* `Publication`
  * A `Dog` *is a* `Animal`
  * A `Circle` *is a* `Shape`
- *Composition* defines a *has a* relationship
  * A `Book` *has a* author

---

## Library refactor

- Let's keep track of all library card holders (users)
  * When a `Publication` is checked out, keep track of who has it checked out
  * For a user, keep track of all `Publications` checked out

---

## Loanable?

- Recall our conversation about whether we could refactor our solution to have a
  `Loanable` interface and a `LibraryItem` abstract class
  * Allows us to have functionality like checkout and return in superclass of
    `Publication`, `Media`, etc.

- And, discuss...

---

## One option

- Create a `User` class
  * id and list of items checked out
- Extract `Loanable` interface and implement `LibraryItem`
  * properties: id, loanHolder
  * checkout/return need the `User`
  * `Publication` can get checkout/return from `LibraryItem`

