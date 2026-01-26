When you create objects in Java using `new`, they take up **<mark style="background: #FFB8EBA6;">heap memory</mark>**.
relocates memory

1. when obj is pointing to null
2. and when the execution is complete

```java
string str = "hello";
string str1 = "hi";
str = str1;
```

now object "hello" will be deallocated
being a developer we cannot force the garbage collector to deallocate
but we can request the garbage collector but its not necessory that the garbage collector will delocate the object


## Important points (exam gold ✨)

- Runs **<mark style="background: #FFB8EBA6;">automatically</mark>** (you don’t control exact timing)
- Works on **<mark style="background: #FFB8EBA6;">Heap memory</mark>**
- Improves **performance & memory management**  It **frees memory**, which helps performance _indirectly_
- You can _request_ GC using:
```java
System.gc();
```
- ⚠️ But Java may ignore it

Q. Is an object **guaranteed** to be removed immediately after setting it to `null`?

Setting an object to `null` **only makes it _eligible_** for garbage collection.  
The **Garbage Collector decides _when_** to actually remove it.

