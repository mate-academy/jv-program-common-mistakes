### Common mistakes

#### Don't use abstract classes to set behaviour for classes
Abstract classes and interfaces have different use cases. Try to figure out when to use 
both in this task by yourself. If you're blocked [this](https://stackoverflow.com/a/479168) may give you a hint.

#### Don't use verbs for class/interface names
```
Bad example:

public interface CalculateArea {
}
```
```
Improved example:

public interface AreaCalculator {
}
```
#### Don't put all behaviour into a single interface if the methods are conceptually different from each other.
All our classes and interfaces should have a single purpose - `draw()` and `getArea()` methods are not conceptually close to each other.

#### You can pass random values to the constructor of a figure instead of generating them inside figure classes.
Let's generate random values in `FigureSupplier`.

#### All magic numbers in your code should be constants.
Please see [this article](https://mate-academy.github.io/style-guides/java/java.html#s5.2.4-constant-names) to learn about constant fields and their naming requirements.
```
Bad example:

public class FigureSupplier {
    public Figure getRandomFigure() {
        Random random = new Random();
        int `figureNumber` = random.nextInt(5);
        // generate a specific figure based on the `figureNumber` value
    }
}
```
```
Improved example:

public class FigureSupplier {
    public static final int FIGURE_COUNT = 5;

    public Figure getRandomFigure() {
        Random random = new Random();
        int figureNumber = random.nextInt(FIGURE_COUNT);
        // generate a specific figure based on the `figureNumber` value
    }
}
```
#### Don't use static methods in your solution
Static methods are in general a bad practice. Let's better create an instance of a class which method you want to call.

#### Don't return `null` from a method.
Returning `null` from a method is a bad practice. If you use switch-case in your solution, you may just put the last possible option in the `default` case.

#### Use only eng in messages/code:
Try not to use ukr/ru messages in `toString()` or `System.out.println()` statements.
We want to make our code universal and consistent.

#### Write informative messages when you commit code or open a PR.
         
Bad example of commit/PR message: `done`/`fixed`/`commit`/`solution`/`added homework`/`my solution` and other one-word, abstract or random messages. 
