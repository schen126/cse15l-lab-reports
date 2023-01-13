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
>> I could not get through step 11, even though I reset my password twice and waited for 15+ minutes each time for the password to take effect. I kept getting this error:
>> ![image](https://user-images.githubusercontent.com/86854157/212216927-b49dff72-e97d-49c9-8136-564995e2d3d7.png)
>> Unfortunately, this means I wasn't able to complete Step 3 of the lab report (Part 5 on the weekly lab tasks)

# Trying Some Commands
