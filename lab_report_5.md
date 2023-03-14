## Lab Report 5
*By Serena Chen*

---
My favorite lab report was `Lab Report 3`, which correlates to the lab in Week 4 (the document for our group can be found [here](https://docs.google.com/document/d/1W8dxYHgvIFSqXOY1R09R4HYT-B3YAbPKHE-gGwP9d4s/edit#heading=h.doiztlgw6k3t)). This [lab report](https://schen126.github.io/cse15l-lab-reports/lab_report_3.html) focused on the `grep` command, which is a powerful tool that allows the user to search for a pattern in files. Because of its many variations, I found it fascinating and very useful. In the [lab of week 4](https://ucsd-cse15l-w23.github.io/week/week4/), we looked for files in a directory using `grep`, and put this info into a script. To expand upon `Lab Report 3` and the lab in week 4, I'll first explore more commands with `grep`, then describe and review the process of the lab.

## Exploring More `grep` Commands [🕵️](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)
### `grep -w`
This command matches only the whole words, not substrings. The syntax for `grep -w` is `$grep -w "[string]" [file name]`

**Example:**
```
[cs15lwi23avc@ieng6-203]:berlitz2:516$ grep "home" Bahamas-Intro.txt 
The islands of the Bahamas were claimed by the English, but hundreds of secret coves became home to pirates and smugglers who turned their backs on nationality to enter the brotherhood of buccaneers. They ruled the seas, plundering ships at will, and then spent their ill-gotten gains in the bars and brothels of Nassau town, the main settlement.
The Bahamian people are among the friendliest you’ll ever meet, and they are eager to share the homeland they love with visitors. The population is a fascinating mixture of descendants of the Loyalist settlers who left America after the American Revolution, freedom lovers who escaped religious persecution, and ex-slaves set free following emancipation. This mixture, which could have produced a society fraught with problems, has evolved into a gentle, sociable, and happy people, proud of their homeland and the progress they have made since independence in 1973. With a stable economy, good health, and no taxes, it’s no wonder that a smile comes naturally to all Bahamians. All the communities still have strong religious faith, the pretty churches are full on Sundays, and a conversation about some future event always ends with “…God willing” or “…with the Lord’s blessing.”
To make the most of your trip you’ll need to tune your mind to “Bahamian time.” On New Providence and Grand Bahama this may not be much slower than at home, but on the Out Islands, time definitely runs more slowly, and nothing is so important that it can’t wait a while. People are more important than to-do lists, so a leisurely exchange of greetings and an inquiry about your family’s well-being precedes any business activity. This genuine thoughtfulness also extends to visitors; someone will always go out of their way to be helpful, in ways that have been lost in more developed locations.
[cs15lwi23avc@ieng6-203]:berlitz2:517$ grep -w "home" Bahamas-Intro.txt 
The islands of the Bahamas were claimed by the English, but hundreds of secret coves became home to pirates and smugglers who turned their backs on nationality to enter the brotherhood of buccaneers. They ruled the seas, plundering ships at will, and then spent their ill-gotten gains in the bars and brothels of Nassau town, the main settlement.
To make the most of your trip you’ll need to tune your mind to “Bahamian time.” On New Providence and Grand Bahama this may not be much slower than at home, but on the Out Islands, time definitely runs more slowly, and nothing is so important that it can’t wait a while. People are more important than to-do lists, so a leisurely exchange of greetings and an inquiry about your family’s well-being precedes any business activity. This genuine thoughtfulness also extends to visitors; someone will always go out of their way to be helpful, in ways that have been lost in more developed locations.
```
![image](https://user-images.githubusercontent.com/86854157/224887532-18819726-0a61-432b-ac29-f50b246fe301.png)
When using just `grep`, words like "homeland" will be printed out as well if we search for the word "home". However, when using `grep -w`, only lines containing the word "home" will be printed.

### `grep -o`
This command prints only the matched string, not the entire line as is the default of `grep`. The syntax for `grep -o` is `$grep -o "[string]" [file name]`

**Example:**
```
[cs15lwi23avc@ieng6-203]:berlitz2:523$ grep "place" Athens-Intro.txt
In the latter years of the 20th century very little was done to improve matters. The population grew but the infrastructure was not developed, resulting in gridlock of the urban traffic system, smog, and noise pollution. Today, at first glance nothing seems to have changed. A brown layer of pollution hangs over the city in both hot and cold weather; the seemingly endless hooting of horns down the wide boulevards and the drone of vehicles making painfully slow progress through the narrow streets raises noise levels; and in a city with so many apartments and so little parking it’s no surprise that sidewalks become places to leave your vehicle, and pedestrians must risk life and limb by walking on the roads.
Tradition still plays an important part in daily life here. The family forms the backbone of Greek society and filial ties are strong. Children play safely in the streets with grandma keeping a watchful eye. New babies are proudly shown to the world in the evening volta or stroll, when neighbors come to “bill and coo.” Families gather for a weekend meal, taking over a corner of a taverna to spend a couple of hours in noisy debate (some may say argument) while perhaps having a little food. Eating always takes second place to conversation at a Greek meal. Greek hospitality is warm and genuine — even small examples such as always being welcomed with a smile and shown to your seats at a taverna. Shopkeepers are skilled salesmen, but never pushy or overbearing.
Tourism also continues to flourish at the dawn of the 21st century. It is Greece’s major foreign currency earner with 11 million people visiting every year. Athens is an international melting pot with people of many nationalities treading the marble steps of the Acropolis to gaze at the birthplace of Western civilization. In 2004 the Olympic Games, first held in Greece during ancient times, will return to the capital giving Athens the chance to stand in the limelight again. The city offers some of the most fascinating and alluring archaeological remains in the world, yet those who visit in the 21st century find that the modern city works hard to live up to the past.
[cs15lwi23avc@ieng6-203]:berlitz2:524$ grep -o "place" Athens-Intro.txt 
place
place
place
```
![image](https://user-images.githubusercontent.com/86854157/224888267-51d081aa-23bf-447b-8b8b-35d8f6a52260.png)
When using `grep`, the entire line containing the word "place" is printed. However, by using `grep -o`, only the words containing "place" will be printed, which is three occurences. 

### `grep -l`
This command displays the files that contain the string/pattern. The syntax for `grep -l` is `$grep -l "[string]" [files or directory you wish to search through]`

**Example:**
```
[cs15lwi23avc@ieng6-203]:berlitz2:534$ grep "purple" *
Algarve-Intro.txt:Despite the region’s ancient roots, few historic monuments survive from before 1755, when the Algarve was rocked by a monumental earthquake that took thousands of lives and leveled buildings as far north as Lisbon. Still, you’ll find vestiges of a vibrant past, including evocative castle ruins and churches with extraordinary displays of Portuguese glazed tiles. Even the humblest village has a classic white church, a sleepy plaza shaded by vivid purple jacaranda, and, if you time it right, the drama of the local market.
California-WhereToGo.txt:Of all the wonders of California, the high desert is perhaps the greatest surprise. The desert is no monotonous expanse of sand dunes, but a beautiful, variegated land full of color and space. In summer it is a bizarre landscape of jagged rock and gravel, naked mountains and salt lakes, baked and shimmering in the desert heat. Go in winter and you may see drifts of spring flowers blooming in the wake of the sparse rains that make it over the snow-dusted Panamint Mountains in the west. Unhidden by vegetation, the colors of the rocks — brick red, ochre, green, and purple-brown — are dramatically deepened at sunset and dawn, creating unforgettable views.
California-WhereToGo.txt:On the way back toward Furnace Creek lies Artist’s Drive, where the road (one way only from south to north) carves its path through a canyon of multi-colored rocks, culminating in the very aptly named Artist’s Palette. Here, oxidization has turned the rocks bright mauve, ochre, green, vermilion, turquoise, and purple.
Canada-WhereToGo.txt:“Bald point,” as French explorers dubbed it, is the southern half of a 20-km (12-mile) sandspit jutting out into Lake Erie. Its terrain is a mixture of marshland, forest, meadows, and sandy beaches. Beginning with a lookout tower for bird-watchers, a circular boardwalk takes you out onto the marshes to observe the flight of the redwing blackbird and purple martin, while bittern stay tucked away in the reeds. Look, too, for the pretty pink-blossomed swamp rose-mallow, unique to Point Pelee. Well-marked bicycle and hiking trails wind through the woods, where you’ll see hackberry, sassafras, sycamore, black walnut, and red cedar, many of the trees draped with hanging vines reminiscent of the American Carolinas.
China-WhereToGo.txt:Although “Yellow Mountain” is the literal translation of Huangshan (which is not one mountain but a range of dozens of peaks), yellow is not the color that first comes to mind when describing this romantic site that has been the subject of Chinese poetry and painting for centuries. In reality, green is the color of the stunted pines clinging to purple cliff faces. Pink are the wildflowers, blue the sky, and white the sea of clouds that rolls in beneath the rocky pinnacles.
[cs15lwi23avc@ieng6-203]:berlitz2:535$ grep -l "purple" *
Algarve-Intro.txt
California-WhereToGo.txt
Canada-WhereToGo.txt
China-WhereToGo.txt
```
![image](https://user-images.githubusercontent.com/86854157/224888994-997ca61a-7dc4-411d-ba0b-23c134d0b55c.png)
Using `grep` prints out all the lines with the word "purple", while `grep -l` prints out the file names of the files containing the word "purple".

### `grep -h`
This command displays the matched lines but not the file names. The syntax for `grep -h` is `$grep -h "[string]" [file name]`

**Example:**
```
[cs15lwi23avc@ieng6-203]:berlitz2:541$ grep "where to go" *
Barcelona-WhatToDo.txt:In the Eixample, Passeig de Gràcia and Rambla de Catalunya are great window-shopping streets, with some of Barcelona’s finest boutiques for fashion, jewelry, and home design. The nearby streets Mallorca, Valencia, and Provença are also overflowing with interesting shops. Avda. Diagonal, which cuts across Barcelona, has some of the finest and most expensive stores in Barcelona. It’s where to go if your tastes run to Armani and your wallet can catch up.
Costa-WhatToDo.txt:Flamenco: All the coastal resorts offer flamenco shows for tourists. These shows can be entertaining, but the performances are more show business than the true spirit of flamenco. To experience flamenco at its most authentic, you will have to search out bars and small clubs in Málaga or Sevilla. Ask the local tourist office for advice on where to go.
CostaBlanca-WhatToDo.txt:For more profound sea experiences, try scuba diving. Several centres provide all equipment, a dive boat, expert local knowledge, and sometimes tuition as well. A diving permit is required under Spanish law. Unless you speak reasonable Spanish and know where to go, let your chosen diving centre deal with the documentation.
CostaBlanca-WhatToDo.txt:Spain has always been famously rich in hunting and shooting possibilities, from wolf to wild boar — though the Costa Blanca is hardly the place for it. Tourist offices have a brochure, “Caza,” which gives more information about where to go for good hunting and how to obtain the necessary permits.      
Nepal-WhatToDo.txt:Deciding where to go will depend on the time available and your physical condition. Serious trekkers usually plan on spending two to three weeks or more on the trail. Five days to a week is about the minimum to have a fair sampling of trekking life (though only after about a week do you get your “trail legs”). Shorter outings around the Kathmandu Valley or the four-day “Royal Trek’’ out of Pokhara (which was followed by Prince Charles) afford great mountain views in season and are not to be disdained.
[cs15lwi23avc@ieng6-203]:berlitz2:542$ grep -h "where to go" *
In the Eixample, Passeig de Gràcia and Rambla de Catalunya are great window-shopping streets, with some of Barcelona’s finest boutiques for fashion, jewelry, and home design. The nearby streets Mallorca, Valencia, and Provença are also overflowing with interesting shops. Avda. Diagonal, which cuts across Barcelona, has some of the finest and most expensive stores in Barcelona. It’s where to go if your tastes run to Armani and your wallet can catch up.
Flamenco: All the coastal resorts offer flamenco shows for tourists. These shows can be entertaining, but the performances are more show business than the true spirit of flamenco. To experience flamenco at its most authentic, you will have to search out bars and small clubs in Málaga or Sevilla. Ask the local tourist office for advice on where to go.
For more profound sea experiences, try scuba diving. Several centres provide all equipment, a dive boat, expert local knowledge, and sometimes tuition as well. A diving permit is required under Spanish law. Unless you speak reasonable Spanish and know where to go, let your chosen diving centre deal with the documentation.     
Spain has always been famously rich in hunting and shooting possibilities, from wolf to wild boar — though the Costa Blanca is hardly the place for it. Tourist offices have a brochure, “Caza,” which gives more information about where to go for good hunting and how to obtain the necessary permits.
Deciding where to go will depend on the time available and your physical condition. Serious trekkers usually plan on spending two to three weeks or more on the trail. Five days to a week is about the minimum to have a fair sampling of trekking life (though only after about a week do you get your “trail legs”). Shorter outings around the Kathmandu Valley or the four-day “Royal Trek’’ out of Pokhara (which was followed by Prince Charles) afford great mountain views in season and are not to be disdained.
```
![image](https://user-images.githubusercontent.com/86854157/224889292-04761219-0d25-4a0b-8fd9-92f02a325133.png)
`grep` prints out the file that each line is included in, and `grep -h` prints out the lines but without the file name in the front.

## Week 4 Lab: How to Analyze a Text File [🗎](https://ucsd-cse15l-w23.github.io/week/week4/)
During this lab, we use command-line tools to search through directories with text files. To test these commands, I'll be using the same source as the lab, which is a [sample of writing in English from the OANC](https://anc.org/data/oanc/download/). 
First, we tried the command `find written_2/`, which allowed us to find files within a directory with the same name.
![image](https://user-images.githubusercontent.com/86854157/224893065-9200e6e3-2464-484e-afc3-4d024905c182.png)

Then, we learned the `>` command, which allows us to redirect output. By using it in `find written_2/ > find-results.txt`, we were able to redirect the output of `find written_2`, which includes all the files in the folder, into a text file called `find-results.txt`.
![image](https://user-images.githubusercontent.com/86854157/224893099-41fc6a15-29d4-49f8-bcc5-e0603e4512da.png)

Using the command `less`, we can print out fewer files at the same time with `find`. By scrolling with up and down arrows, and pressing `q` to quit, we can treat the output like a digital book to flip through. One usage example is `less find-results.txt`.

`wc` allows us to count the number of words in a file. Using `wc find-results.txt`, we can see how many words are in this file. 
![image](https://user-images.githubusercontent.com/86854157/224893292-d7ca0b99-6677-48ae-9667-8c8ffb569447.png)

However, when searching for files with `find written_2/`, it doesn't just include addresses to `.txt` files, but addresses to the directories that these .txt files are contained in. An alternative is using `grep ".txt" find-results.txt`, which will specifically find lines ending in `.txt` within `find-results.txt`. By redirecting the output into a file using `grep ".txt" find-results.txt > grep-results.txt`, then doing `wc grep-results.txt`, we can see how many `.txt` files there actually are in the directory.
![image](https://user-images.githubusercontent.com/86854157/224893379-657e7dd0-e73d-43fa-9a9f-03c891bd8c77.png)

Then, to make this process easier to complete, we can put this information into a script. A [script](https://ryanstutorials.net/bash-scripting-tutorial/bash-script.php) is a list of commands in a `.sh` file that will be executed one after the other. Here's my example:
![image](https://user-images.githubusercontent.com/86854157/224894573-93cdee73-487e-4d8e-bb0f-078ea0aac659.png)
