# Simple Python Project Structure That Works

In order to create a good and scalable project we also need a good scalable structure. This simple structure will make your projects easier to maintain and grow.

```graphql
./src/* 
  ├─ src/assets - media files
  ├─ src/components - frontend componenets
  ├─ src/functions/* - internal logic code
  │  └─ /libs - dont forget to organize your code!
  ├─ src//utils/* - external logic code
  │  └─ /repository - connects and deals with database
  ├─ src//models - data structure
  .
  .
  .
  └─ scripts!
```

## How does it work?

It strongly takes into SOLID coding principles and the MVC model.

<details>
<summary>SOLID/ MVC</summary>

### SOLID
**S**ingle-Responsibility Principle

**O**pen-Closed Principle

**L**iskov Substitution Principle

**I**nterface Segregation Principle

**D**ependency inversion Principle

<sup>If you would like to learn more about SOLID principles applied in python please read my post on this!</sup>

### MVC

- Model defines the data structure
- View defines what will be shown to the UI
- Controller contains the business logic

<sup>I sould also have a post about MVC as well!</sup>

</details>

## Script vc Functions

First lets get something clear.

Scripts are ment to be run while functions/libs are ment to be imported so your scripts must **always** be in the root folder of your project

## Functions and Components

Functions and components are the main folder of your code, these represent (for the most part) the controller and view (from MVC).

You should have all your internal business logic contained in your functions folder. And by internal I mean that it does not depend on anything else other than it self

