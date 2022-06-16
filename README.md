<h1 align="center"> 
<img src ="./images/logo.png" alt ="logo"    width=150 height=150/>
</h1>
<h1 align="center">Test End-to-End</h1>
<p align="center">How to create test end-to-end with Prisma and Node.JS</p>
<p align="center">
  <a href="#-introduction">Introduction</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-project">Project</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-how-to-run">How to run</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-license">License</a>
</p>

## ✨ Introduction

Testing an application it is an important step to ensure the quality of your software as well how to measure the behavior of our system in certain situation.

However, test in software a divide in as follows

- Unit: Test how a component/functionality work in **isolation**
- Integration: Test how one or more components/features work together
- E2E: Simulates what a user will do in our application

### Databases

- Unit: Not
- Integration: Perhaps
- E2E = Yes( not only database, any external connection includes api)

---
### Example

For this purpose, we can take an example of an E-commerce and see how behavior;

For example

1. Register a user
2. Register the address in the database
3. Starts the communications with **payment gateway** to send a transaction

Unit: Does not have a database and an Gateway API
E2E: It not advisable using mocks or fake data

Payment Gateway: Account of the test (API test Key)

> For example, we can take as a Payment Gateway, we can cite [Stripe](https://stripe.com)
---
## :gear: Techs 
- [Typescript]()
- [Prisma]()
- [Express]()
- [Jest]()
- [Supertest]()

---

## 💻 Project
The main purpose of this project is educational, so we will not go deep down in pattern or clean code. However, some of the concepts will be used in this project.

Now, the project is design to be a platform to register a lesson with a description (optional field), since we are constructing an API it is only for learning purposes there is no need to develop further functionalities.

The only functionality here is created lesson, so our tests are centered around this functionality. Therefore, let's start.


### Unit Tests

We have spoken about this test in the introduction, but let make a further description.
> A Unit Test is a test, usually automated, that tests a single unit of the application, usually a single functions, in a single context.

To create this test we will follow some rules, first this test we will not create an register in the bank. This rule it is cited by Martin Fowler and you can see [here](https://martinfowler.com/bliki/InMemoryTestDatabase.html). 
Then we create the repository called `InMemoryLessonsRepository.ts`, inside this script we push the data about Lesson to test in memory and when test ends the data is deleted from the memory

The rules tested in this functionally was
- Create a Lesson
- Should NOT be able to create a new lesson with invalid title

> IMPORTANT: We not crate a register in our database.

### A End-2-End test(e2e)

A e2e testing is a technique that tests the entire software product from beginning to end to ensure the application flow behaves as expected. It defines the product's system dependencies and ensures all integrated pieces work together as expected.

The tests implement here are
1. Create a lesson in the database
2. Create a lesson in the database and check if the number of lessons in the database is equal to 1

However, an end-to-end test is tricky, because:
- The tests should not interfere with each other
- It is not allowed to use the dev database(you should use a test database)

Therefore, we will create a new environment to perform our e2e. There is a script on the `prisma` folder, where we create these requirements. And, we create a new jest configuration file called `jest-e2e.config.ts`, please take a look.

At last, with these requirements completed, we can start to write our test in the `app.e2e-spec.ts`. Here we put all rules need to start to write.

---
## :rocket: How to run

To run the this project 

- Clone the repo and access the directory;
- Use the `npm` or `yarn` to install the dependencies;
- Run the migrations with `npx prisma migrate dev` or `yarn prisma migrate dev`;
- Init the unitary test is `npm run test` and e2e test `npm run test:e2e`

> This project using an Postgres as default database.


---
## 📄 License
The projects is under the MIT license. See the file [LICENSE](LICENSE) fore more details

---

Made with ♥ by Rafael and [Rocketeseat](https://youtu.be/w_el04y0cHo])👋 


[![Linkedin Badge](https://img.shields.io/badge/-Rafael-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/tgmarinho/)](https://www.linkedin.com/in/rafael-mgr/)
[![Gmail Badge](https://img.shields.io/badge/-Gmail-red?style=flat-square&link=mailto:nelsonsantosaraujo@hotmail.com)](mailto:ribeirorafaelmatehus@gmail.com)
