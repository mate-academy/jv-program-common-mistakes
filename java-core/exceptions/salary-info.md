### Common mistakes

#### If you create a formatter, make it a constant field.
If you create a formatter, make it a [constant](https://mate-academy.github.io/style-guides/java/java.html#s5.2.4-constant-names).
That will make your code easier to understand. Plus if you use it in several places in your code 
you will be able to change its value easily with one action(change variable declaration). In other case you need to update
value in each each place it's being used.

#### Use LocalDate instead of Date.
Here is some [background](https://www.baeldung.com/migrating-to-java-8-date-time-api) why you should use it primarily.

#### Don’t create redundant loops. Two is enough.
The more loops you have, the slower your code may get, so try to solve task with minimum amount.

#### Don’t use two-dimension arrays and HashMap(or any other Map).
They may simplify the work for you, but for now you will get more value from solving this task if you complete it 
without using these data structures. Let's do it manually.

#### Use StringBuilder.
You have learned in previous topics about different internal structure of `String` and `StringBuilder` don't forget to use it 
on practice. What works better when we have multiple concatenation in our code?

#### Remember about informative name of the variables.
