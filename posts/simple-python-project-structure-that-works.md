# Simple Python Project Structure That Works

In order to create a good and scalable project we also need a good scalable structure. This simple structure will make your projects easier to maintain and grow.

```graphql
./src - # your project root folder
  ├─ /assets - # media files
  ├─ /components - # frontend componenets
  ├─ /functions/ - # internal logic code
  │  └─ /libs - # dont forget to organize your code!
  ├─ //utils/ - # external logic code
  │  └─ /repository - # connects and deals with database
  ├─ //models - # data structure
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

You should have all your internal business logic contained in your functions folder. In other words we can not use any external API or service on this code, rathar we should import another code that will do it for us.

In order to do it the best way you should also import respecting the SOLID `dependency inversion principle`.

## External code

So the code that will use external services should be located in the `utils` folder.

There is one folder/file that is also standardized (in my structure). The `repository`.

It is the code that will handle the interface between python your database.

## Models and Assets

Models is only usefull if you are running (and I recomend) any type of data validation. I personally use the marshmallow library.

Models for the validatios should be stored in the models folder.

Finally assets is the folder to save all sorts of media files such as pictures, videos and csv files.