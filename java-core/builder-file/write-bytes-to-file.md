### Common mistakes

#### Don't ignore exceptions
Leaving empty catch block or `e.printStackTrace` here is a bad practice. 
Better re-throw `RuntimeException` with original exception and some message in the parameters:
```
catch (Exception e) {
    throw new RuntimeException("Can't write data to file " + fileName, e);
}
```

#### Remember about informative name of the variables
