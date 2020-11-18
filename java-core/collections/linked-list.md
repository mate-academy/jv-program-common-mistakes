### Common mistakes

#### Make `Node` an inner class.
The purpose of inner classes is to group classes that belong together, which makes your code more readable and maintainable.
#### When creating a new `Node`, pass all the fields to `Node` constructor.
#### Create informative variable names.
Writing proper variable names can be a highly valuable investment to the quality of your code. 
Not only you and your teammates understand your code better, but it can also improve code sustainability in the future later on. 
When you go back to the same code base and re-read it over again, you should understand what is going on.

Bad example:
```java
String[] arr = new String[]{"Alex", "Bob", "Alice"};
for (String s : arr) {
    System.out.println(s);
}
```
Refactored code:
```java
String[] usernames = new String[]{"Alex", "Bob", "Alice"};
for (String username : usernames) {
    System.out.println(username);
}
```
#### Don’t complicate if-else construction. [Detailed explanation.](https://www.youtube.com/watch?v=P-UmyrbGjwE&list=PL7FuXFaDeEX1smwnp-9ri8DBpgdo7Msu2)
#### Don’t create repeating code.
If the logic of your code repeats - move it to the separate private method. 
Remember about [DRY and KISS](https://dzone.com/articles/software-design-principles-dry-and-kiss) principles.
#### Don’t create redundant variables.
Redundant variables are confusing and make your code less clean and much more difficult to read. Not to mention they occupy stack memory.
#### Don’t use class Objects.
#### Don’t forget about access modifiers
You should never want to expose the object fields directly. They should be accessed through special methods (getters and setters).
#### If you tested in `main()`, don’t forget to remove it as well as all commented code.
#### Don’t forget that you can have `null` as a method parameter in `remove(T object) method`.
