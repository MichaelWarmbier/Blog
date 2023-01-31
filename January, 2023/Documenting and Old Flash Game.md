# <p align="center">Documenting an Old Flash Game</p>

<p align="center"><strong>January 31st, 2023</strong></p>

###### <p align="center">© Michael Warmbier</p><br><br>

&emsp;&emsp;Sometime in early January, it was suggested to me that I should try my hand in remaking an old game a colleague of mine was a fan of back when he was younger. That game, _PitSweeper_, was made in _Adobe Flash_ back in 2009. Out of curiosity for how realistic such a task would be in a short time, I found a repository on Github named the [JPEXS Flash Decompiler](https://github.com/jindrapetrik/jpexs-decompiler) by Jindra Petrik. Despite its less-than-modern user interface, it was very helpful for viewing all the assets and scripts associated with the game.

Even with only little knowledge of _ActionScript_, the language which Flash relies on, as well as _Java_, the most well-known syntactically similar language, I was able to discern a lot of the intent from the one Java-centric university class I'd taken. In this class, I'd also learned how to create class diagrams. I started documenting the project as an opportunity to practice, with a fully detailed available collection of scripts present. Later on, this side-project became a fully detailed [document on PitSweeper](https://github.com/MichaelWarmbier/PitSweeper).

<img align="center" src="https://i.gyazo.com/e8ea3a07b01e349156f054a0d17ec618.gif">

I started this process by writing the names of all objects the game relied on, by hand and on paper, then connecting the names exactly how they stated they were; through inheritance within the scripts. Sifting through the classes was a great opportunity to learn about the differences between ActionScript and Java, as well as attributes I had not even heard of before. Following this, I created a class diagram in its entirety and as accurately as possible over the course of a few hours worth of work. 

<img align="center" src="https://cdn.discordapp.com/attachments/1065328426032058470/1070041505735127062/image.png">

While the class diagram was in progress, I also started to begin my work on understanding the structures as they were defined. This included creating charts of all object sets that it would be beneficial to represent in that way, as well as turning those charts into `.csv` data that I could move over to Markdown later. Originally, a lot of the data names were only temporary or guesses, until sifting through the code further revealed their actual use; such as with the `dicetype` and `dicenumber` variables. I initially considered these to be part of the 'miss chance' method that was present. Instead, as it turns out, it was related to the extra damage random damage feature. 

Beyond attributes, determining the objects' passive effects as well as fundamental considerations, such as level randomization and creation, required a lot of code translating. I opted to translate, to the best of my ability and with blatant language differences, ActionScript code into _C++_ code. Along with this, I named related constants and variables after what they appeared to do (as they had defaulted to obfuscated names), while leaving comments and simplifying structures (such as converting iterated `while loops` to `for` loops).

<img align="center" src="https://media.discordapp.net/attachments/1065328426032058470/1070041188851273788/image.png?width=1056&height=676">

The biggest challenge when documenting, although a short process, was writing a _Python_ script that would give me the information I needed from the map data matrices. As they stood, they were just flat, one-dimension arrays of information. I needed to un-flatten them and then print that text. I also used padding to make all the values equal in length, as to make it easier to see what was going on. Lastly, in order to calculate the theoretical total level variations, I created a program that would mimic the bitwise operation done on a constant set of values present in the game's actual code. 

This entire process was lengthy but fulfilling. Genuinely, an exciting opportunity to practice something I unexpectedly enjoyed a lot. It also added a fine document to my collection and became the second document I'd ever written.