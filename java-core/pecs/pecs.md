#### Parameterize `MachineProducer` in such a way that any implementation NOT using `Machine` or its subtype could NOT be created.
For example, this code should not compile:
```java
public class StringProducer implements MachineProducer<String> { }
```
#### The method `getAll(Class type)` in `MachineService` must return `List<Machine>`. Don’t change parameterization here.
#### Consider creating a local variable in your implementation of `getAll(Class type)` method.
```java
List<? extends Machine> machines = someProducer.get();
return new ArrayList<>(machines);
```
#### The size of a list passed to `fill()` method must double. 
See the example implementation in the [video](https://www.youtube.com/watch?v=humASfXSA7c).
#### Don’t forget about access modifiers for your custom fields in `Excavator`, `Truck` and `Bulldozer` classes.
You should never want to expose the object fields directly. They should be accessed through special methods (getters and setters).
#### Don’t remove no-args constructors in `Excavator`, `Truck` and `Bulldozer` classes.
They will be needed to run the test.
