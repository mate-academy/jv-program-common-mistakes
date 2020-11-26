### Common mistakes

#### Ignoring existing methods of the `Set` interface
Interface `Set` has a lot of [methods](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/Set.html). 
It is better to use existing methods, if possible, than to create your own.

#### Don't copy `Set` using loops
A lot of `Set` implementations have a constructor that takes Collection as a parameter. 
So we can use this constructor to initialize a `Set` with data from other collection.

#### Using specific reference when you can use more abstract: 
```
Bad example:
    HashSet set = new HashSet();
```
This example is bad cause it won't allow us to use polymorphism in our code.
```
Improved example:
    Set set = new HashSet();
```
