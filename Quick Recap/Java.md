
# Java Identifiers

In **Java**, an **identifier** is the **name you give to a program element** so Java can identify it.

### Examples of identifiers

- Variable names → `count`, `totalPrice`
- Method names → `calculateSum()`, `printDetails()`
- Class names → `Student`, `BankAccount`
- Interface names → `Runnable`
- Package names → `com.example.app`

## ****Rules For Naming Java Identifiers****

-### Rules for Naming Identifiers in Java

1. An identifier can contain **letters (A–Z, a–z), digits (0–9), underscore (_), and <mark style="background: #FF5582A6;">dollar sign ($)</mark>**.
2. An identifier **must begin with a letter, underscore (_), or <mark style="background: #FF5582A6;">dollar sign ($)</mark>**.
3. An identifier **<mark style="background: #FF5582A6;">cannot start with a digit</mark>**.
4. **No spaces** are allowed in an identifier.
5. **Special characters** like `@`, `#`, `%`, `-` are **not allowed**.
6. An identifier **must not be a Java keyword** (e.g., `int`, `class`, `public`).
7. Identifiers are **case-sensitive** (`sum` and `Sum` are different).
8. An identifier can be of **any length**.

![[data_types_in_java.webp]]

## Class

A class is a user-defined blueprint that defines variables and methods. It represents a type of object and forms the foundation of Object-Oriented Programming.

```java
class Car {
    String model;
    int year;

    Car(String model, int year) {
        this.model = model;
        this.year = year;
    }

    void display() {
        System.out.println(model + " " + year);
    }
}

public class Geeks {
    public static void main(String[] args) {
        Car myCar = new Car("Toyota", 2020);
        myCar.display(); 
    }
}
```



[[Drawing 2026-01-25 07.55.37.excalidraw]]

<mark style="background: #ABF7F7A6;">final keyword </mark> --> 
```java
final int MINUTES_PER_HOUR = 60;
```

---
## Java basic program

```java
public class Main{
    public static void main(String [] args)
    {
        int number = 22;
        System.out.println(number);
    }
}
```

```java
variable = (condition) ? expressionTrue :  expressionFalse;
```

---
## AND  OR  NOT

- `&&` (AND) - all conditions must be true
- `||` (OR) - at least one condition must be true
- `!` (NOT) - reverses a condition (true = false, false = true)

---
## Java Switch Statements

```java
public class Main {

    public static void main(String[] args) {
        int day = 2;
        switch (day) {
            case 1:
                System.out.print("monday");
                break;
            case 2:
                System.out.println("tuesday");
                break;
            case 3:
                System.out.println("Wenesday");
                break;
            default:
                System.out.println("Sorry you have entered the wrong input");
                break;
        }
    }
}
```

The main differences between **primitive** and **non-primitive** data types are:

## The var Keyword 

The `var` keyword lets the compiler <mark style="background: #ABF7F7A6;"> automatically detect the type of a variable based on the value you assign to it </mark>.

```java
var myNum = 5;         // int
var myDouble = 9.98;   // double
var myChar = 'D';      // char
var myBoolean = true;  // boolean
var myString = "Hello"; // String
```

```java
var x; // Error  
var x = 5;  // OK
```


while using var datatype we should be always assigned to the varibale 

---
## Narrowing Casting

```java
public class Main {
  
    public static void main(String [] args)
    {
        int a = 65;
        char b = (char) a;
        System.out.print(b);
    }
}
```

what happens here is a will has a number 65 when it gets converted into a character it will make it into a ASCII and try to map it to character in keyboard ie the Unicode

<mark style="background: #ABF7F7A6;">Because Unicode </mark>`65` = `'A'`.

<mark style="background: #ABF7F7A6;">how to type cast</mark> `char b = (char) a;`

```java
public class Main {

    public static void main(String[] args) {
        int a = 2000;
        String b = (String) a;
        System.out.println(b);
    }
}
```

👆 this wont work bic

- `a` is an `int` (a <mark style="background: #ABF7F7A6;">primitive type</mark>).
    
- `String` is a <mark style="background: #ABF7F7A6;">reference type</mark>.
    
