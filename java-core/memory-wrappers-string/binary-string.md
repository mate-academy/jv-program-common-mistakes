# Common mistakes

## Don’t complicate if-else construction.

### Problem Statement:
We are tasked with creating a method that accepts an integer as an argument and returns a boolean value indicating whether the number is odd. The method should return `true` if the number is odd, and `false` otherwise. The oddness of a number can be determined by checking the remainder when the number is divided by 2 (`number % 2`). If the remainder is 1, the number is odd.

### Example 1: Complicated if-else construction
#### Problem:
In this case, the code uses an if-else block to check the condition and return `true` or `false` accordingly. This approach is straightforward but verbose. It uses two return statements within the if-else block, which can be seen as redundant and may make the code less readable.

```java
public class Example1 {
    public static boolean isOdd(int number) {
        if (number % 2 == 1) {
            return true;
        } else {
            return false;
        }
    }

    public static void main(String[] args) {
        System.out.println(isOdd(3));  // Output: true
        System.out.println(isOdd(4));  // Output: false
    }
}
```

### Example 2: Refactored version with ternary operator
#### Problem:
The ternary operator is a more concise way to write simple if-else statements. However, while it reduces the verbosity of the code, it still evaluates a condition to return `true` or `false`, which can be further simplified.

```java
public class Example2 {
    public static boolean isOdd(int number) {
        return (number % 2 == 1) ? true : false;
    }

    public static void main(String[] args) {
        System.out.println(isOdd(3));  // Output: true
        System.out.println(isOdd(4));  // Output: false
    }
}
```

### Example 3: Refactored version with `return number % 2`
The expression `number % 2 == 1` itself evaluates to a boolean value (`true` or `false`). Therefore, there's no need for a ternary operator or an if-else block. This version of the code is the most simplified and direct way to solve the problem.

```java
public class Example3 {
    public static boolean isOdd(int number) {
        return number % 2 == 1;
    }

    public static void main(String[] args) {
        System.out.println(isOdd(3));  // Output: true
        System.out.println(isOdd(4));  // Output: false
    }
}
```

In summary, as we progress from Example 1 to Example 3, we move from a verbose solution to a more concise and readable one, while still accurately solving the problem. This progression demonstrates the importance of code refactoring for simplicity and readability, which are crucial for maintainable and understandable code.

## Use StringBuilder instead of String or StringBuffer.
Since the String object is immutable, each call for concatenation will result in a new String object being created.
On the other hand, StringBuilder is mutable and thus is considered to be a very efficient way to concatenate Strings.
The compiler will replace concat with StringBuilder when we have a simple code row but with loops.  [java doc](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html)

## Create your own implementation, don’t use any standard methods.

## Remember about informative names of the variables.
Writing proper variable names can be a highly valuable investment in the quality of your code. 
Not only you and your teammates understand your code better, but it can also improve code sustainability in the future. 
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

## Try to use only one for/while loop in your solution.
The more loops you have, the slower your code may get, so try to solve this task with a minimum amount.
