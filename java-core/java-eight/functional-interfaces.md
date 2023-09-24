### Common Mistakes

#### Avoid Rushing to Create Your Own Functional Interfaces
Java already provides several functional interfaces. Try to find the behavior you need among the [existing ones](https://docs.oracle.com/javase/8/docs/api/java/util/function/package-summary.html).

#### Avoid Magic Numbers in Your Code
Your code should be easy to read. Move all hardcoded values to [constant fields](https://mate-academy.github.io/style-guides/java/java.html#s5.2.4-constant-names) and give them informative names.

#### Simplify If-Else Constructions [Detailed explanation](./../complicated-if-else.md)

#### Avoid Hardcoding When You Need to Return Random Values
Consider using methods from the `java.util.Random` class instead.

#### Don't Create Redundant Variables
Redundant variables are somewhat similar to commented code. They create confusion, make your code less clean, and are more difficult to read. Additionally, they occupy stack memory.