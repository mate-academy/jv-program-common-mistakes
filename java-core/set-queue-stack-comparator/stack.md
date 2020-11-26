### Common mistakes

#### Use any magic numbers in the code
Your code should be easy to read. Move all hardcoded values 
to [constant fields](https://mate-academy.github.io/style-guides/java/java.html#s5.2.4-constant-names) and give them informative names.

#### Use getters and setters in class Node
We have access to private fields of inner class, so using getters or setters is redundant.

#### Parameterization of the Node class
Class `Node` take value, so we should parameterized it to prevent problems with data types.

#### Using public access modifiers everywhere
If the method has only a utility purpose and is used only inside the same class, it should not be 
`public`. Keep your code as close as possible to follow the encapsulation principle.

#### Remember about access modifiers.
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
