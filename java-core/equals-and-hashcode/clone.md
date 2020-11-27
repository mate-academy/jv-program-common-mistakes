### Common mistakes

#### Follow encapsulation rule
Remember to use access modifiers with all class elements. We should explicitly control the access level to 
different parts of our code.

#### We're interested in creating deep copy
If you copy an object of class `Car` with field `Engine` inside - keep in mind that `engine` may have non-primitive fields
on its own. So how will they be copied?  What influence does it make on our `car` copy? Is it deep or shallow?

#### Your method in the class should have clear and logical structure
Your class should have a clear readable structure and order of elements. Generally, order
class methods by functionality, meaning if you have several methods that are involved in completing 
a common task they should be located near to each other independently of their accessibility.  
Let's consider the following situation: we need to calculate the salary of an employee. In our class we use
3 methods to achieve desired result: `getMonthlySalary()`, `getInitialSalary()` and `getMonthlyBonus()` methods.  
How can we order our methods?   
``` 
Bad example: 

private int getMonthlyBonus(Person employee); {...}

//Constructor and some methods..

public int getMonthlySalary(Person employee) {
    int initialSalary = getInitialSalary(employee);
    int bonuses = getMonthlyBonus(employee);
    return initialSalary + bonuses;
}

// Other methods

private int getInitialSalary(Person employee); {...}
```
``` 
Refactored code: 

//Constructor and other class elements..

public int getMonthlySalary(Person employee) {
    int initialSalary = getInitialSalary(employee);
    int bonuses = getMonthlyBonus(employee);
    return initialSalary + bonuses;
}

private int getInitialSalary(Person employee); {...}

private int getMonthlyBonus(Person employee); {...}

// Other methods
```
In the second example we've united all methods with a common purpose in one place, which makes our code easier to read and understand. In case you don't have several methods with common logic it will make sense to order them by 
accessibility (from `public` to `private`).
