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
## Java Method Overloading

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

## Quick check (your turn 👇)

Look at this code:

```java
void greet(String name) {
    System.out.println("Hello " + name);
}

greet("Alex");
```

👉 What is the **formal argument**?  
👉 What is the **actual argument**?

Answer in one line — I’ll confirm 👍

