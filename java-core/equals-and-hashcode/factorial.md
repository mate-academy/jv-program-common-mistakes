### Common mistake

#### Redundant if else blocks in code 
Don't use `else` blocks if we can avoid them. That makes code easier to read.
```
Bad Exampple:
 public int returnModulus(int input) {
    if (input % 2 == 0) {
        return 0;
    } else {
        return 1;
    }
}
```
```
Refactored code: 
 public int returnModulus(int input) {
    if (intpu % 2 == 0) {
        return 0;
    }
    return 1;
}
```

#### Not keeping your code simple and clean 
 - Don't use short variable naming that consists ofr 1 or 2 letters. Cause other including yourself 
in few weeks won't understand what's going on in the code. 
 - Don't make your code longer unnecessarily with adding empty lines between line of codes.
 - Same with redundant variables, don't create any unless it solves particular problem for you.
 