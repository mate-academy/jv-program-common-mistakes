### Common Mistakes

#### Simplify Code When Making Comparisons:
Aim to simplify your code wherever possible.
```java
// Bad example:
if (a == b) {
    return true;
}

// Refactored code:
return a == b;
```

#### Avoid Casting Objects Repeatedly When Comparing Fields:
In the `equals` method, avoid casting the input object during each field comparison. Instead, create a new object and cast it to the required type just once.

#### Decide Between `instanceof` and `getClass()`:
Choose the option that best suits your needs. What's the difference between them?

#### Adhere to the Equals and HashCode Contract:
Recall the theory you've learned and ensure your code fulfills all the requirements. Failing to do so may lead to unpredictable results, especially when using your class with collections like HashMap.

#### Avoid Using Methods from the Objects Class:
The Objects class can simplify this task by delegating null checks to it, but we strongly recommend not using it here. The current task aims to help you understand how basic methods work and why certain checks are important when writing your code.

#### Use the `this` Keyword Only When Absolutely Necessary:
```java
public class Square {
    public Integer width;
    // Necessary to use `this` keyword due to variable shadowing
    public Square(Integer width) {
        this.width = width;
    }
    // `this` keyword usage is not necessary
    public int countArea() {
        return width * width; // not `this.width * this.width`
    }
}
```
