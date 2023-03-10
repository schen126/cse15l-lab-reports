## Lab Report 2
*By Serena Chen*

---
# Part 1: StringServer 🧶🖥️
I started by copying the [code](https://github.com/ucsd-cse15l-f22/wavelet) provided by Professor Politz during [Lab 2](https://ucsd-cse15l-w23.github.io/week/week2/) into a new repo so I could edit it, which included the code for [`Server.java`](https://github.com/ucsd-cse15l-f22/wavelet/blob/master/Server.java) and [`NumberServer.java`](https://github.com/ucsd-cse15l-f22/wavelet/blob/master/NumberServer.java). The former would build a web server using HttpServer, and the latter would actually handle URL requests. I copied and used `Server.java` as is, but renamed and edited `NumberServer.java` to `StringServer.java` to handle Strings instead of numbers.
As I was working on a new computer that did not have GitHub Desktop installed, I followed the following steps:
1. Go to [GitHub's website](https://desktop.github.com/) and download the `.exe` file to install the app
<br /> <p align="center"> <img src="https://user-images.githubusercontent.com/86854157/215649461-98bb374c-d6c9-456f-be49-f35e8dd47bdb.png" width="600"> </p>
2. After opening the app, log in to your account
3. Select a repository to clone, which will download a copy of that repo onto your local computer. In my case, I chose my `cse15L_lab_report_code` repo
<br /> <p align="center"> <img src="https://user-images.githubusercontent.com/86854157/215649703-0bfba983-a766-4619-943a-ef96196ee57d.png" width="600"> </p>
4. Following that, open the repo in Visual Studio Code ([download instructions](https://github.com/schen126/cse15l-lab-reports/blob/main/lab_report_1.md) are in Lab Report 1)
> After making changes to the code locally, make sure to `push` the change so the main version (on GitHub) will be modified

I spent a while modifying `StringServer.java`, and ended up with this code:
<br /> <p align="center"> <img src="https://user-images.githubusercontent.com/86854157/215658770-46cf8116-9eda-4678-aa26-89e7d5350151.png" width="600"> </p>
Here's a closer look at my `handleRequest()` method, which is responsible for concatenating messages to one another and returning them to the user:
```
public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return messages;
        } else {
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    messages += "\n" + parameters[1];
                    return messages;
                }
            }
            return "404 Not Found!";
        }
    }
```
The main features are:
* The variable `messages` contains the concatenated Strings and newLines added by the user
* If the user only enters the main path, `messages` will be returned. If this is the first time the user is opening the server, the page will be blank
* If the user enters the `/add-message` path, the program will check if it is followed by `s`. If it is, the string entered by the user will be concatenated to `messages`
After coding the server, I ran the server using `javac Server.java StringServer.java` and `java StringServer 4001`. Upon starting the server and opening the link, I was given a blank page (meaning my `messages` variable is empty, as expected):
<br /> <p align="center"> <img src="https://user-images.githubusercontent.com/86854157/215659099-9f270f17-fdd1-4d00-b680-3866c2997ac1.png" width="400"> </p>
**Methods Used:** 
* `main`: The program checks for a port number. If one exists, a new `Handler` is created, and `handleRequest` is called.
* `handleRequest`: The URL is passed into `handleRequest`, which parses the url and returns a String for the website to print out
**Arguments:**
* `main` takes in `String[] args`, which is passed to the program from the Terminal from the user. `args[0]` should be the port number, which is `4001` in my case
* `handleRequest` takes `URI url`. In my case, it's `http://localhost:4001`
> The same methods and arguments repeat for every case I use. However, their values change, which is what I will be detailing.

In this first case, because `url`'s path is only a `/`, `messages` will return immediately. It is empty right now, so a blank screen will be shown.
In the second case, I use the command `/add-message?s-hello`, which will concatenate `hello` to `messages` through the `handleRequest()` method. Therefore, since this String is returned soon after, the text `hello` will be printed onto the screen.
<br /> <p align="center"> <img src="https://user-images.githubusercontent.com/86854157/215659139-a2947147-c40f-49f0-b6bd-6825ccaacbc9.png" width="400"> </p>
In the third case, I use the command `/add-message?s=1234`, which will concatenate `1234` to `messages`, which will then become `hello\n1234`. Even though `1234` is technically an integer, the program reads it in as a String, so it will be concatenated regardless.
<br /> <p align="center"> <img src="https://user-images.githubusercontent.com/86854157/215659180-2ca28a52-c11f-4437-a41f-ba2d0fc73fda.png" width="400"> </p>
Lastly, I entered a random string after the original url, which ended up being `http://localhost:4000/add`. Because `add` is not a keyword in this program, I received an error message. `messages` was not updated, so, theoretically, if I returned to `http://localhost:4000`, I should still see the message `hello\n1234`.
<br /> <p align="center"> <img src="https://user-images.githubusercontent.com/86854157/215659274-31717b9d-6d48-4edd-be8e-f1667fc98253.png" width="400"> </p>

# Part 2: Bugs  🐛🐛🐛
In [Lab 3](https://ucsd-cse15l-w23.github.io/week/week3/), we were given buggy files to study. Using tests to determine their outputs, we could then fix the bug. The code I'll be discussing is from the `ArrayExamples` class, specifically the `reversed()` function. 

**Failure-Inducing Input:**
Upon entering the array `{6, 5, 4}`, I received an error at `element 0`. Supposedly, the first element in the array should have become `4`, but it was `0` instead.
```
  @Test
  public void testReverseInPlace1() {
    int[] input1 = {6, 5, 4};
    assertArrayEquals(new int[]{4, 5, 6}, ArrayExamples.reversed(input1));
  }
 ```

**Non-Failure-Inducing Input:**
Upon entering the array `{0}`, I received `{0}`, which is the expected value.
```
  @Test
  public void testReverseInPlace2() {
    int[] input1 = {0};
    assertArrayEquals(new int[]{0}, ArrayExamples.reversed(input1));
  }
  
 ```
**Symptoms:**
![image](https://user-images.githubusercontent.com/86854157/215669941-8a03935a-4e04-440b-b2c8-b208e7e7ff2a.png)
![image](https://user-images.githubusercontent.com/86854157/215670074-a5303961-d2a0-4250-8eb4-9739db668d05.png)
> The second input didn't induce a failure so there are no symptoms.

**Bug:**

Before:
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
```
After:
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
```
The cause of the bug is that `arr`, which is the old array, was copying into `newArray`, or my supposed output. Since `newArray` is empty, this causes `arr` to become completely empty, while `newArray` is not changed at all. Since I end up returning `arr`, I just end up returning an empty array of all 0's. To fix this, I changed all the instances of `newArray` into `arr`, and vice versa.

# Part 3: New Discoveries 🔎
Before Lab 2, I didn't know much about servers, including what they were, how they worked, and what inputs they took in. When I studied `NumberServer.java`, I realized that url's belong to a type called `URI`, and they include a path that tells the program what to do. Depending on what path the user enters into the search bar, the program will do something different, which can be anything from incrementing a number to printing out a picture. 

After completing the lab assignment, I can make my own server and even customize the paths it would use to execute commands. This would allow me to create my own servers if I ever wanted to make an online resume or Zoom meeting tracker, which I think is super fascinating. Though I'd have to study more on how to format a web server in a more aesthetic way, the possibilities are endless!
