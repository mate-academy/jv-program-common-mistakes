### Common Mistakes

#### Avoid Magic Numbers in the Code
Your code should be easy to read. Move all hardcoded values to [constant fields](https://mate-academy.github.io/style-guides/java/java.html#s5.2.4-constant-names) and give them informative names.

#### Skip Getters and Setters in Class Node
We have access to private fields of the inner class, so using getters or setters is redundant.

#### Parameterize the Node Class
Class `Node` accepts a value, so we should parameterize it to prevent issues with data types.

#### Don't Overuse Public Access Modifiers
If a method serves a utility purpose and is used only within the same class, it should not be `public`. Adhere to the encapsulation principle by keeping your code as restricted as possible.

#### Avoid Default Access Modifiers
All fields and methods should have access modifiers. Remember the encapsulation principle.

#### Pay Attention to Variable Naming
Incorrect naming can significantly impact your code readability!
```java
// Bad naming:
    T[] a;
```  
```java
// Good naming:
    T[] stack;
```  

#### Use Annotation `@SuppressWarnings("unchecked")` if Your Implementation is Based on an Array and a Test Fails with the Error: `uses unchecked or unsafe operations`
Suppressing the warning with `@SuppressWarnings("unchecked")` informs the compiler that the programmer believes the code to be safe and won't cause unexpected exceptions.
```java
// Example:
@SuppressWarnings("unchecked")
public class Stack<T> {
}
```
