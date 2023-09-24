### Common Mistakes

#### Explore Existing Methods of the `Set` Interface
The `Set` interface provides a variety of [methods](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/Set.html). It's preferable to utilize these existing methods, when possible, rather than creating your own.

#### Avoid Copying `Set` Using Loops
Many `Set` implementations have a constructor that accepts a Collection as a parameter. You can use this constructor to initialize a `Set` with data from another collection.

#### Prefer Abstract References Over More Specific Ones:
```java
// Bad example:
    HashSet set = new HashSet();
```
This example is unfavorable as it doesn't allow us to use polymorphism in our code.
```java
// Improved example:
    Set set = new HashSet();
```