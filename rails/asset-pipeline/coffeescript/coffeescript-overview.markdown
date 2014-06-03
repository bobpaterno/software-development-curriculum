# CoffeeScript Overview

## Introduction to CoffeScript
CoffeeScript is a programming language that compiles down to JavaScript. It can be considered as an attempt to expose the good parts of JavaScript in a simple way,
and is essentially just a syntactic rewrite of JavaScript. The core language itself stays the same, with small semantic enhancements. The syntax is modified, modeled after
Python and Ruby and implements many features from those two languages. The CoffeeScript compiler outputs clean JavaScript that follows best practices and is eminently readable; it also allows you to use any existing JavaScript library seamlessly from CoffeeScript (and vice-versa).
The compiled output is readable and pretty-printed, will work in every JavaScript runtime, and tends to run as fast or faster than the equivalent handwritten JavaScript.

## Comparing CoffeeScript to Javascript
### Assignments

**Javascript**
```javascript
var str = "hello";
var number = 1; 
var opposite = true;
```
*CoffeeScript*
```javascript
str = "hello"
number = 1 
opposite = true
```
### Conditions

####Javascript
```javascript
if (opposite) { 
  number = -42; 
} 
```
####CoffeeScript
```javascript
number = -42 if opposite
```
### Functions

####Javascript
```javascript
function square(x) { 
  return x * x; 
}; 
```
####CoffeeScript
```javascript
square = (x) -> x * x
```
###Arrays

####Javascript
```javascript
var stuff = [1, 2, 3, 4, 5];
```
####CoffeeScript
```javascript
stuff = [1, 2, 3, 4, 5]
```
## Installation

Since Rails 3.1 Coffee-Rails is included in the default Gemfile when you create a new application. If you are upgrading to Rails 3.1 you must add the coffee-rails to your Gemfile:

    gem 'coffee-rails'

## Further Reading

* [RailsCasts CoffeeScript Tutorial](http://railscasts.com/episodes/267-coffeescript-basics)
* [Tutsplus CoffeeScript Tutorial](http://code.tutsplus.com/tutorials/rocking-out-with-coffeescript--net-17027)

## Sources

* 1
* 2
* 3
* 4