- <mark style="background: #ABF7F7A6;">Java does not allow casting between primitives and unrelated reference types</mark>.

```java
int a = 2000;
String b = Integer.toString(a);
System.out.println(b);
```

---

| Operator | Name      | Description                            | Example |
| -------- | --------- | -------------------------------------- | ------- |
| ++       | Increment | Increases the value of a variable by 1 | ++x     |
| --       | Decrement | Decreases the value of a variable by 1 | --x     |


## Order of Operations

From highest to lowest priority:

- `()` - Parentheses
- `*`, `/`, `%` - Multiplication, Division, Modulus
- `+`, `-` - Addition, Subtraction
- `>`, `<`, `>=`, `<=` - Comparison
- `==`, `!=` - Equality
- `&&` - Logical AND
- `||` - Logical OR
- `=` - Assignment

---
## Java Strings

```java
public class Main {
    public static void main(String[] args) {
        String name = "akshay";
        System.out.println("the length of name is :"+ name.length());
    }
}
```

## toUpperCase

```java
System.out.println("To upper case :"+ name.toUpperCase());
System.out.println("To lower case :"+ name.toLowerCase());
```

## indexOf

```java
        System.out.println(name.indexOf("akshay"));
```

```output
11
```

---

| Code | Result          |
| ---- | --------------- |
| \n   | New Line        |
| \t   | Tab             |
| \b   | Backspace       |
| \r   | Carriage Return |
| \f   | Form Feed       |

---
## Java While Loop

```java
public class Main {

    public static void main(String [] args)
    {
        int i = 3;
        while (i > 0) {
            System.out.println("apple");
            i --;
        }
    }
}
```

## Java For Loop

```java

for (int i = 0; i < 5; i++) {  System.out.println(i);}

```

---

## Java Arrays

```java
String[] cars;
String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
```


```java
public class Main {

    public static void main(String[] args) {
       int [] mynum = {10,20,30,10};
       for(int i= 0;i < mynum.length; i++)
        System.out.println(mynum[i]);
    }
}
```


` mynum.length`  --> used for getting the <mark style="background: #ABF7F7A6;">length of the array</mark>


### Loop Through an Array with For-Each


```java
String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};

for (String c : cars) {
  System.out.println(c);
}
```


In Java, the enhanced `for-each` loop <mark style="background: #ABF7F7A6;">works only with arrays or Iterable objects</mark>.

ie: 
```java
public class Main {

    public static void main(String[] args) {
        String name = "apple";
        for(char i : name)
        System.out.println(i);
    }
}
```

<mark style="background: #FF5582A6;">this wont work</mark> 👆

```java
public class Main {
    public static void main(String[] args) {
        String name = "apple";
        for (char i : name.toCharArray()) {
            System.out.println(i);
        }
    }
}
```

`for (char i : name.toCharArray()) {`  --> <mark style="background: #ABF7F7A6;"> toCharArray </mark>


usage of for each in multi dimensional array

```java
String[][] cars = {
    {"Volvo", "BMW"},
    {"Ford", "Mazda"},
    {"Tesla", "Audi"}
};

for (String[] row : cars) {        // each row is a 1-D array
    for (String c : row) {         // each element in that row
        System.out.println(c);
    }
}

```

```output
Volvo
BMW
Ford
Mazda
Tesla
Audi
```

---
# Java Methods

```java
public class Main {
    static void mymethord(){
        System.out.println("apple");
    }
    public static void main(String[] args) {
        mymethord();
        mymethord();
        mymethord();

    }
}
```


## Parameters and Arguments

```java
public class Main {
  static void myMethod(String fname) {
    System.out.println(fname + " Refsnes");
  }

  public static void main(String[] args) {
    myMethod("Liam");
    myMethod("Jenny");
    myMethod("Anja");
  }
}
```


👇 my trial

```java
public class Main {
    static void myCall(String aple)
    {
        System.out.println(aple + " is a good boy");
    }
    public static void main(String[] args) {
        myCall("akshay");
    }
}
```

we can also use multiple parameters `static void myMethod(String fname, int age) {`

Function with return int

```java
public class Main {
    static int myMethord(int number){
        if(number == 10){
            return 1;
        }
        return 0;
    }
    public static void main(String[] args) {
        System.out.println(myMethord(10));
    }
}
```



