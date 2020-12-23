### Common mistakes

__first part__

#### Follow SOLID rules
Please design your classes according to the SOLID principles. Make your classes simple, reusable and focused on a single problem.
In this case you will save a lot of time when you need to add/modify existing functionality in the future.
#### Don't keep all logic in a single package
You can use packages to make the structure of the code better, so let's do it. Gather classes with same 
 purpose/common logic in a corresponding package.
#### VSC usage
Remember about informative commit and PR naming. Person that is outside of context of your work progress should understand
what feature/functional you have added.
#### Don't ignore exceptions in try-catch blocks
Don't leave `e.printStackTrace()` or `System.out.println(e.getMessage())` at the catch blocks. 
Let's rethrow a RuntimeException() with informative message and exception object.

    Good:
    ```
    } catch (FileNotFoundException e) {
        throw new RuntimeException("Can't find file by path: " + filePath, e);
    }
    ```
#### Follow the encapsulation principle
Hide inner class elements with the help of access modifiers. It's a bad practice to make your class exposed.
#### Use data structures from the Collection framework
In order to represent fruit storage you may use already existing data structures, think of the one that will be 
the most suitable for your needs.
#### Show how your solution works
Let's create `main()` to show how the program works.
#### Avoid hardcode in your solution
* Use hardcoded values only in the Main class and/or test classes.  
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
#### Strive to have most of the functionality covered with tests
Ensure you have covered at least 80% of code with tests. That will decrease a chance of getting unexpected behaviour 
after software release and during maintenance stage.
You can check this requirement by `running your tests with coverage` (see this [tutorial](https://www.loom.com/share/85886cc0b3c9458a8b5c0d5af9bf4720))
or run `mvn clean verify` in the terminal.
#### Don't keep all tests in a single class
Create a corresponding test class for each class you test. Do not test logic of whole program in one test class.
That's important for code readability.
    Example:  
    ```  
    CsvFileService -> CsvFileServiceTest  
    FruitService -> FruitServiceTest  
    ...  
    ```  
Same goes for files that you use in tests, let's save them into folder: `src/test/resources/[your-files.csv]`   
#### Try to cover different scenarios in tests
Your task is to include edge cases apart from regular method use case. But we want to test only business logic,
no need to cover `Main` class with tests. You can exclude Main class with `main()` method from check for code coverage in pom.xml.   
__Example__: find the following code in the pom.xml and change `Main` according to your 
    class naming where you have your `main()` method.  
    ```  
    <configuration>  
        <excludes>  
            <exclude>**/Main*</exclude>  
        </excludes>  
    </configuration>  
    ```  
After all tests have passed you can send your solution)  
