### Common mistakes

### Keep the code simple while comparing something:
Try to make your code more simple where it's possible
```
Bad example:
 if (a == b) {
 return true;
 }
```
```
Refactored code:
 return a == b;
```

#### Don't cast an object every time you compare each set of fields
In method `equals` let's not cast the input object always during field comparison instead, you can
create a new object and cast it to the needed type just once.

#### Think of what you want to use: `instanceof` or `getClass()`
You should choose which of these options will suit us the best. What's the difference between them? 

#### Follow every rule of equals and hashcode contract
Remember all theory that you've just learned, does your code fulfill all requirements? 
If not you may get unpredictable results especially while using your class with collections, like HashMap.

#### Don't use methods of the Objects.class
Objects.class can make this task a bit easier because you can delegate null checks to it, but we strongly recommend you not to use it here. Our current task now is to understand how basic methods work inside of the box and why certain checks are important while writing your code.

#### Use `this` keyword only when it's absolutely necessary
```java
public class Square {
    public Integer width;
    // necessary to use `this` keyword because of variable shadowing
    public Square(Integer width) {
        this.width = width;
    }
    // `this` keyword usage is not necessary
    public int countArea() {
        return width * width; // not `this.width * this.width`
    }
}
```