```java
public class Operation{
    public static void main(String[] args) {
        int x = 10;
        int y = 20;
        System.out.println(x > y); //false
        System.out.println(y < x); //False
        System.out.println(x != y); //True
    }
}
```

```java
public class apple{
    public static void main(String[] args) {
        int age = 20;
        int age1 = 30;
        boolean hasId = true;
        System.out.println(age >= 18 && hasId && age <= age1); //true
        System.out.println(age <= 18 || hasId); //true
        System.out.println(!hasId); //false
    }
}
```

in case of java Boolean value cannot take in the value of o or null it only takes the value as <mark style="background: #ADCCFFA6;">true</mark> or <mark style="background: #ADCCFFA6;">false</mark>


```java
public class IfStatement{
    public static void main(String[] args) {
        int age = 8;
        if(age >= 18){
            System.out.println("able to vote");
        }
        else{
            System.out.println("not able to vote");
        }
  
    }
}
```

---
---
---


---

---

---



# java practice questions basic

https://www.geeksforgeeks.org/java/java-programming-examples/

[[java practice questions]]

| String b = Integer.toString(a); |                                         |
| ------------------------------- | --------------------------------------- |
| char b = (char) a;              |                                         |
| name.length();              --> | to get lngth of string                  |
| animals.length              --> | to get length of array                  |
| name.toUpperCase();             |                                         |
| indexOf("akshay")         -->   | this is used for sentence not for array |
| name.toCharArray()      -->     | get charecters from string              |
```java
public class loops {

  

    public static void main(String[] args) {

        int number = 1234;

        String b = Integer.toString(number);

        System.out.println(b.length());

    }

}
```

<mark style="background: #FFB8EBA6;">reverse a number in java</mark>

```java
while(num!= 0)
{

}
```


```java
*
**
***
****
*****
```

`for(;i<=5;i++)` --> is it correct for a loop

## Methods

```java
public class Attendance {

    static void Happy(){
        System.out.println("Hello java");
    }
    public static void main(String[] args) {
        System.out.println("good morning");
        Happy();
    }
}
```

2 types of argument actual argument and formal argument

what is actual argument and formal argument and which one will call witch

what is static or non static methord

```java
public class Addition{
    int add(int x,int y){
        return x+ y;
    }
    static int add1(int x , int y){
        return x+y;
    }
}
```

default constructor

constructor will be called by the instructor

constructor overloading

```java
public class Employee{

    private int id;

    private String name;

    private float salary;

  

    public Employee(){

        System.out.println("Default Constructor");

    }

  

    public Employee(int id, String name, float salary){

        this.id = id;

        this.name = name;

        this.salary = salary;

  

    }

    void display(){

        System.out.println("id="+id + "Name = "+ name+ "salary ="+ salary);

    }

}
```


even though we are calling a default constructor the the variables will be assigned with default value

ie Employee emp = new Employee(); this also creating a 

```java
public class Employee{

    private int id;

    private String name;

    private float salary;

  

    public Employee(){

        System.out.println("Default Constructor");

    }

  

    public Employee(int id, String name, float salary){

        this.id = id;

        this.name = name;

        this.salary = salary;

  

    }

    void display(){

        System.out.println("id="+id + "Name = "+ name+ "salary ="+ salary);

    }

}
```



```java
public class Manager{

    public static void main(String[] args) {

        Employee emp = new Employee();

        Employee emp1 = new Employee(101,"black",3654);

        Employee emp2 = new Employee(102,"black",3654);

        emp.display();

        emp1.display();

        emp2.display();

  

    }

}
```


what is the difference between static and non statc memory alocation 
static will have the shared copy of all object
and static variable wont get initialised through the constructor
class loading is happening first or object loading ?


```java
class Calculator {

    int add(int a, int b) {   // non-static method
        return a + b;
    }
}

public class TestNonStatic {
    public static void main(String[] args) {
        Calculator calc = new Calculator();  // object required
        int result = calc.add(10, 20);
        System.out.println("Sum = " + result);
    }
}

```

