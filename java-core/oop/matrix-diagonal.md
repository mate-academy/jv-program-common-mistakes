### Common mistakes

#### Use single loop instead of a nested one where possible
Algorithms with nested loops require more computational resources comparing to the ones with single loop. 
As a result you may receive performance degradation when overusing this approach. Always try to avoid nested 
loops where possible.

#### Follow checkstyle rules: 
```
Bad practice:
for(int i=0;i<array.length;i++){
if(array[i]>max)
max=array[i];
}
```
```
Refatored code:
for (int i = 0; i < array.length; i++) {
    if (array[i] > max) {
        max = array[i];
    }
}
```
[CheckStyle rules](https://google.github.io/styleguide/javaguide.html)

#### Variable naming
Incorrect naming may have significant impact on your code readability!  
```
Bad naming:
int[][] m = new int[x][y];
int[] d = getDiagonal(m);
```  
```
Good naming: 
int[][] matrix = initializeMatrix();
int[] diagonal = getDiagonal(matrix);
```  
