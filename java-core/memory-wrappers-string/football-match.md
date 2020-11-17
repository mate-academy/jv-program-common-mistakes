### Common mistakes

#### Don’t use commented code.
It's important to develop good practices from the very beginning and fix bad ones. Pushing commented code belongs to the second group.
So whenever you create a PR - double check for absence of commented code. 
The main problem is that commented code adds confusion with no real benefit, because while using repository 
with commented code in it you will waste time analyzing its purpose and the reason why it was added. 

#### Use ternary operator instead of if-else.
Ternary operator is a condensed form of the `if-else` statement that also returns a value. It is often useful to make your code look cleaner.

#### Don’t create redundant variables.
Redundant variables are somewhat similar to commented code. They are confusing and make your code less clean and much more difficult to read. Not to mention they occupy stack memory.

#### Don’t forget about whitespace between operators.
According to the convention, all binary operators (those operators that work with two operands) should be separated from their operands by spaces.
[Read more.](https://www.oracle.com/java/technologies/javase/codeconventions-whitespace.html)