```java
class Calculator {

    static int add(int a, int b) {   // static method
        return a + b;
    }
}

public class TestStatic {
    public static void main(String[] args) {
        int result = Calculator.add(10, 20); // class name
        System.out.println("Sum = " + result);
    }
}

```

<mark style="background: #FF5582A6;">Array Declaration</mark>

```java
Declaration + Creati
int[] numbers = new int[5];
```

In object-oriented programming, properties and methods are both members of an object, but they play different roles:

🧱 Property

What it is: A value or piece of data that belongs to an object

Purpose: Describes the object’s state

Think: Nouns / adjectives

Accessed like: a variable


Example (JavaScript):

car.color      // "red"
car.speed      // 120

Here, color and speed are properties — they store information about the car.


---

⚙️ Method

What it is: A function that belongs to an object

Purpose: Describes the object’s behavior

Think: Verbs / actions

Called like: a function


Example (JavaScript):

car.start()
car.accelerate(10)

Here, start() and accelerate() are methods — they do something.


---

🧠 Simple mental model

Properties = what the object has

Methods = what the object can do


Or:

> Properties are data, methods are behavior.


<mark style="background: #FF5582A6;">used for string comparison</mark>

```java
username.equals("admin")
```

<mark style="background: #FF5582A6;">reverse an array</mark>

```java
(int i = transactions.length - 1; i >= 0; i--)
```

<mark style="background: #FF5582A6;">count the number of digits in  a number</mark>

```java
int num = 12345;
int count = 0;

num = Math.abs(num);

if (num == 0) {
    count = 1;
} else {
    while (num != 0) {
        count++;
        num /= 10;
    }
}

System.out.println("Digits = " + count);

```


<mark style="background: #FF5582A6;">reverse a number </mark>

```java

```


<mark style="background: #FF5582A6;">print right angle triangle</mark>

```java
public class StarPattern {
    public static void main(String[] args) {
        for(int i= 0; i<= 5;i++)
        {
            for(int j = 0; j <= i ;j++)
            {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}
```


<mark style="background: #FF5582A6;">Array search uses break statement to exit from  the loop</mark>

```java
for (int i = 0; i < arr.length; i++) {
            if (arr[i] == key) {
                System.out.println("Element found at index " + i);
                found = true;
                break;
            }
```


- [ ]  Binary Search (Only for Sorted Array)
- [ ]  Sorting Arrays (Most Asked)
- [ ]  Selection Sort (Easy Logic)
- [ ]  **##  Using Java Built-in Sort (REAL WORLD)**
- [ ]  **#  Searching Using Java Built-in Method**

<mark style="background: #D2B3FFA6;">Static method = can be called without creating an object</mark>

### Lock it in 🧠 (final takeaway)

- **static method** → call using class / directly
- **non-static method** → call using **object**

if it is a non static method and we are trying to call a non static function without creating a method we will get an error

```java
public class Calculator {
    void multiply(int m){
        System.out.println(m*5);
    }
    public static void main(String[] args) {
        // Calculator c1 = new Calculator();
        // c1.multiply(2);
        multiply(5);
    }
}
```



## <mark style="background: #ABF7F7A6;">what is the diff bet actual and formal argument</mark>

### First: big picture

When you **define** a method vs when you **use (call)** a method, Java uses two different terms.

---

## 1️⃣ Formal arguments (a.k.a. parameters)

These are written **in the method definition**.

Think of them as **placeholders** — they say _what kind of data_ the method expects.

Example:

```java
void add(int a, int b) {
    System.out.println(a + b);
}
```

Here:

- `int a`
    
- `int b`
    

👉 These are **formal arguments**

They don’t have real values yet — they’re just names waiting for data.

---

## 2️⃣ Actual arguments

These are written **when the method is called**.

They are the **real values** you pass into the method.

Example:

```java
add(5, 3);
```

Here:

- `5`
    
- `3`
    

👉 These are **actual arguments**

---

## 3️⃣ Which one calls which? (Important!)

🧠 **Actual arguments are passed to formal arguments**

So:

- Method call → **actual arguments**
    
- Method definition → **formal arguments**
    

You can remember it like this:

> **Actual values go into formal parameters**

---

## 4️⃣ Match them mentally

