# <p align="center">The Creation of Smite Build Maker and the Smite API Application</p>

<p align="center"><strong>January 26th, 2023</strong></p>

###### <p align="center">© Michael Warmbier</p><br><br>


&emsp;&emsp;In mid-2021, a colleague of mine had suggested creating a tool that would be able to perform calculations of various characters in a video game called _Smite_. Smite is a game designed around the MOBA genre, where you pick characters based on Gods and deities from various pantheons and then battle in a strategy arena. Its design relies on player choice dictating what items to buy throughout the course of various matches, which apply statistical changes that allow the player to earn an edge in gameplay.

Originally, this project was conceived through _Google Sheets_. A tool was created to see the various base statistics that each character would gain depending on their level within the game. This proof of concept was later extended into an idea called _SmiteStats_. SmiteStats, the precursor name to SmiteBuildMaker, was going to be a website that allowed users to calculate the results of various item configurations, _builds_, without having to open the notoriously slow game themselves in order to use the built-in builder provided. 

<p align="center"><img src="https://github.com/MichaelWarmbier/michaelwarmbier.github.io/blob/master/Assets/Previews/api_app.gif?raw=true"></p>

###### <p align="center">The original appearance of the Smite API APP </p>

In order to create a website, I requested permission to access Smite's official API and receive developer credentials. Unfamiliar with using API, I did research and eventually found various then-outdated repositories of wrapped methods and similar tools. The decision was eventually made to take the initiative and create what was then my first original solo project, the _Smite API App_. Originally it was a series of wrappers that progressed into a C-like asynchronous structure despite its design being in _Node.js_. Through use of custom methods, I was able to access the API using nothing but a basic command-line interface. Later on, these methods were improved and combined into one large algorithm that relied on the user input from the CLI to complete its task. In order for this to be possible, several subroutines were created to handle the various information requests the API had. Eventually, everything was restructured and underwent a relatively lengthy documentation period that resulted in the published product being marketed as a developer tool for those who just needed raw `.json` and `.xml` formatted data.

<p align="center"><img src="https://github.com/MichaelWarmbier/michaelwarmbier.github.io/blob/master/Assets/Previews/smiteapi.gif?raw=true"></p>

###### <p align="center">The Smite API App as it looks today</p>


The documentation of the Smite API App was an incredible learning experience about the values of documentation and how it can impact the development process of a project. It's still regarded as one of my favorite projects ever and my first software project in general, even if it lacks a lot of potential additions in that regard.

<p align="center"><img src="https://media.discordapp.net/attachments/239457759836372996/859520411293450240/unknown.png?width=1057&height=481"></p>

###### <p align="center"> An example of a proposition created by a peer at the time </p>

Being unfamiliar with back-end web development and primarily focused on front-end and programming, the API hurdle was a tough one to overcome. Eventually, the project was moved over to _Repl.it_, which is where it still resides and is hosted from. This allowed for a much faster development process, as well as server space to store the `.json` data. Slowly I began creating a website that could read Gods and items from this data and use the information to change elements on the screen.

<p align="center"><img src="https://cdn.discordapp.com/attachments/1065328426032058470/1068187161263869982/unknown-9.png"></p>

###### <p align="center">The original SmiteStats</p>

At this point the site was undergoing multiple redesigns as my skills with CSS, HTML and JavaScript improved. Feedback was received from peers that was translated into changes still present to this day. A secondary program was made, named the Smite Data Formatter, specifically made to automate the translation of all necessary `.json` files into a single collection of data that relied on a reference of information that was excluded from that data to be created. This also underwent several changes for the sake of effectiveness, but the original code went unchanged.

<p align="center"><img src="https://github.com/MichaelWarmbier/michaelwarmbier.github.io/blob/master/Assets/Previews/smitebuildmaker.gif?raw=true"></p>

###### <p align="center"> Smite Build Maker as it looks today </p>

Utilizing these three applications in conjunction, a prototype website was created lacking most of the features available today. This was released on March 25th, 2022 and has since been expanded upon, added various features present in the game and fixing bugs in order to make the results as accurate and customizable as possible. The choice to use `.json` to store most of the server-side information on Repl.it was also made.

Smite Build Maker was without a doubt my largest idea and project at the time. Its conception was a valuable learning experience with an impact that is reflected in all of my projects since. Initial release as well as future updates received outstandingly positive attention from the few voices that were willing to share. While it is not currently my most popular project, being behind both the Smite API App and my _Chance For Rain_ website, it is without a doubt one of the most useful and one of the most evolved.