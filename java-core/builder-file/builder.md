### Common mistakes

#### Using private constructor of class 
If you use a builder pattern, make the outer class's constructor with a Builder input parameter private, not public, default or protected.
We should hide it from users and forbid to pass Builder in parameters.

#### Using getters in builder
You should not use getter in builder class, because it is internal class of Plane. 
We will get data about Plane using plane's getters.

#### Returning Builder object in Builder's setters.
You should always return Builder object in Builder's setters. It helps to create different objects with different amount of parameters.
```
    Car firstCar = new Car().Builder() // car with model, color and year
        .setModel("bmw")
        .setColor("red")
        .setYear(2010)
        .build();
        
    Car secondCar = new Car().Builder() // car with model and color
        .setModel("audi")
        .setColor("black")
        .build();
        
    Car thirdCar = new Car().Builder() // car only with model
        .setModel("ford")
        .build();
```
