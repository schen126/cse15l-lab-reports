## Week 4 Lab Report
*By Serena Chen*

---
**Setup**
1) Delete existing forks of the repository on your account
![image](https://user-images.githubusercontent.com/86854157/221533090-e1bbb7d1-1d7c-4aee-8ab1-32783f5be427.png)

>> Use `rm -r [file name]` to delete the repository

2) Fork the repository
3) Start the timer


**Numbered Steps**

4) Log into `ieng6`
![image](https://user-images.githubusercontent.com/86854157/221532092-96ed734d-f2ec-42c9-8eee-54e1239e5644.png)


Keys pressed: `ssh cs15lwi23username@ieng6.ucsd.edu<enter>`

Command: `ssh cs15lwi23username@ieng6.ucsd.edu`
>> This will log you into your remote account. Because I configured the account with ssh-keygen during setup, I didn't need to enter a password and it automatically logged me in.

5) Clone your fork of the repository from your Github account
![image](https://user-images.githubusercontent.com/86854157/221534801-854861b0-865c-484d-a8aa-5e73b3b8fbb2.png)
![image](https://user-images.githubusercontent.com/86854157/221533885-93bf2a9f-58a3-440b-9213-53b3267e155e.png)

Keys pressed: `git clone <Ctrl>v<enter>`

Command: `git clone git@github.com:schen126/lab7.git`
>> Since I went to my Github page for `lab7` and copied the `ssh` key for a local clone, I just pasted it directly onto my terminal.

6) Run the tests, demontrating that they fail
![image](https://user-images.githubusercontent.com/86854157/221540020-c24c1998-29e2-469e-9586-cf1f15cce13a.png)

Keys pressed: `cd lab7, <Ctrl>c<Ctrl>v<enter>, <Ctrl>c<Ctrl>v<enter>`

Command(s):
```
cd lab7
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit/runner.JUnitCore ListExamplesTests
```
>> As I was in my home directory in my remote account, I changed the directory to the `lab7` directory so I could access the java files. Since I already typed the commands out on a separate notepad, I just copied and pasted the commands into the terminal.

7) Edit the code to fix the failing test
![image](https://user-images.githubusercontent.com/86854157/221538367-815abc25-c047-41ca-9abe-930bf2062585.png)
![image](https://user-images.githubusercontent.com/86854157/221537603-7fe4bf3d-1f0b-4892-bb54-f3582cfaa0ca.png)

Keys Pressed: `nano ListExamples.java<enter>, <down>*42, <right>*12, <backspace>, 2, <Ctrl>o<enter>, <Ctrl>x`

Command(s):
```
nano ListExamples.java
<Ctrl>o
<Ctrl>x
```
>> Because the tests failed, we have to fix the code. To edit the code from the terminal, we can use the `nano` command, which will send us to a screen where we can change the code. Using the arrow windows, we can navigate to the error on line 43 and change `index1` to `index2`, which will fix the error. Afterwards, <Ctrl>o will save the change, and <Ctrl>x will exit the editor.

8) Run the tests, demonstrating that they now succeed
![image](https://user-images.githubusercontent.com/86854157/221539165-ecdc46e6-ea22-401d-a22e-b9e67dd4daf0.png)

Keys pressed: `<up><up><up><enter>, <up><up><up><enter>`

Command(s):
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit/runner.JUnitCore ListExamplesTests
```
>>Because I used the same commands in Step 6 earlier, the `javac` and `java` commands were already stored in my history. Therefore, I could access these commands by pressing the up arrow on the terminal.

9) Commit and push the resulting change to your Github account
![image](https://user-images.githubusercontent.com/86854157/221541613-77f69e33-9a17-45d8-a090-6cb3966788b9.png)

Keys pressed: `git add ListExamples.java<enter>, git commit -m "Without bugs"<enter>, git push<enter>`

Command(s):
 ```
 git add [file]
 git commit -m "message"
 git push
 ```
 >> `git add` adds `ListExamples.java` to the list of files to be committed, `git commit` commits the changes, and `git push` pushes these changes to Github.
