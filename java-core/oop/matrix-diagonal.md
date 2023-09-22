### Common Mistakes

#### Prefer Single Loop Over Nested Loops Where Possible
Algorithms with nested loops require more computational resources compared to those with a single loop. As a result, you may experience performance degradation when overusing this approach. Always try to avoid nested loops where possible.

#### Adhere to Checkstyle Rules:
```java
// Bad practice:
for(int i=0;i<array.length;i++){
if(array[i]>max)
max=array[i];
}

// Refactored code:
for (int i = 0; i < array.length; i++) {
    if (array[i] > max) {
        max = array[i];
    }
}
```
[CheckStyle rules](https://google.github.io/styleguide/javaguide.html)

#### Pay Attention to Variable Naming
Incorrect naming can significantly impact your code readability!
```java
// Bad naming:
int[][] m = new int[x][y];
int[] d = getDiagonal(m);

// Good naming:
int[][] matrix = initializeMatrix();
int[] diagonal = getDiagonal(matrix);
```
