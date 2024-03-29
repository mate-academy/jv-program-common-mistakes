# Taxi service cleanup
Taxi project will be added as a reference project to your CV. This project should be located in a newely created GitHub repo. The below you can find the instructions how to create a repo and the clean up your project.
See instructions how to move source code from last HW (Web security topic) [here](https://youtu.be/3HHoJ_YZu6w).

1. Create a new repo on GitHub. See instructions [here](https://dou.ua/forums/topic/28895/).
2. Remove `Main` class.
3. Add README with project description.
4. If your code repeats several times inside of a class, move it to separate method.
5. Check your method signatures and remove `throws Exception` if your code cannot throw this exception.
6. Do not ignore Intellij Idea hints, read and fix them where applicable.
7. Go over your whole project, if you have variables/methods/fields that are never used don’t forget to remove them.
8. Check all url-mapping in project.
9. Add logger to your project: 
    - you can log some information in the AuthenticationService about correct or incorrect login.
    - relative path to `.log` file can not work, so use absolute path instead and add notes about it in the `README.md` file. 
10. Remove from project commented code, sout, `e.printStackTrace()` or replace them with logger.
11. Don't push `log` folder, `target`, `.iml` to GitHub (add them to `.gitignore` before committing any code).
12. Remove mentions of mate from pom.xml.
13. Replace real values with stubs in ConnectionUtil.
14. We recommend you to install this [plugin](https://chrome.google.com/webstore/detail/grammarly-for-chrome/kbfnbcaeplbcioakkpcpgfkobkghlhen?hl=en), 
especially if your level English isn't quite high, to decrease amount of possible errors during the writing of Readme.
15. Check all you dao classes and rename string variables with a query to just "query" and objects of PreparedStatement 
to "statement" because their context is already indicated in the method name.
