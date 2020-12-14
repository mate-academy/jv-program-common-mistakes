### Common mistakes

#### Don’t use class Objects.
#### Any magic numbers should be constants
Your code should be easy to read. Move all hardcoded values to constant fields and give them informative names.

Bad example:
```java
public class Shelf {
    private Object[] items;

    public Shelf() {
        items = new Object[6];
    }
}
```
Refactored code:
```java
public class Shelf {
    private static final int MAX_ITEMS_NUMBER = 6;
    private Object[] items;

    public Shelf() {
        items = new Object[MAX_ITEMS_NUMBER];
    }
}
```
#### Don’t complicate if-else construction. [Detailed explanation.](https://www.youtube.com/watch?v=P-UmyrbGjwE&list=PL7FuXFaDeEX1smwnp-9ri8DBpgdo7Msu2)
#### Don’t create repeating code.
If the logic of your code repeats - move it to the separate private method. For example, the index check for `get()`, `set()` and `remove()` methods should be moved to the separate method.

There is even a software design principle called [DRY](https://dzone.com/articles/software-design-principles-dry-and-kiss) that urges not to repeat yourself.
#### Don’t create redundant variables.
Redundant variables are confusing and make your code less clean and much more difficult to read. Not to mention they occupy stack memory.
#### Use [System.arraycopy()](https://docs.oracle.com/javase/8/docs/api/java/lang/System.html#arraycopy-java.lang.Object-int-java.lang.Object-int-int-) to move your array elements.
#### Resize the array in a separate method.
According to one of the important principles called **Single Responsibility** principle, any software component must have only one responsibility, that is, to be in charge of doing just one concrete thing.
#### Make your exceptions informative.
If you throw an Exception, you should always add an informative message so that it would be clear from the stack trace what exactly went wrong.
