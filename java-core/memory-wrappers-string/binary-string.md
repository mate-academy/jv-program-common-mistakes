### Common mistakes

#### Don’t complicate if-else construction. [Detailed explanation.](https://www.youtube.com/watch?v=P-UmyrbGjwE&list=PL7FuXFaDeEX1smwnp-9ri8DBpgdo7Msu2)

#### Use StringBuilder instead of String or StringBuffer.
Since the String object is immutable, each call for concatenation will result in a new String object being created.
On the other hand, StringBuilder is mutable and thus is considered to be a very efficient way to concatenate Strings.
Compiler will replace concat with StringBuilder when we have simple code row but with a loops that won't work.  [java doc](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html)

#### Create your own implementation, don’t use any standard methods.

#### Remember about informative names of the variables.
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

#### Try use only one for/while loop in your solution.
The more loops you have, the slower your code may get, so try to solve this task with minimum amount.
