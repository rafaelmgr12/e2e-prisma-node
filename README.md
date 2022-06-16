<h1 align="center"> 
<img src ="./images/logo.png" alt ="logo"    width=150 height=150/>
</h1>
<h1 align="center">Test End-to-End</h1>
<p align="center">How to create test end-to-end with Prisma and Node.JS</p>

## Introduction

Testing an application it is an important step to ensure the quality of you software as well how to measure the behavior of our system in certain situation.

However, test in software a divide in as follow

- Unit: Test how a component/functionality work in **isolation**
- Integration: Test how one or more components/features work together
- E2E: Simulates what a user will do in our application

## Databases

- Unit: Not
- Integration: Perhaps
- E2E = Yes( not only database, any external connection includes api)

## Example

For this purpose we can take an example of a E-commerce and see how it behavior;

For example

1. Register an user
2. Register the address in the database
3. Starts the communications with **payment gateway** to send a transaction

Unit: Does not have a database and an Gateway API
E2E: It not advisable using mocks or fake data

Payment Gateway: Account of the test (API test Key)

> For example we can take as an Payment Gateway, we can cite [Stripe](https://stripe.com)

