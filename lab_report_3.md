## Week 2 Lab Report
*By Serena Chen*

---
For my lab report, I'll be talking about the `grep` command. According to [GeeksForGeeks](https://www.geeksforgeeks.org/grep-command-in-unixlinux/), `grep` stands for "**g**lobal search for **r**egular **e**xpression and print out." It allows the user to search for a pattern in files, then display the results. And according to [ChatGPT](https://chat.openai.com/chat), the "powerful command-line utility" can be modified in many ways to change its behavior.

![image](https://user-images.githubusercontent.com/86854157/218420441-7cb1785a-967d-4f52-af2e-30105e4ae500.png)

To use `grep`, the correct syntax is `grep [options] pattern [files]`.
>> Beyond adding the sources I use as hyperlinks within my lab report, I'll also compile a short [bibliography](https://github.com/schen126/cse15l-lab-reports/blob/main/lab_report_3.md#sources) at the end so it's easier for me to track my sources.
>> Also, I will use `[brackets]` to indicate that this blank should be filled in with the corresponding word, command line, or other variable. 

# Command Variation 1: `-i`
[`grep-i`](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) allows the user to search for a string in a case-insensitive fashion. Therefore, searching in a file with a string like "cats" could return "cAts," "CATS", "caTS," or any other variation of the same word.
The syntax for `grep -i` is `$grep -i "[phrase]" [file]`

# Command Variation 2: `-n`
[`grep-n`](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) allows the user to search within a file for a certain phrase, then show the line number of the file in addition to the line matched. This is useful if you're searching for a word in a huge text file, and need to know exactly where to scroll to, to find the line. 
The syntax for `grep -n` is `$ grep -n "[phrase]" [file]`

# Command Variation 3: `^ and $`
The special characters [`^` and `$`](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) can be placed in the beginning and end, respectively, of a phrase to specify where the program should be looking for this pattern. `grep "^word"` is used to match the lines that start with the given string, while `grep "word$"` is used to match the lines that end with the given strings. 
The syntaxes are:
* `$grep "^[phrase]" [file]`
* `$grep "[phrase]$" [file]`

# Command Variation 4: `-A n`
[This command](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) will print the searched line and `n` lines after the result. For example, looking for `grep -A3 "Hello World!' somefile.txt` would print out each occurence of "Hello World!" in `somefile.txt`, each of which would be followed by the three lines after the line in which the phrase was found.
The syntax is: `$grep -A[number of lines n] [phrase] [file]`

# Sources
* [GeeksForGeeks - Grep Command in Unix/Linux](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)
* [OpenAI - ChatGPT](https://openai.com/blog/chatgpt/)
