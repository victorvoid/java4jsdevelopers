# Java for JS Developers

- [JavaScript and Java](#javascript-and-java)
- [Comments](#comments)
- [Declarations](#declarations)
  - [Data type conversion](#data-type-conversion)
- [Literals](#literals)
  - [Array literals](#array-literals)
  - [String literals](#string-literals)
- [Loops](#loops)
  - [For/in](#for-in)
- [Functions](#functions)
  - [Defining functions and Calling functions](#defining-functions-and-calling-functions)
- [Classes](#classes)

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
//"19" - 9 = 10
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

Functions
---------

##Defining functions and Calling functions
ES5
```js
function aow() {
  console.log("aow js");
}
aow();
```

Java
```java
  static void aow(){
    System.out.println("aow java");
  }
  aow(); //in main
```

Classes
--------

##Class declarations

ES5

```js
var person = function(){

}
```

ES6
```js
class Person {

}
```

Java
```java
