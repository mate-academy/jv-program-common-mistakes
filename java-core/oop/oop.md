### Common mistakes

#### Using specific reference when you can use more abstract: 
```
Bad example:
Cat fluffy = new Cat();
Dog oscar = new Dog();
```
This example is bad cause it won't allow us to use polymorphism in our code.
Our reference is now bonded to specific implementation, but it is always better to depend on the abstraction.
Let's see how we can improve it:
```
Improved example:
Animal fluffy = new Cat();
Animal oscar = new Dog();
```  
#### Ignoring access modifiers for you class and class members
Remember that if you don't use any access modifiers that will apply the default one. Do we always want
to have all elements with default access modifiers? Remind yourself about encapsulation principle and 
when private or public should be used.