```java
add(5, 3);
    ↑  ↑
    |  |
    a  b
```

- `5` goes into `a`
    
- `3` goes into `b`
    

---
---
---

# <mark style="background: #FFB86CA6;">Java Methods</mark>  static void myMethod()

a block of code which only runs when it is called
pass data, known as parameters, into a method.
Methods are used to perform certain actions, and they are also known as **functions**.

<mark style="background: #FFB8EBA6;">how it comes</mark>

<mark style="background: #FF5582A6;">class</mark> --> <mark style="background: #FF5582A6;">method</mark>

```java
public class Main {
  static void myMethod() {
    // code to be executed
  }
}
```

- `static` <mark style="background: #FF5582A6;">means that the method belongs to the Main class and not an object of the Main class</mark>. 
- `void` <mark style="background: #FF5582A6;">means</mark> that this method <mark style="background: #FF5582A6;">does not have a return value</mark>. 

## Call a Method

```java
public class Main {
  static void myMethod() {
    System.out.println("I just got executed!");
  }

  public static void main(String[] args) {
    myMethod();
  }
}
```

<mark style="background: #CACFD9A6;">static void myMethod()</mark>  --> how method is defined <mark style="background: #FF5582A6;"> important </mark>

## Java Method Parameters

```java
public class Main {
  static void myMethod(String fname) {
    System.out.println(fname + " Refsnes");
  }

  public static void main(String[] args) {
    myMethod("Liam");
    myMethod("Jenny");
    myMethod("Anja");
  }
}
```


<mark style="background: #FF5582A6;">When a **parameter** is passed to the method, it is called an **argument**. So, from the example above: `fname` is a **parameter**, while `Liam`, `Jenny` and `Anja` are **arguments**.</mark>

## Java Method Return

```java
public class Main {
  // Method that doubles the number
  static int doubleGame(int x) {
    return x * 2;
  }

  public static void main(String[] args) {
    for (int i = 1; i <= 5; i++) {
      System.out.println("Double of " + i + " is " + doubleGame(i));
    }
  }
}
```

## <mark style="background: #FFB86CA6;">Method Overloading</mark>

<mark style="background: #FFB8EBA6;">multiple methods can have the same name with different parameters:</mark>

```java
int myMethod(int x)
float myMethod(float x)
double myMethod(double x, double y)
```

```java
public class Main{
    static void apple(){
        System.err.println("apple apple");

    static void apple(int m){
        System.out.println("apple apple apple");
    }
  
    public static void main(String[] args) {
        apple();
        apple(5);
    }
}
```

## <mark style="background: #ADCCFFA6;">imp program</mark>

```java
public class Main {
  static int plusMethod(int x, int y) {
    return x + y;
  }
  
  static double plusMethod(double x, double y) {
    return x + y;
  }
  
  public static void main(String[] args) {
    int myNum1 = plusMethod(8, 5);
    double myNum2 = plusMethod(4.3, 6.26);
    System.out.println("int: " + myNum1);
    System.out.println("double: " + myNum2);
  }
}
```

## Java Scope

In Java, variables are only accessible <mark style="background: #D2B3FFA6;">inside the region where they are created</mark>. This is called **scope**.

## Block Scope

```java
public class Main {
  public static void main(String[] args) {

    // Code here CANNOT use x

    { // This is a block

      // Code here CANNOT use x

      int x = 100;

      // Code here CAN use x
      System.out.println(x);

    } // The block ends here

    // Code here CANNOT use x

  }
}
```


# Java OOP # <mark style="background: #FFB8EBA6;">Java OOP</mark> # <mark style="background: #BBFABBA6;">Java OOP</mark>  # <mark style="background: #ADCCFFA6;">Java OOP</mark>

## Java - What are Classes and Objects?



| ==class== | ==objects== |
| --------- | ----------- |
| Fruit     | Apple       |
|           | Banana      |
|           | Mango       |
# IMPORTANT

So, a class is a <mark style="background: #FF5582A6;">template</mark> for objects, and an <mark style="background: #FF5582A6;">object is an instance</mark> of a class.

<mark style="background: #D2B3FFA6;">When the individual objects are created, they inherit all the variables and methods from the class.</mark>


