### Common mistakes

#### Any magic numbers should be constants
Your code should be easy to read. Move all hardcoded values 
to [constant fields](https://mate-academy.github.io/style-guides/java/java.html#s5.2.4-constant-names) and give them informative names.
For example: constants can be `defaultCapacity`, `loadFactor`...

#### Don’t use getters and setters in class Node
We have access to private fields of inner class, so using getters or setters is redundant.

#### Remember to parameterize the Node class
Class `Node` should take key and value, so we should parameterized it to prevent problems with data types.

#### Using public access modifiers everywhere
If the method has only a utility purpose and is used only inside the same class, it should not be 
`public`. Keep your code as close as possible to follow the encapsulation principle.

#### Remember about access modifiers.
All fields and methods should have access modifiers. Remember about the encapsulation principle.

#### Diamond operator
Be attentive with diamond operator in java. 
What is the difference between: `new Node<>(...)` and `new Node<K,V>(...)`and `new Node(...)`. 
Read more about it [here](https://www.baeldung.com/java-diamond-operator)
