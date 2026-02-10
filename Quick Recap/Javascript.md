variable name could start with either " _ " or " $ " symbols

<mark style="background: #ABF7F7A6;">If you put a number in quotes, the rest of the numbers will be treated as strings, and concatenated.</mark>

```js
let x =  2 + 3 +"5";
console.log(x)
```

--> output  --> 55

```js
let x = "5" + 2 + 3;
console.log(x)
```

--> output --> 523

### Let

1. Variables declared with `let` have **Block Scope**
2. Variables declared with `let` must be **Declared** before use
3. Variables declared with `let` <mark style="background: #ABF7F7A6;">cannot be Redeclared</mark> in the same scope

## Function Scope

```js
function myfunction() {  
  var x = 1;  
  let y = 2;  
  const z = 3;  
}  
//x can NOT be used here  
//y can NOT be used here  
//z can NOT be used here
```

## Global Scope

```js
{  
  var x = 2;  
}  
// x CAN be used here
```

Variables declared with the `var` always have **Global Scope**.

 

```js
console.log("welcome to javascript")
```

```terminal
node file1.js
```


## 📦 Understanding Modules (Core Idea)

Node is built from **modules**.

Example using the built-in file system module:

```js
const fs = require("fs");  
fs.writeFileSync("hello.txt", "Hello world");
```

Now a file appears in your folder.

```java
var v1 = 100;
console.log(v1);
console.log('v1 =' + v1);
console.log('type of v1 =' + typeof v1 );
```

```out put
100
v1 =100
type of v1 =number
```

```js
var v1 = 100;
console.log(v1);
console.log('v1 =' + v1);
console.log('type of v1 =' + typeof v1 );
var v2 = true;
console.log("type of v2"+ typeof v2);
var v3 = "good";
console.log("type of v2"+ typeof v3);
```

```output

100
v1 =100
type of v1 =number
type of v2boolean
type of v2string
```

```js
var v1 = 100;
console.log(`my name is ${v1}`);
console.log(v1);
```

```output
my name is 100
100
```

sooo

` `${varible_name}` `


```js
var name = "my namee is akshay";

console.log(name);
console.log(name.length);
console.log(name.toUpperCase());
console.log(name.toLowerCase());
```

```output
my namee is akshay
18
MY NAMEE IS AKSHAY
my namee is akshay
```

```js
var name = "My name is akshay";
console.log(`First Name: ${name.substr(name.lastIndexOf(' ') + 1)}`);
```

```output
First Name: akshay
```

```js
var name = "My name is akshay";

console.log(`First Name: ${name.substr(name.lastIndexOf(' ') + 1)}`);
console.log(`Last Name: ${name.substr(name.indexOf(' ') + 1)}`);

```

```js
var d = new Date();
console.log(d.getDate());
console.log(d.getMonth());
console.log(d.getFullYear());
console.log(d.getHours());
console.log(d.getMinutes());
```

```ooutput
PS D:\Desktop\my-nord-app> node file1.js
9
1
2026
15
20
```

d.toLocate

```js
var v1 = 100;
var v2 = 200;
var uname = "ammu";
var mname = "Pllu";

if (v1 == v2)
    console.log("both are same");
if(uname == "ammu" && mname == "Pllu")
    console.log("htis is good");
```

``==``  → will only check the content and not the type

`===` → will check the type too

if "100" == 100 → will give the output as true

if "100" === 100 → will give the output as false


<mark style="background: #ABF7F7A6;"> let  </mark> and <mark style="background: #ABF7F7A6;">  var  </mark> are used to declare the variable

```js
var i = 1;
do {
    console.log(i);
    i++;
} while (i <= 10);
```

```js
var items = ["pencil","cat","dog"];

console.log(items);
console.log(items.length);
items.push("tintu");
items.unshift("mingan")
console.log(items)
items.splice(2,1,"goooo");
console.log(items);
```

pop → remove the element

