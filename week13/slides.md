# Welcome to CS 5004

*Credit to Mark Miller for much of the content presented in this course!*

---

## Week 13

- [Design Patterns](https://refactoring.guru/design-patterns)
  * ~~Decorator~~
  * Web APIs
  * Testing

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

---

## Announcements

- Office hours by appointment only
  * Shorter hours today
- Complete Project 4 resubmissions by Friday

---

## Testing Pyramid

<img
src="https://ctf-cci-com.imgix.net/5yK8Y4Xyw9UrFKrwofhpRY/93abeed26295d8be191b53da9bf62ca5/article-image-2.png?ixlib=rb-3.2.1&auto=format&fit=max&q=75&dpr=1&w=750"/>

---

## Unit Testing

- Test one part of the application in isolation
- Ex. a single class or method
- No side effects or dependencies
  * Don't need to use file system/network
  * Don't need to determine whether some other thing happened as a result
- *Mocking* may be used if some dependencies exist

---

## Integration Testing

- Test how parts of the application work together
- Fewer in number than unit tests
- Run less frequently

---

## End-to-end Testing

- Testing the application as the user would experience it
- Run at significant milestones

---

## Open/closed-box Tests

- Open: the tester knows all of the internal workings of the code
- Closed: the tester doesn't need to know about the code

---

## Test Doubles

- A "[pretend object used in place of a real object for testing purposes](https://martinfowler.com/articles/mocksArentStubs.html)"
- Stubs: provide canned answers to calls made during the test
- Mocks: simulate the behavior of a complex component
- Use when the code has external dependencies
  * Database access, system calls, network calls

---

## System.in

- Using a stub to simulate `System.in` behavior
  * `testGetLocation`
  * `getGoAgain`?
