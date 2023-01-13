## Week 1 Lab Report
*By Serena Chen*

---
# Installing VSCode
I actually already installed VSCode before for CSE 11, but I remember the steps are like this:
1. Go to the [Visual Studio Code Website](https://code.visualstudio.com/) and click `Download for Windows`
![image](https://user-images.githubusercontent.com/86854157/212214825-fa8a6696-5b7a-4d1c-8c66-1bffc1683b97.png)
2. Click on the downloaded file
3. Allow the publisher to make changes to your computer
4. Select the default option for everything
5. Download VSCode and open it up!
![image](https://user-images.githubusercontent.com/86854157/212215489-915b56df-02f3-479a-9442-65c68c0a65cb.png)


>> I pinned VSCode to my taskbar for easier access.
>> ![image](https://user-images.githubusercontent.com/86854157/212215071-b41628a4-07a0-4b57-807f-dee1677fafbf.png)

---
# Remotely Connecting
>> I had a LOT of trouble with this step.
1. Look up your [CSE15L Account] (https://sdacs.ucsd.edu/~icc/index.php)
2. Reset your password with [these instructions](https://docs.google.com/document/d/1hs7CyQeh-MdUfM9uv99i8tqfneos6Y8bDU0uhn1wqho/edit)
>> Make sure to not change your MyTritonLink password as well

![image](https://user-images.githubusercontent.com/86854157/212216048-df305277-8c68-47d6-ad85-0c09d777ea5d.png)

3. Wait for 15 minutes for the password to take effect
4. In the meantime, download [Git](https://gitforwindows.org/) for Windows
![image](https://user-images.githubusercontent.com/86854157/212216147-e249c3ec-0808-4ded-a53e-09bf90b4fd62.png)
5. When installing Git, change the default from VIM to VSCode for one of the steps
6. Open a terminal in VSCode using `CTRL+``
7. Search for `Select Default Profile` in the Command Palette and select `Git Bash`
8. Click on the `+` icon in the terminal and add a new Git Bash terminal
![image](https://user-images.githubusercontent.com/86854157/212216519-264d2e39-685e-4d63-8ec3-f1ac8160baf1.png)
9. Type this command into the terminal, replacing `zz` with your CSE15L account username: ` $ ssh cs15lwi23zz@ieng6.ucsd.edu`
10. Select `yes` when the terminal asks you to verify your authenticity
11. Enter your password and you should be connected!
![image](https://user-images.githubusercontent.com/86854157/212259074-bc4ba714-71c2-4c47-86a1-3a070cd373ce.png)

>> I could not get through step 11 during the lab, even though I reset my password twice and waited for 15+ minutes each time for the password to take effect. I kept getting this error:
>> ![image](https://user-images.githubusercontent.com/86854157/212216927-b49dff72-e97d-49c9-8136-564995e2d3d7.png)
>> After a few hours, I tried it again. The system let me in after I refreshed my VSCode.

# Trying Some Commands
After connecting remotely to the CSE basement computer, there are many commands to try.
* `ls --help` - lists information about commands that can be used
![image](https://user-images.githubusercontent.com/86854157/212261007-45578841-5c2e-4d2a-93a8-7938eec35fc4.png)
* `ls` - lists the files in a directory
* `cd` - changes the directory
* `cd ~` - returns to the home directory
![image](https://user-images.githubusercontent.com/86854157/212261943-78543adb-4aad-49fa-9bad-c680e1f3e3f8.png)
* `cat /(location of the file)` - prints the content of a file
![image](https://user-images.githubusercontent.com/86854157/212262269-926df065-f86e-4c71-95e4-6d00114e4d74.png)
* `pwd` - prints the working directory
![image](https://user-images.githubusercontent.com/86854157/212263317-eb8408cd-c350-4cc3-94d7-b314581f6eae.png)
* `mkdir` - make a new directory
* `cp` - copies a directory
* `Ctrl-D` - exists the remote server
![image](https://user-images.githubusercontent.com/86854157/212263376-e265441d-b264-4cfd-9ba6-14aeec9095aa.png)
