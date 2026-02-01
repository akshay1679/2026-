**<mark style="background: #FFB8EBA6;">object</mark>** --> anything available in real world is called object 
**<mark style="background: #FFB8EBA6;">class</mark>** --> object is the instance of class, the class is the structure or blueprint and its a collection of <mark style="background: #ABF7F7A6;">attributes</mark>(properties of class variables of class) and <mark style="background: #ABF7F7A6;">behaviors</mark> ie car is the blueprint and Ferrari F40 
is the object
car is a physical object while  <mark style="background: #FF5582A6;">ask how a car becomes class</mark>
**<mark style="background: #FFB8EBA6;">abstraction</mark>** -->  hiding the unwanted data also it only shows what is necessary GRANDY BOOCH
<mark style="background: #FFB8EBA6;">encapsulation</mark> --> binding the data members all together in one unit

```java
class Employee {  
    String name;  
    int age;  
    public void displayEmployee(){  
        System.out.println("Name ="+name);  
        System.out.println("Age ="+age);  
  
    }  
}  
class HelloWorld {  
    public static void main(String as[])  
    {  
        Employee obj = new Employee();  
        obj.displayEmployee();  
    }  
}
```

```output
Name = null
Age = 0
```

```java
class Employee {  
    String name;  
    int age;  
    public void displayEmployee(){  
        System.out.println("Name ="+name);  
        System.out.println("Age ="+age);  
  
    }  
}  
class HelloWorld {  
    public static void main(String as[])  
    {  
        Employee obj = new Employee();  
        obj.name = "akshay";  
        obj.age = 20;  
        obj.displayEmployee();  
    }  
}
```

there is a problem with the code ie we could be able to tamper with the code ie we could change the data

to prevent we could make the member variables private

```java
class Employee {  
    private String name;  
    private int age;  
    public void displayEmployee(){  
        System.out.println("Name ="+name);  
        System.out.println("Age ="+age);  
  
    }  
}  
class HelloWorld {  
    public static void main(String as[])  
    {  
        Employee obj = new Employee();  
        obj.name = "akshay";  
        obj.age = 20;  
        obj.displayEmployee();  
    }  
}
```

when we run it we will get error ie we cannot change the name and age to prevent it

```java
class Employee {  
    private String name;  
    private int age;  
    public void SetName(String name){
    this.name = name;
    }
    public void SetAge(int age){
        this.age = age;
    }
    public void displayEmployee(){  
        System.out.println("Name ="+name);  
        System.out.println("Age ="+age);  
  
    }  
}  
class HelloWorld {  
    public static void main(String as[])  
    {  
        Employee obj = new Employee();  
        obj.setName("akshay");
        obj.setAge(20); 
        obj.displayEmployee();  
    }  
}

```

we can also iinclude or condition inside

```java
public void SetAge(int age){
	if (age > 100 || age < 0)
		system.out.println("invalid age");
	else
        this.age = age;
    }
```


final code

```java
class Employee {  
    private String name;  
    private int age;  
    public void SetName(String name){  
        this.name = name;  
    }  
    public void SetAge(int age){  
        if (age > 100 || age < 0)  
            System.out.println("invalid age");  
        else  
            this.age = age;  
    }  
  
    public void displayEmployee(){  
        System.out.println("Name ="+name);  
        System.out.println("Age ="+age);  
  
    }  
}  
class HelloWorld {  
    public static void main(String as[])  
    {  
        Employee obj = new Employee();  
        obj.SetName("akshay");  
        obj.SetAge(20);  
        obj.displayEmployee();  
    }  
}
```