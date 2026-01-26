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

## Java Method Overloading


# java practice questions basic

https://www.geeksforgeeks.org/java/java-programming-examples/

