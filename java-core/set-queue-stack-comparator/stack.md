### Common mistakes

#### Don't use magic numbers in the code
Your code should be easy to read. Move all hardcoded values 
to [constant fields](https://mate-academy.github.io/style-guides/java/java.html#s5.2.4-constant-names) and give them informative names.

#### Don't use getters and setters in class Node
We have access to private fields of inner class, so using getters or setters is redundant.

#### Parameterize Node class 
Class `Node` takes a value, so we should parameterize it to prevent problems with data types.

#### Don't use public access modifiers everywhere
If the method has only a utility purpose and is used only inside the same class, it should not be 
`public`. Keep your code as close as possible to follow the encapsulation principle.

#### Avoid default access modifiers
All fields and methods should have access modifiers. Remember about the encapsulation principle.

#### Variable naming
Incorrect naming may have significant impact on your code readability!  
```
Bad naming:
    T[] a;
```  
```
Good naming: 
    T[] stack;
```  
#### If your implementation is based on an array, use annotation `@SuppressWarnings("unchecked")` if test failed with error: `uses unchecked or unsafe operations`
Suppressing the warning with @SuppressWarnings("unchecked") tells the compiler that the programmer believes the code to be safe and won't cause unexpected exceptions.
```
Example:
@SuppressWarnings("unchecked")
public class Stack<T> {
}
``` 
