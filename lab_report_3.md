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
**Example 1**
```
[cs15lwi23avc@ieng6-202]:berlitz2:347$ grep "MONDAY" Paris-WhereToGo.txt
[cs15lwi23avc@ieng6-202]:berlitz2:348$ grep -i "MONDAY" Paris-WhereToGo.txt
Situated 64 km (40 miles) southeast of Paris by the A6 or by train from Gare de Lyon and then bus to the château. Bus tours from Paris are available. Open Monday, Wednesday– Sunday 9:30am–12:30pm, 2–5pm. Entrance free first Sunday of the month. Closed Tuesday.
Situated 85 km (53 miles) northwest of Paris by the A13, D181, and D5, or by train from Gare St-Lazare to Vernon with a shuttle bus from the station to Giverny. The house is open April–October, Tuesday–Sunday 10am–noon, 2–6pm, the gardens all year Tuesday–Sunday 10am–6pm; closed Monday. The best time to go is in the early morning (to beat the crowds) during the spring (for the most impressive flower displays).
Located 6 km (4 miles) west of Paris. Métro: Grande Arche de La Défense, then bus 258, or RER to rueil-Malmaison, and then walk. Open Monday, Wednesday–Sunday 10:30am– noon, 1:30–5:30pm (4:30pm in winter). Closed Tuesday.
Versailles is situated 24 km (15 miles) southwest of Paris, by road (N10); or by train from Gare St-Lazare to Versailles; or by RER (line C5) to Versailles-Rive Gauche; or by métro to Pont de Sèvres, then bus 171. The château is open Tuesday–Sunday 9am–6:30pm (winter 5:30pm); the Grand and Petit Trianon Tuesday–Sunday 10am–6:30pm (Tuesday–Friday 10am–12:30pm and 2–5:30pm, Saturday and Sunday 10am–5:30pm in winter); the gardens Tuesday–Sunday 7am to sunset. Entrance free first Sunday of the month. Closed Monday.
```

