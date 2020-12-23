# HW 20

__first part__
* Please ensure you have designed your classes according to the SOLID principles. Make your classes are simple, reusable and focused on a single problem.
* You can use packages to make the structure of the code better, so let's do it.
* Remember about informative commit naming.
* Don't leave `e.printStackTrace()` or `System.out.println(e.getMessage())` at the catch blocks. 
Let's rethrow a RuntimeException() with informative message and exception object.

    Good:
    ```
    } catch (FileNotFoundException e) {
        throw new RuntimeException("Can't find file by path: " + filePath, e);
    }
    ```
* Remember about access modifiers!!!
* Consider using data structures from the Collection framework that you know to represent fruit storage.
* Let's create `main()` to show how the program works.
* Avoid hardcode in your code. Use hardcoded values only in the Main class and/or test classes.
    Bad:
    ```
    public class FileService {
        public void readFromFile() {
            File file = new File("src/main/resources/file.txt");
            ...
        }
    }
    ```
  
    Good:
    ```
    public class FileService {
        public void readFromFile(String filePath) {
            File file = new File(filePath);
            ...
        }
    }
    ```
* Use the absolute path to a resource: Everyone who pulls your project should be able to run it. Please provide the relative path to a resource instead.

    Bad:
    ```
    readFromFile("C:/Users/.../my-project/src/main/resources/file.txt");
    ```
  
    Good:
    ```
    readFromFile("src/main/resources/file.txt");
    ```
* Avoid using switch-cases and if-else constructions.
* Be attentive with [class](https://mate-academy.github.io/style-guides/java/java.html#s5.2.2-class-names) 
and [method](https://mate-academy.github.io/style-guides/java/java.html#s5.2.3-method-names) naming. 

__second part__
* Ensure you have covered at least 80% of code with tests.  
You can check this requirement by `running your tests with coverage` (see this [tutorial](https://www.loom.com/share/85886cc0b3c9458a8b5c0d5af9bf4720))
or run `mvn clean verify` at the terminal.
* Create a corresponding test class for each class. Do not test logic of whole program in one test class.
    
    Example:
    ```
    CsvFileService -> CsvFileServiceTest
    FruitService -> FruitServiceTest
    ...
    ```
* Don't test `main()` method.
* Make sure all your tests pass before submitting your solution.
* Don't forget to check edge cases in your tests.
* Let's save the files used for tests in a folder: `src/test/resources/[your-files.csv]`
* You can exclude Main class with `main()` method from check for code coverage in pom.xml. 
    
    __Example__: find the following code in the pom.xml and change `Main` according to your 
    class naming where you have your `main()` method.
    ```
    <configuration>
        <excludes>
            <exclude>**/Main*</exclude>
        </excludes>
    </configuration>
    ```
