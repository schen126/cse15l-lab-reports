## Week 4 Lab Report
*By Serena Chen*

---
**Setup**
1. Delete existing forks of the repository on your account
* Use `rm -r [file name]` to delete the repository
3. Fork the repository
5. Start the timer

**Numbered Steps**
4. Log into `ieng6`
`ssh cs15lwi23username@ieng6.ucsd.edu`
`<enter>`
>> This will log you into your remote account

5. Clone your fork of the repository from your Github account
`clone git@github.com:schen126/lab7.git`

6. Run the tests, demontrating that they fail
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit/runner.JUnitCore ListExamples.java
```

7. Edit the code to fix the failing test
```
nano ListExamples.java
<Ctrl>+o
<Ctrl>+x
```

8. Run the tests, demonstrating that they now succeed
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit/runner.JUnitCore ListExamples.java
```

9. Commit and push the resulting change to your Github account
 ```
 git add ListExamples.java
 git commit
 git push
 ```
