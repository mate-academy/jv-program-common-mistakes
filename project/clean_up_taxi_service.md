# Taxi service cleanup

1. You must [create a new repo](add_video_about_it) with project collected from tasks from JDBC and Web modules.
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
