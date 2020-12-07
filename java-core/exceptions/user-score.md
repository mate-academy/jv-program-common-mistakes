### Common mistakes

#### Don’t use commented code.
It's important to develop good practices from the very beginning and fix bad ones. Pushing commented code belongs to the second group.
So whenever you create PR double check for absence of commented code. 
The main problem is that commented code adds confusion with no real benefit, because while using repository 
with commented code in it you will waste time analyzing its purpose and the reason it was added in the first place. 

#### Don’t complicate if-else construction. [Detailed explanation](https://www.youtube.com/watch?v=P-UmyrbGjwE&list=PL7FuXFaDeEX1smwnp-9ri8DBpgdo7Msu2)

#### Be attentive about the class you extend to declare your exception
Should it extend `RuntimeException` or `Exception` and why? (double check task description)

#### Be attentive about exception with method signature
Should we use `throws` keyword with method `getUserScore()`? Let's think about it.

#### Don’t create unneeded variables.
Try to keep your code simple. That is one of the core principle in programming. If you create a variable without any 
particular reason in mind - think twice if it is required and whether we can complete task without it and we won't 
decrease code readability.

#### Remember about informative name of the variables.

#### Don't complicate your code with a lot of empty lines
```
Bad example:
public int add(int a, int b) {

    int result = a + b;
    
    
    return result;
    
}

Good example:
public int add(int a, int b) {
    return a + b;
}
```

#### Don't hardcode the message in the exception class, pass it to constructor.
Hardcoding reduces the flexibility of the code by forcing actual values into the source code.
