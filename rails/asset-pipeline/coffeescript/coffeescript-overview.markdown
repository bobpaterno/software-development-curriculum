# CoffeeScript Overview

## Introduction to CoffeScript
CoffeeScript is a programming language that compiles down to JavaScript. It can be considered as an attempt to expose the good parts of JavaScript in a simple way,
and is essentially just a syntactic rewrite of JavaScript. The core language itself stays the same, with small semantic enhancements. The syntax is modified, modeled after
Python and Ruby and implements many features from those two languages. The CoffeeScript compiler outputs clean JavaScript that follows best practices and is eminently readable; it also allows you to use any existing JavaScript library seamlessly from CoffeeScript (and vice-versa).
The compiled output is readable and pretty-printed, will work in every JavaScript runtime, and tends to run as fast or faster than the equivalent handwritten JavaScript.

#### The main benefits of using Coffeescript instead of Javascript are:
* You can use less code to solve the same problem
* The code may be more readable
* The code may be easier to maintain


## Syntax

#### Assignments
**CoffeeScript**
```javascript
str = "hello"
number = 1 
opposite = true
```
**Javascript**
```javascript
var str = "hello";
var number = 1; 
var opposite = true;
```

#### Conditions
**CoffeeScript**
```javascript
number = -42 if opposite
```
**Javascript**
```javascript
if (opposite) { 
  number = -42; 
} 
```

#### Functions
* Functions are denoted with **->**
* Parameters are defined before the function **(x) ->**
* Parameters can also be set with default values **(x=2) ->**
**CoffeeScript**
```javascript
square = (x) -> x * x
```
**Javascript**
```javascript
function square(x) { 
  return x * x; 
}; 
```

#### Arrays
**CoffeeScript**
```javascript
stuff = [1, 2, 3, 4, 5]
```
**Javascript**
```javascript
var stuff = [1, 2, 3, 4, 5];
```

#### Indention
Because brackets are not required scope is dictated by indention.
**CoffeeScript**
```javascript
stuff = [1, 2, 3, 4, 5]
```
**Javascript**
```javascript
var stuff = [1, 2, 3, 4, 5];
```

## Installation

Since Rails 3.1 Coffee-Rails is included in the default Gemfile when you create a new application. If you are upgrading to Rails 3.1 you must add the coffee-rails to your Gemfile:

    gem 'coffee-rails'

## Further Reading

* [RailsCasts CoffeeScript Tutorial](http://railscasts.com/episodes/267-coffeescript-basics)
* [Tutsplus CoffeeScript Tutorial](http://code.tutsplus.com/tutorials/rocking-out-with-coffeescript--net-17027)

## Sources

* [Official Coffeesript website](http://coffeescript.org/)
* [CoffeeScript-Wikipedia](http://en.wikipedia.org/wiki/CoffeeScript)
* [Six Revisions](http://sixrevisions.com/javascript/coffeescript-basics/)
* [CoffeeScript and Asset Pipeline](http://guides.rubyonrails.org/asset_pipeline.html)
