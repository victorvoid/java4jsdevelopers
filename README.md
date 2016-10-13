# JS for Java Developers

- [JavaScript and Java](#javascript-and-java)
- [Comments](#comments)
- [Declarations](#declarations)
  - [Data type conversion](#data-type-conversion)
- [Literals](#literals)
  - [Array literals](#array-literals)
  - [String literals](#string-literals)
- [Loops](#loops)
  - [For/in](#for-in)
- [Methods](#methods)
  - [Defining and Calling methods](#defining-and-calling-methods)
- [Classes](#classes)
  - [Class declarations](#class-declarations)
  - [Constructor](#constructor)
  - [Getters and Setters](#getters-and-setters)
  - [Inheritance](#inheritance)

JavaScript and Java
-----------------

JavaScript and Java are similar in some ways but fundamentally different in some others. The JavaScript language resembles Java but does not have Java's static typing and strong type checking. JavaScript follows most Java expression syntax, naming conventions and basic control-flow constructs which was the reason why it was renamed from LiveScript to JavaScript.

In contrast to Java's compile-time system of classes built by declarations, JavaScript supports a runtime system based on a small number of data types representing numeric, Boolean, and string values. JavaScript has a prototype-based object model instead of the more common class-based object model. The prototype-based model provides dynamic inheritance; that is, what is inherited can vary for individual objects. JavaScript also supports functions without any special declarative requirements. Functions can be properties of objects, executing as loosely typed methods.

JavaScript is a very free-form language compared to Java. You do not have to declare all variables, classes, and methods. You do not have to be concerned with whether methods are public, private, or protected, and you do not have to implement interfaces. Variables, parameters, and function return types are not explicitly typed.

Java is a class-based programming language designed for fast execution and type safety. Type safety means, for instance, that you can't cast a Java integer into an object reference or access private memory by corrupting Java bytecodes. Java's class-based model means that programs consist exclusively of classes and their methods. Java's class inheritance and strong typing generally require tightly coupled object hierarchies. These requirements make Java programming more complex than JavaScript programming.

In contrast, JavaScript descends in spirit from a line of smaller, dynamically typed languages such as HyperTalk and dBASE. These scripting languages offer programming tools to a much wider audience because of their easier syntax, specialized built-in functionality, and minimal requirements for object creation.

From [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Introduction#JavaScript_and_Java)

Comments
--------

ES5/6/Java
```js
// a one line comment
 
/* this is a longer, 
   multi-line comment
 */
 
/* You can't, however, /* nest comments */ SyntaxError */
```

Declarations
------------

ES5/6 - There are three kinds of declarations in JavaScript.

``var`` - Declares a variable, optionally initializing it to a value.

``let`` - Declares a block scope local variable, optionally initializing it to a value.

``const`` - Declares a read-only named constant.

Java - All variables must have a type. You can use primitive types such as int, float, boolean, etc. Or you can use reference types, such as strings, arrays, or objects.

ES5
```js

var name = "Paul",
    age  = 19;

```

ES6
```js

let name = "Paul",
    age  = 19;

```

Java
```java

String name = "Paul";
int age = 19;

```

Data type conversion
--------------------

ES5
```js

var name = "Paul"
name = 19;
//Because JavaScript is dynamically typed, this assignment does not cause an error message.
```
Java
```java

String name = "Paul";
name = 12;

//error: incompatible types: int cannot be converted to String
```

ES5

```js

console.log("19" - 9); 
//10
```

Java
```java
System.out.println("19" - 9);
//error: bad operand types for binary operator '-'
```

## Converting strings to numbers

ES5
```js
  parseInt("15", 10); // 15 -> you want to use radix 10
  parseFloat("3.14"); ////floor automatically converts string to number
```

Java
```java
  System.out.println(Integer.parseInt("12")); //12
  System.out.println(Float.parseFloat("15.87")); //15.87
```

Literals
-------

## Array literals

ES5
```js
  var powersOfTwo = [1, 2, 4, 8, 16, 32, 64, 128];
```
Java
```java
  int[] powersOfTwo = {1, 2, 4, 8, 16, 32, 64, 128};
```
## String literals

ES5
```js
 "Hello!"
```
ES6
```js
// Basic literal string creation
`In JavaScript '\n' is a line-feed.`

// Multiline strings
`In JavaScript this is
 not legal.`

// String interpolation
var name = "Bob", time = "today";
`Hello ${name}, how are you ${time}?` //Hello Bob, how are you today?
```

Java
```java
 "abc" is a literal String. 
  
  String s1 = "Bob"; //A String object is an individual instance of the java.lang.String class. 
```

Loops
------

##For in

ES5
```js
var strArray = ["Victor", "Paul", "Leona"];
for(myStr in strArray){
  console.log(strArray[myStr]);
}

//or

var strArray = ["Victor", "Paul", "Leona"];
for(myStr of strArray){
  console.log(myStr);
}
```

Java
```java
String[] strArray= {"Victor", "Paul", "Leona"};
for (String myStr : strArray) {
  System.out.println(myStr);
}
```

Methods
---------

##Defining and Calling methods
ES5
```js
var Person = (function () {
    function Person(name) {
        this.name = name;
    }
    // Methods
    Person.prototype.doSomething = function () {
        console.log("I'm a " + this.name);
    };
    return Person;
})();

var person1 = new Person("Victor Igor");
person1.doSomething();
```

Java
```java
class Person{
  String name;
  void doSomething(){
    System.out.println("I'm a " + this.name;)
  }
}
```

Classes
--------

##Class declarations

ES5

```js
function Person(){
  // field, constructor, and 
  // method declarations
}
```

ES6
```js
class Person {
  // field, constructor, and 
  // method declarations
}
```

Java
```java
class Person {
  // field, constructor, and 
  // method declarations
}
```

##Constructor

ES5
```js
function Person(name, age) {
  this.name = name;
  this.age = age;
}
var person = new Person("Victor Igor", 80); //instance
console.log(person.name, person.age);    
```

ES6
```js
class Person {
  constructor(name, age){
    this.name = name;
    this.age  = age;
  }
}
let person = new Person("Victor Igor", 80);
```

Java
```java
class Person {
  String name;
  int age;
  Person(String name, int age){
    this.name = name;
    this.age  = age;
  }
}
```

##Getters and Setters

ES5
```js
function Person (name, age) {
  var _name = name;
  var _age = age;
  this.setName = function(name) {
    _name = name;
  }
  this.getName = function() {
      return _name;
  }
  this.setAge = function(age){
    _age = age;
  }
  this.getAge = function(){
    return _age;
  }
  
}

//instantiate the Person class with some arguments
var person1 = new Person("Victor Igor1", 80);
console.log("Name: ", person1.getName() + " Age: " + person1.getAge());
```

ES6
```js
class Person {
  constructor(name, age) {
    // Check that (name, age) is a valid date
    
    // If it is, use it to initialize "this" date's ordinary variables
    this._name = name;
    this._age = age;
  }
  set name(name){
     this._name = name;
  }

  get name() {
    return this._name;
  }

  set age(age){
     this._age = age;
  }

  get age(){
    return this._age;
  }
}
let person1 = new Person("Victor Igor", 20);
console.log(person1.name);
```

Java
```java
class Person {
  private String name;
  private int age;
  public Person(String name, int age){
    this.name = name;
    this.age  = age;
  }
  
  public String getName(){
    return this.name;
  }
  
  public void setName(name){
    this.name = name;
  }
  
  public String setAge(age){
    this.age = age;
  }
  
  public void getAge(age){
    this.age = age;
  }
}
```