A class should always start with an uppercase first letter, and that the name of the java file should match the class name.

## Create an Object

In Java, an object is created from a class. We have already created the class named `Main`, so now we can use this to create objects.

```java
public class Main{
    static void good(){
        System.out.println("good boy");
    }
    public static void main(String[] args) {
        Main m1 = new Main();
        m1.good();
    }
}
```


## Using Multiple Classes

can also create an object of a class and access it in another class.

Remember that the name of the java file should match the class name.

Main.java

```java
public class Main {
  int x = 5;
}
```

Second.java

```java
class Second {
  public static void main(String[] args) {
    Main myObj = new Main();
    System.out.println(myObj.x);
  }
}
```

## Java Class Attributes

In the previous chapter, we used the term "**variable**" for `x` in the example (as shown below).
In Java,<mark style="background: #FFF3A3A6;"> variables declared inside a class are called "<mark style="background: #FFB8EBA6;">attributes</mark>"</mark>.
<mark style="background: #ABF7F7A6;">attributes are variables that belong to a class</mark>:


```java
public class Main{

    int m = 20;

    public static void main(String[] args) {

        Main m1 = new Main();

        System.out.println(m1.m);

    }

}
```

==so here m is the attribute==

also can modify attribute values

### Attribute Overriding

```java
public class Main{
    int m = 20;
    public static void main(String[] args) {
        Main m1 = new Main();
        System.out.println(m1.m);
        m1.m = 50;
        System.out.println(m1.m);
    }
}
```

this is called <mark style="background: #FF5582A6;">attribute overriding</mark>
if we don't want to do that we can  declare the attribute as <mark style="background: #FF5582A6;">final</mark>

###  Multiple Objects

```java
public class Main{
    int m = 20;
    public static void main(String[] args) {
        Main m1 = new Main();
        Main m2 = new Main();
        System.out.println(m1.m);
        m1.m = 50;
        System.out.println(m1.m);
        System.out.println(m2.m);
    }
}
```

```java
public class Main{
    static void Speed(int m){
        System.out.println("speed is "+m);
    }
    static void Acce(int m){
        System.out.println("Acce "+m);
    }
    public static void main(String[] args) {
        Main m1 = new Main();
        System.out.print("the ");
        m1.Speed(20);
    }
}
```

<mark style="background: #FFB8EBA6;">The dot (.) is used to access the object's attributes and methods.</mark>

## Java Constructors

A constructor in Java is a **special method** that is used to initialize objects.

The constructor is called when an object of a class is created.




---
---
----
## Quick check (your turn 👇)

Look at this code:

```java
void greet(String name) {
    System.out.println("Hello " + name);
}

greet("Alex");
```

# Encapsulation

if we need to assign value we need to have a main method

getter method
setter method

who  is having an argument and who is not having an argument

what happens if i make an int static inside a clas and then make method out of the class if i make 2 methods change in one method will reflect in the other method so during encapsulation make the variable `private int abc;`  private for using getter and setter so nobody will be able to just change it by just calling b1.id = 20;

getter name --> to get name

setter name --> to set name


```java
public class Cust {

        private int id;

        private String name;

        private String address;

  

        public void setInfo(int id, String name, String address)

        {

            this.id = id;

            this.name = name;

            this.address = address;

        }

        public int getId(){

            return id;

        }

        public String getName(){

            return name;

        }

        public String getAdderss(){

            return address;

        }

    }
```


```java
public class Manager {

  

    public static void main(String[] args) {

        Cust c1 = new Cust();  

        c1.setInfo(123,"appu","kahsda");

        System.out.println(c1.getId());

  

    }

}
```

so for constructor we have to give all the values to set it initially else there will be error
if we are using setter we have the option to skip the values

```java
public class Customer {

    private int id;

    private String name;

    private String address;

  

    public void setInfo(int id, String name, String address) {

        this.id = id;

        this.name = name;

        this.address = address;

    }

  

    public int getId() {

        return id;

    }

  

    public String getName() {

        return name;

    }

  

    public String getAddress() {

        return address;

    }

}
```

