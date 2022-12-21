# HW 04

1. Do not implement following methods in DAO layer, only in service layer. Use update method from DAO.
    - ```void addDriverToCar(Driver driver, Car car);```
    - ```void removeDriverFromCar(Driver driver, Car car);```
2. Use `PreparedStatement` over `Statement`, even for a static query with no parameters in `getAll()` method. It's the best practice, and it's slightly faster.
3. Be careful and do not create nested connection problems. Nested connection problem is the situation, when you open DB connection inside another connection. **This often occurs when you try to get from DB drivers for some car**.
