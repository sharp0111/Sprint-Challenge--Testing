# Assessing your Testing Fu

* Keep Calm! Test On!
* Now that you're familiar with the concepts of testing, your goal is to write documentation and tests for an API that is already in production. (This happens a lot :))
* Answers to your written questions will be recorded in _ANSWERS.md_
* This is to be worked on alone but you can use outside resources. You can _reference_ any old code you may have, and the React Documentation, however, please refrain from copying and pasting any of your answers. Try and understand the question and put your responses in your own words. Be as thorough as possible when explaining something.
* **Just a friendly Reminder** Don't fret or get anxious about this, this is a no-pressure assessment that is only going to help guide you here in the near future. This is NOT a pass/fail situation.

## Start by forking and cloning this repository.

## Questions - Self Study - You can exercise your Google-Fu for this and any other _Sprint Challenge_ in the future.

1. In Mocha, what are the differences between `before`, `after`, `beforeEach`, and `afterEach`? When do they run? What are they used for?
2. What is the point of Test Driven Development? What do you personally think about this approach?
3. What is a `spy` in `sinon`? How do we use it to effectively test a `callback`?

## Initializing Project -

* Fork/Clone this project into a directory on your machine.
* `cd` into your forked local copy.
* notice there is a `package.json` file included. We have included all of the dev-dependencies that you'll need to build your project.
* run `yarn` to download and install all the dependencies you need for this project.
* run `yarn test` to start your tests.
* Keep an active log of your changes by `commiting` with Git and `pushing` often to GitHub.
* Write all of your tests in the `server.test.js` file. This is where you're going to be doing your API mocking/testing.

## Project Description

* You're going to be writing the documentation and the tests for a CRUD API.
* The API itself is really simple. You're task is to peek at the endpoints found in the `server.js` file and write docs for each one, then write the tests for the end points.

## DOCUMENTATION GOES HERE

```
# API Documentation

Provides access to the collection of Games of various Genre.

## Port - Location of all endpoints to interface with our API is at http://localhost:5050/api/

## [GET] `/game/get`
| Endpoint      | Type          | Data  |
| ------------- |:-------------:| -----:|
| /game/get     |    GET        | Array |

### Example:
[
  {
    title: 'California Games',
    genre: 'Sports',
    date: 'June 1987'
  },
  {
    title: 'World of Warcraft',
    genre: 'Strategy',
    date: November, 2004
  }
]

## [POST] `/game/create`
| Endpoint         | Type          | Data  |
| ---------------- |:-------------:| -----:|
|   /game/create   |      POST     |  json |

### Example:
{
  title: 'California Games',
  genre: 'Sports',
  date: 'June 1987'
}

## PUT Route
| Endpoint         | Type    | Data  |
| ---------------- |:-------:| -----:|
| /game/update     |   PUT   |  json |

### Example:
{
  id: '12345',
  title: 'California Games',
}

## DELETE Route
| Endpoint          | Type   | Data  |
| ----------------- |:------:| -----:|
| /game/destroy/:id | DELETE |  json |

### Example:
  {
    id: '12345',
  }
```

## TESTS

* I have already manually tested this API for you.
* All you have to do is write Unit tests to ensure that the end points do what they're supposed to do.
* THERE IS NO NEED TO `YARN START`, BUT YOU'LL WANT TO ENSURE THAT YOU HAVE A `MONGO` INSTANCE UP AND RUNNING.

### Write a test for the "POST" method

* The `POST` method should take in an object that looks like this

```js
{
  title: 'California Games',
  genre: 'Sports',
  date: 'June 1987'
}
```

### Write a test for the "GET" method

* Our get method should return the list of games.
* **REMINDER** That this data structure returned from Mongo will be an array, so to test your game with a `beforeEach` hook you'll need to make sure you test against the first item in the array

```js
expect(res.data[0].foo).to.equal(bar.foo);
```

* Write your `PUT` and your `DELETE`

### Write a test for the "PUT" method

* Just like in class, send up the information you want changed on the server via the `req.body`.
* You can send up the Id and the Server will be using that to

## Stretch Problem

### Write a test for the "DELETE" method

* `DELETE` can take an ID off of the route parameter, or off of the req.body. It's your choice.

### Remember you can use any resources you want to solve these problems, but avoid copying/pasting solutions you've previously written. Also if you don't finish all of the challenges, that's fine! Just do what you can and submit your challenges in the end! HAVE FUN!