```java
public class Manager {

  

    public static void main(String[] args) {

    Customer c1 = new Customer();

        c1.setInfo(123,"appu","kahsda");

        System.out.println(c1.getId());

  

    }

}
```

```java
public class Cust {
    private int id;
    private String name;
    private String address;
    private static String company = "Sjhsjjksd";


    public Cust() {
        System.out.println("Deafult constructor");
    }

    public Cust(int id, String name, String address) {
        this.id = id;
        this.name = name;
        this.address = address;
    }

    public void setInfo(int id,String name, String address) {
        this.id = id;
        this.name = name;
        this.address = address;

    }

    public int getId() {
        return id;
    }

    public String getName() {
        return name;
    }

    public String getAddress() {
        return address;
    }

    public static String getCompany() {
        return company;
    }
}




=========================================================



public class Mang1 {
    public static void main(String[] args) {
        Cust c1 = new Cust();
        
        c1.setInfo(1,"sddsds",  "dsahshdjhsjnull");
        System.out.println(c1.getAddress());
        Cust c2 = new Cust(1,"shivam","DSDSAdas");
        System.out.println("ID is "+ c2.getId() + " name is " + c2.getName()+ " address is " + c2.getAddress());
        System.out.println(Cust.getCompany());
    }
}

```


# Inheritance



## Constructor Behavior In Inheritance

what is a constructor
what is a super statement and what is 
when can we write a super 
and when can we ignore the super

```java

```

ambiguity why java doesn't support multiple inheritance
constructor will have the class name

---

## Method overloading 

eg:

```java
public class ManagerOverloading {
    public static void main(String[] args) {
        A a1 = new A();
        a1.test();
    }
}
```

```java
public class A {
    A(){
  
    }
    void test(){
        System.out.println("first one");
    }
    void test(int m){
        System.out.println("Second one");
    }
}
```


---

constructor overloading and method over loading in single code

```java

```


<mark style="background: #ADCCFFA6;">widening</mark> the child is going to the parent 
<mark style="background: #ADCCFFA6;">narrowing</mark> the parent is going to the child


## Java widening vs narrowing.

In **Java inheritance**, your notes are basically right—this is about **casting between child and parent classes**.

### 🔹 Widening (Upcasting)

**Child → Parent**

- Happens **automatically**
    
- Always **safe**
    
- You lose access to child-specific methods
    

```java
class Parent {
    void show() {
        System.out.println("Parent");
    }
}

class Child extends Parent {
    void play() {
        System.out.println("Child");
    }
}

Parent p = new Child(); // widening (upcasting)
p.show();               // OK
// p.play();            // ❌ not accessible
```

👉 The reference is **Parent**, but the object is **Child**.

---

### 🔹 Narrowing (Downcasting)

**Parent → Child**

- Must be done **explicitly**
    
- Can cause **ClassCastException** if wrong
    
- Use `instanceof` to stay safe
    

```java
Parent p = new Child();

Child c = (Child) p;   // narrowing (downcasting)
c.play();              // OK
```

⚠️ Unsafe case:

```java
Parent p = new Parent();
Child c = (Child) p;   // ❌ Runtime error
```

✅ Safe version:

```java
if (p instanceof Child) {
    Child c = (Child) p;
}
```

---

### 🧠 One-line memory trick

- **Widening** → child → parent → _safe, automatic_
- **Narrowing** → parent → child → _explicit, risky_ 

If you want, I can also explain this with **real-world analogies** or **memory diagrams** 👀
we cannot override the static method



# NOTES

- else if
- `if (username.equals("admin") && password.equals("java123"))`
- ```int[] transactions = {2000, -500, -1000, 3000, -700}; for (int i = transactions.length - 1; i >= 0; i--) { System.out.println("Transaction: " + transactions[i]); }
  ```
� � Challenge 1. Check if a number is Prime 2. Print Fibonacci series 3. Find factorial of a number 4. Print numbers in reverse (10 → 1)

`Arrays.sort(marks);`

```java
public class Example4 {
    static boolean isEven(int number) {
        return number % 2 == 0;
    }

    public static void main(String[] args) {
        System.out.println(Example4.isEven(10)); // true
        System.out.println(Example4.isEven(7)); // false
    }
}
```

8⃣ Method with Array Parameter

