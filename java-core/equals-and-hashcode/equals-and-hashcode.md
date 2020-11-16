### Common mistakes

### Redundant code while comparing smt:
Try to make your code more simple where it's possible
```
Bad example:
 if (a == b) {
 return true;
 }
```
```
Refactored code:
 return a == b;
```

#### Casting input object every time you compare set of fields
In method `equals` let's not cast input object every time while field comparison but instead 
create new object of the needed type instead.

#### Comparing types with `instanceof` or `getClass()`
You should choose which of these options will suit us the best. What's the difference between them
anyway. Try to figure it out by yourself, but is you stuck, here's a [hint](https://overcoder.net/q/59643/instanceof-vs-getclass#1971415)

#### Not following all rules from equals and hashcode contract
Remember all theory that you've just learned, does you code fulfill all requirements? 
If not you may get unpredictable result especially while using your class with collections, like HashMap

#### Using util methods from Objects.class
Objects.class can make this task a bit easier, because you can delegate null checks to it, but it will 
strongly recommend to not use it now. Our current task is to understand how basic methods work inside the box
and why certain check are important while writing your programs.
