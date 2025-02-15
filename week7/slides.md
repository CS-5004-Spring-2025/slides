# Welcome to CS 5004

*Credit to Mark Miller for much of the content presented in this course!*

---

## Week 7

- Lecture Thursday, guest on Friday
- Project 3
- JSON
- Collections

---

## JSON

- [Javascript Object Notation](https://www.json.org/json-en.html)
- "lightweight data-interchange format"

```json
{
  "author": "Octavia Butler",
  "title": "Kindred",
  "pageCount": 320
}
```

---

## Or...

```json
{
  "books": [
    {
      "author": "Octavia Butler",
      "title": "Kindred",
      "pageCount": 320
    },
    {
      "author": "Octavia Butler",
      "title": "The Parable of the Sower",
      "pageCount": 245
    }
  ]
}
```

---

## JSON Parsing

- There are many Java libraries you can use for parsing JSON.
- [https://www.baeldung.com/java-json](https://www.baeldung.com/java-json
- I'll demo [Jackson](https://github.com/FasterXML/jackson)

---

## Adding a dependency

```
dependencies {
    testImplementation(platform("org.junit:junit-bom:5.10.0"))
    testImplementation("org.junit.jupiter:junit-jupiter")
    implementation("com.fasterxml.jackson.core:jackson-databind:2.0.1")
    implementation("com.fasterxml.jackson.datatype:jackson-datatype-jsr310:2.15.0")
}
```

- Gradle > Sync All Gradle Projects

---

## Option 1: JSON to POJO

- Serialize/deserialize JSON into a "plain old java object"
- Step 1: create the POJO class

```java
public class Book {

    @JsonProperty("author")
    private String author;

}
```

---

## Then...

```java
ObjectMapper mapper = new ObjectMapper();
try {
    // Book is a plain old java object (POJO).
    // mapper will create an instance of book from a json file.
    Book book = mapper.readValue(new File("resources/book.json"), Book.class);

    mapper.writeValue(new File("resources/book.out.json"), book);
}
```

---

## Option 2: A more manual approach

```json
 {
  "tasks": [
    {
      "description": "Complete Project 2",
      "deadline": "2025-02-04"
    },
    {
      "description": "Slides for Linked Lists",
      "deadline": "2025-02-01"
    }
  ]
}
```

---

## Aside: LocalDate

- [LocalDate](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/time/LocalDate.html)
  can store month, day, year

```java
LocalDate today = LocalDate.parse("2025-02-14");
System.out.println(today.getMonth());
```

---

## JsonNode Class

- [JsonNode](https://fasterxml.github.io/jackson-databind/javadoc/2.7/com/fasterxml/jackson/databind/JsonNode.html)
  is a tree

```java
JsonNode node = objectMapper.readTree(new File("resources/tasks.json"));
for (JsonNode task : node.get("tasks")) {
    Task t = new Task(
            task.get("description").asText(),
            LocalDate.parse(task.get("deadline").asText()));
    tasks.add(t);
}
```

---

## Java Collections Framework

<img src="collections.png"/>

*Thanks to Albert Lionelle!*

---

## Some notes

- `Set`: A collection that contains no duplicate elements.
- `HashSet`: `Set` interface backed by `HashMap`; no guarantees on order
- `TreeSet`: guaranteed log(n) time cost for the basic operations (add, remove and contains).
- `TreeMap`: sorted according to natural ordering of keys; guaranteed log(n) time cost for the containsKey, get, put and remove operations

---

## Design Exercise - 1

- Consider the Library example
- Assume a method to get all items sorted by ID
- Which option is best?
  * Manually insert new items in sorted order
  * When the method is called, sort the list
  * Use a TreeSet and sort by ID

