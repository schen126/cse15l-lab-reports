## Lab Report 2
*By Serena Chen*

---
# Part 1: StringServer 🧶🖥️
I started by copying the [code](https://github.com/ucsd-cse15l-f22/wavelet) provided by Professor Politz during Lab 2 into a new repo so I could edit it, which included the code for [`Server.java`](https://github.com/ucsd-cse15l-f22/wavelet/blob/master/Server.java) and [`NumberServer.java`](https://github.com/ucsd-cse15l-f22/wavelet/blob/master/NumberServer.java). The former would build a web server using HttpServer, and the latter would actually handle URL requests. I copied and used `Server.java` as is, but renamed and edited `NumberServer.java` to handle Strings instead of numbers.
As I was working on a new computer that did not have GitHub Desktop installed, I followed the following steps:
1. Go to [GitHub's website](https://desktop.github.com/) and download the `.exe` file to install the app
<br /> <p align="center"> <img src="https://user-images.githubusercontent.com/86854157/215649461-98bb374c-d6c9-456f-be49-f35e8dd47bdb.png" width="400"> </p> <br />
2. After opening the app, log in to your account
3. Select a repository to clone, which will download a copy of that repo onto your local computer. In my case, I chose my `cse15L_lab_report_code` repo
![image](https://user-images.githubusercontent.com/86854157/215649703-0bfba983-a766-4619-943a-ef96196ee57d.png)
4. Following that, open the repo in Visual Studio Code ([download instructions](https://github.com/schen126/cse15l-lab-reports/blob/main/lab_report_1.md) in Lab Report 1)
> After making changes to the code locally, make sure to `push` the change so the main version (on GitHub) will be modified

![image](https://user-images.githubusercontent.com/86854157/215658365-1cb2a095-c7f9-4f2e-8bc1-32226499d756.png)
![image](https://user-images.githubusercontent.com/86854157/215658448-2cd5223e-13d3-4b27-a0a7-a743cc87973d.png)
![image](https://user-images.githubusercontent.com/86854157/215658497-47016698-77aa-457c-b4ac-288f356799eb.png)
![image](https://user-images.githubusercontent.com/86854157/215658539-85322495-9250-41e4-bdad-66b5c7afc8c5.png)
![image](https://user-images.githubusercontent.com/86854157/215658770-46cf8116-9eda-4678-aa26-89e7d5350151.png)

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


# Part 2: Bugs  🐛🐛🐛

# Part 3: New Discoveries 🔎
