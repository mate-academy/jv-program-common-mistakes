# HW 04

1. Do not implement following methods in DAO layer, only in service layer. Use update method from DAO.
    - ```void addDriverToCar(Driver driver, Car car);```
    - ```void removeDriverFromCar(Driver driver, Car car);```
2. Use `PreparedStatement` over `Statement`, even for a static query with no parameters in `getAll()` method. It's the best practice, and it's slightly faster.
