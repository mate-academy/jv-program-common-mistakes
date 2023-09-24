### Common Mistakes

#### Avoid Commented Code
It's important to develop good practices from the outset and rectify bad ones. Pushing commented code falls into the latter category. Therefore, whenever you create a Pull Request (PR), ensure there is no commented code present. The primary issue with commented code is that it adds confusion without any real benefit. When working with a repository containing commented code, you will waste time analyzing its purpose and the reason it was added in the first place.

#### Simplify If-Else Constructions [Detailed explanation](./../complicated-if-else.md)

#### Be Mindful of the Class You Extend When Declaring Your Exception
Should it extend `RuntimeException` or `Exception`, and why? (Double-check the task description.)

#### Be Mindful of Exceptions in Method Signatures
Should we use the `throws` keyword with the `getUserScore()` method? Let's think about it.

#### Avoid Unnecessary Variables
Strive to keep your code simple, as simplicity is a core principle in programming. If you create a variable without a particular reason, think twice about its necessity and whether the task can be completed without it without compromising code readability.

#### Use Informative Variable Names

#### Avoid Excessive Empty Lines
```java
// Bad example:
public int add(int a, int b) {

    int result = a + b;
    
    
    return result;
    
}

// Good example:
public int add(int a, int b) {
    return a + b;
}
```

#### Avoid Hardcoding Messages in Exception Classes; Pass Them to the Constructor
Hardcoding reduces code flexibility by embedding actual values within the source code.

#### Replace Magic Numbers with Constants
Your code should be easy to read. Move all hardcoded values to [constant fields](https://mate-academy.github.io/style-guides/java/java.html#s5.2.4-constant-names) and give them informative names. For example, constants can be named `EMAIL_POSITION_IN_ARRAY`, `SCORE_POSITION_IN_ARRAY`.