![image](https://user-images.githubusercontent.com/86854157/218550582-bbedc362-cdb9-44ba-b26e-aa8999183c03.png)

In the first line, I look for the phrase "MONDAY" in the file `Paris-WhereToGo.txt`. It returns nothing, because the string "MONDAY" in all caps does not exist. However, using -i, I can search for "MONDAY" in a case insensitive fashion, so I can also see where strings like "Monday" are. This is useful if you want to find a word, but don't particularly care how that word is formatted in recards to capitalization.

**Example 2**
```
[cs15lwi23avc@ieng6-202]:berlitz1:360$ grep "Asia" WhereToGreek.txt
        heart of central Asia, south through the Aegean. The summer season is
        culture, and see the majestic ancient archaeological sites of old Asia[cs15lwi23avc@ieng6-202]:berlitz1:361$ grep -i "Asia" WhereToGreek.txt        heart of central Asia, south through the Aegean. The summer season is
        Thirasia now has separate settlements that can be visited by ferry from
        islands of Nea and Palea Kameni. Allow time in Thirasia to explore        culture, and see the majestic ancient archaeological sites of old Asia
```

![image](https://user-images.githubusercontent.com/86854157/218552054-296ccf1d-8894-42e2-90fb-6e2fc9637797.png)

When searching for "Asia," `grep` only returned phrases pertaining to Asia the continent. However, searching for "Asia" in a case-insensitive fashion returned places like "Thirasia" as well.

# Command Variation 2: `-n`
[`grep -n`](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) allows the user to search within a file for a certain phrase, then show the line number of the file in addition to the line matched. 
The syntax for `grep -n` is `$ grep -n "[phrase]" [file]`

**Example 1**
```
[cs15lwi23avc@ieng6-202]:berlitz1:365$ grep -n "place" WhatToJapan.txt
41:        In Tokyo, the place to go for every electronic and computer
205:        was not yet frowned upon. So they were in turn replaced by older men.
287:        festivals and ceremonies taking place annually, this entire book
355:        festivals held throughout Japan. The best place to view the spring
```

![image](https://user-images.githubusercontent.com/86854157/218553020-89f97172-357f-4b9a-b200-6d1e5dc7e648.png)

Using `grep -n`, I can see the line number where `grep` found each occurence of the phrase I'm looking for. This is useful if you're searching for a word in a huge text file, and need to know exactly where to scroll to, to find the line. 

**Example 2**
```
[cs15lwi23avc@ieng6-202]:berlitz1:366$ grep -n pyramid IntroEgypt.txt
21:        purpose of the pyramids fill the stands of bookshops and the listings
29:        paintings breathtaking, the pyramids prodigious, and the huge temple
```

![image](https://user-images.githubusercontent.com/86854157/218553672-1f2f80a2-c959-4374-b45b-c695a7271454.png)

I can see that the phrase "pyramid" occurs twice, once in line 21, and once in line 29. 

# Command Variation 3: `-v`
["grep -v"](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) allows the user to search for lines that don't contain a specific string.
The syntax is `$ grep -v "[phrase]" [file]`

**Example 1**
```
[cs15lwi23avc@ieng6-202]:berlitz1:379$ grep -v "a" WhereToHongKong.txt





        Where to Go
        commerce.
        ground floor.
        offices).
        To the Summit
        month.
        time.
        Western District
        The Western District is one of Hong Kong’s oldest
        more.
        period.
        old premises.
        thriving.
        opportunity.
        redevelopment.
        summer long.
        Kowloon
        mile).
        Chinese culture.
        housing project.
        New Territories
        beyond.
        fortune.
        Sheung Shui.
        One of the most interesting sites in the New Territories is
        30 minutes.
        ”
        intrigue.
        little more like Hong Kong.
        Arriving
        objects.
        Trying Your Luck
        border.
        hotels.
        116).
        stories, which will often be pointed out to you.
        hotel.
        An Excursion to Shenzhen
        Kong.
        economic zone.
```
Using `grep -v`, I can get every line from the file `WhereToHongKong.txt` that does not contain "a." As you can see, this mostly consists of lines with very few letters.

**Example 2**
```
[cs15lwi23avc@ieng6-202]:berlitz1:385$ grep -v "a" IntroLasVegas.txt





        the desert.
        tomorrow, who knows?
        thirsty pioneers.
        1905.
        growing up in “Sin City. ”
        hustle.
        glittering moments.
        
        
        
```

![image](https://user-images.githubusercontent.com/86854157/218557277-7c34c974-aea7-4f3c-b28c-107ed1123f88.png)

As you can see, there are many lines that seem to be blank. This is because empty lines do not contain "a," so they will be listed as well. `grep -v` can be useful if you're trying to do an inverse search.

# Command Variation 4: `-A n`
[This command](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) will print the searched line and `n` lines after the result. For example, looking for `grep -A3 "Hello World!' somefile.txt` would print out each occurence of "Hello World!" in `somefile.txt`, each of which would be followed by the three lines after the line in which the phrase was found.
The syntax is: `$grep -A[number of lines n] [phrase] [file]`

**Example 1**
```
[cs15lwi23avc@ieng6-202]:berlitz1:389$ grep -A3 city IntroLosAngeles.txt 
        is preceded by its reputation. Here is a city teeming with movie stars,
        exorbitant wealth, sunny beaches, palm trees, and beautiful people. But
        L.A. is also linked with adventure and maybe even danger, complete with
        earthquakes, floods, crime, and scandals of O. J. Simpson proportions.
--
        Los Angeles. The city is not merely beautiful coastlines, hit TV shows,
        opulent mansions in the hills, and the latest in celebrity gossip. Los
        Angeles County is a collection of 88 separate, incorporated cities
        packed between the Pacific Ocean and Orange and San Bernardino
        counties. Many of these towns have their own city halls, police forces,
        and fire brigades.
        The result is that L.A. is a place without a geographic
        heart, but with lots of soul. If its soul is superficial, flighty, and
```

![image](https://user-images.githubusercontent.com/86854157/218558171-afd0f49e-23b8-46e0-972d-e236c1cf646a.png)

Using `A -n`, I can get some of the context for the phrase "city" in the file `IntroLosAngeles.txt`. This is useful if you're trying to find out in what specific situation a phrase is being used.


**Example 2**
```
[cs15lwi23avc@ieng6-202]:berlitz1:392$ grep -A5 "great vacation" WhatToEgypt.txt
        with Egyptians and make great vacation activities. Camel rides and
        treks can be taken around the pyramids, at Luxor and Aswan; at every
        resort in the Sinai and on the Red Sea coast. Horseback-riding is also
        well organized in the Sinai and the Red Sea, less so along the Nile
        Valley.
        Other sports: If you feel the need to work up a sweat while
```

![image](https://user-images.githubusercontent.com/86854157/218558811-ec3f8313-3cdc-4f33-b8f5-4acee199dbef.png)

By searching with this command for "great vacation," I can see that this part of the file is discussing vacation activities in Egypt, including camel rides and horseback riding.

# Sources
* [GeeksForGeeks - Grep Command in Unix/Linux](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)
* [OpenAI - ChatGPT](https://openai.com/blog/chatgpt/)
* [Wikipedia - Grep](https://en.wikibooks.org/wiki/Grep)
