### Common mistakes

#### All non-constant fields should be initialized in the constructor
Example:
```java
public class Shelf {
    private Object[] items;

    public Shelf() {
        items = new Object[]{"book", "photo", "phone"};
    }
}
```
#### Any magic numbers should be constants
Your code should be easy to read. Let's move all hardcoded values to constant fields and give them informative names.

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
#### Don’t use any kind of List, Set or Map
We will soon learn how these collections work.
#### Don’t create repeating code
If the logic of your code repeats - move it to the separate private method. 
There is even a software design principle called [DRY](https://dzone.com/articles/software-design-principles-dry-and-kiss) that urges not to repeat yourself.
#### Don't use class Objects
