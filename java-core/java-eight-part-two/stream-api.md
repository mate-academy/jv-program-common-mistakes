## Common Mistakes (jv-stream-github-practice)

#### Minimize the Use of Stream Operations
* If you have a long boolean expression, consider creating your own implementation of Predicate and use it in your filter.
* Where possible, try to use a single map operation instead of a sequence of them.
* If you need to throw an exception when no result is found after stream execution, sometimes `get()/getAsDouble()` may help. Try to look up what these methods do.

#### Utilize Stream API to Solve All Tasks. Avoid Using Loops.
#### Understand the Difference Between Bitwise and Boolean Operators.
#### Consider the Better Way to Compare Enum Values: equals() vs == ?
[Hint](https://stackoverflow.com/a/1750453)
#### Start Each New Method on a New Line in the Stream for Better Readability. For example:
```java
List<String> data = new ArrayList();
data.stream()
        .distinct()
        .filter(x -> x.length() < 5)
        .map(Integer::valueOf)
        .collect(Collectors.toList());
```
#### Employ Constants
Magic numbers and strings decrease code readability. Avoid them and use constants in the class CandidateValidator.

#### Utilize Validator Properly
If you need to pass your custom `Predicate` implementation into a filter, there are two optimal solutions:
```java
Predicate<Candidate> customPredicate = new CustomPredicate<>();
Collection.stream()
    .filter(predicate)
    ...
```  
Or:
```java
Collection.stream()
        .filter(new CustomPredicate<>())
        ...
```

#### The Exception Message in Method `findMinEvenNumber()` Should Be Formatted as Follows:
```java
"Can't get min value from list: " + numbers
```