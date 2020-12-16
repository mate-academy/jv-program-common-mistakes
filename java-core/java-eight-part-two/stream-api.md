__stream-api__
* Don't complicate stream operation with a lot of `filter()` operations. 
Don't create more than one `filter()` operation for each method.
* Use Stream API to solve all tasks. Don't use loops.
* Remember about the difference between bitwise and boolean operators.
* Pay attention to what is a better way to compare Enum values: equals() vs == ? [Hint](https://stackoverflow.com/a/1750453).
* Call each new method from a new line in the stream. It will look better. For example:
```
List<String> data = new ArrayList();
data.stream()
        .distinct()
        .filter(x-> x.length()<5)
        .map(Integer::valueOf)
        .collect(Collectors.toList());
```
