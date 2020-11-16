### Common mistakes

#### Ignoring encapsulation
Remember to use access modifiers with all class elements. We should explicitly control access level to 
different parts of our code.

#### Creating shallow copy of object's field
If you copy object of class `Car` with field `Engine` inside - keep in mind that `engine` may have non-primitive fields
on its own. So how will they will copied?  What influence does it make on our  `car` copy? Is it deep ro shallow?

#### Order of methods in your class
Your class should have clear readable structure and order of elements. Generally order
class methods by functionality, meaning if you have several methods that are involved in completing 
common task they should be located near to each other independently of their accessibility.
Let's consider following situation: we need to calculate salary for employee. In our class we use
3 methods to achieve desired result: `getMonthlySalary()`, `getInitialSalary()` and `getMonthlyBonus()` methods.
How can we order our methods? 
``` 
Bad example: 

private int getMonthlyBonus(Person employe); {...}

//Contstructor and other class elements..

public int getMonthlySalary(Person employee) {
    int initialSalary = getInitiallySalary(employee);
    int bonuses = getMonthlyBonus(employee);
    return initialSalary + bonuses;
}

// Other methods

private int getInitialSalary(Person employee); {...}
```
``` 
Refactored code: 

//Contstructor and other class elements..

public int getMonthlySalary(Person employee) {
    int initialSalary = getInitiallySalary(employee);
    int bonuses = getMonthlyBonus(employee);
    return initialSalary + bonuses;
}

private int getInitialSalary(Person employee); {...}

private int getMonthlyBonus(Person employe); {...}

// Other methods
```
In second example we united all methods with common purpose in one place, which makes our code easier to read 
and understand. In case you don't have several methods with common logic it will make sense to order them by 
accessibility (from `public` to `private`).
