# Don't complicate if-else statements

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
