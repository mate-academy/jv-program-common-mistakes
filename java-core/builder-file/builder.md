### Common Mistakes

#### Utilize Private Constructor in Class
When employing a builder pattern, ensure the outer class's constructor with a Builder input parameter is private, not public, default, or protected. This hides it from users and prohibits passing the Builder in parameters.

#### Avoid Using Getters in Builder
You should not use getters in the builder class, as it is an internal class of Plane.
We will obtain data about Plane using the plane's getters.

#### Return Builder Object in Builder's Setters
Always return the Builder object in the Builder's setters. This facilitates the creation of different objects with varying amounts of parameters.
```java
    Car firstCar = new Car.Builder() // car with model, color, and year
        .setModel("bmw")
        .setColor("red")
        .setYear(2010)
        .build();
        
    Car secondCar = new Car.Builder() // car with model and color
        .setModel("audi")
        .setColor("black")
        .build();
        
    Car thirdCar = new Car.Builder() // car only with model
        .setModel("ford")
        .build();
```
