# Welcome to CS 5004

*Credit to Mark Miller for much of the content presented in this course!*

---

## Week 11

- [Design Patterns](https://refactoring.guru/design-patterns)
  * ~~Iterator~~
  * ~~Builder~~
  * Decorator
  * Web APIs

---

## Decorator: Example

- Notifier: SMS, Facebook, Slack
- How do you enable many combos?
- Also, java.io library!

*From [Refactoring Guru](https://refactoring.guru/design-patterns/decorator)*

---

## Decorator

- Structural design pattern
- *Wraps* an object to add new behaviors
- An alternative to inheritance
- Consider adding new menu functionality
   * Could use inheritance or a decorator
- Example: Menu class

---

## Web Architecture Overview

<img src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*3E4w7rCe3eaz6gLlZoe6nQ.png"/>

---

## Web Architecture Overview

- The client connects to the server using HTTP.
- The server connects to a database to read/write data.
- The server replies to the client using HTML or similar format.
- The browser displays the result.
- A website is designed to be consumed by a human.

---

## APIs

<img
src="https://raw.githubusercontent.com/Codecademy/articles/0b631b51723fbb3cc652ef5f009082aa71916e63/images/rest_api.svg"/>

---

## APIs

- Consumed by a machine, not a human.
- The server will return JSON (or similar machine-readable format).
- Another developer can write an application to integrate with the service!

---

## REST

- REpresentational State Transfer
- A pattern for building web APIs
- Components of the application are *resources*
- Resources are addressed with the URL
- HTTP request types
  * GET - fetch a resource
  * PUT - update a resource
  * POST - create a resource
  * DELETE - remove a resource

---

## Fitness Tracker API?

---

## Fitness Tracker API?

- /users/{userid}
  * GET returns a user's profile
- /foods/{foodid}
  * GET returns information (e.g., calories) about a particular food
- /users/nutrition?date={date}&userid={userid}
  * differing opinions about parameters

---

## Examples

- [GitHub API](https://docs.github.com/en/rest/quickstart?apiVersion=2022-11-28)
- [AccuWeather](https://developer.accuweather.com/apis)

---

# Building a Forecast App
