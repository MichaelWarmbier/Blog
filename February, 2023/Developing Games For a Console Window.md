# <p align="center">Developing Games For a Console Window</p>

<p align="center"><strong>February 7th, 2023</strong></p>

###### <p align="center">© Michael Warmbier</p><br><br>

&emsp;&emsp;After I had just finished my introductory course for my major, _Introduction to Computer Science_, I of course learned how to create programs that ran in the Windows _Command Prompt_ application by default. At the time, I wasn't very familiar with libraries and how they could be utilized to create different program windows, graphical user interfaces and speed along the process of making these applications. I did, however, know how to output text using `cout`.

Out of genuine interest for the subject I eventually stumbled upon one of the many videos that went over how to make _Pong_ in C++, through the console. Admittedly what allowed this guide to stand out from the rest, in retrospect, was how it didn't rely on high-level concepts to teach a relatively low-level project. No classes, no enumerators; these were things I had to implement myself after learning about their using and noticing how it could apply. What I did learn about, however, was the concept of a game loop. Specifically, I learned about how you could break portions of the code into individual scripts or functions that ran within a constant loop.

```cpp
bool GAMEOVER = false;
int main() {
    do {
        draw();     // Draw screen
        input();    // Input handle
        logic();    // Apply logic
    } while (GAMEOVER);
}
```

This was a relatively simple structure that would be the basis for my next four projects; projects that I now dub the "Console Game Library" or similar. In short, these were four games I recreating utilizing the techniques I learned from this point onward that relied on no libraries save for `<Windows.h>`, for `draw()` and the standard libraries. The only exception to this rule was `<chrono.h>`, which I used to control the **f**rames **p**er **s**econd of the programs I made with delta time.

<hr>

### <p align="center">Pong</p>
<br>

&emsp;&emsp;Of course, the first project I worked on was _Pong_. It wasn't anything special, just a two-dimensional array of values output to the screen using conditional logic based on the **i** and **j** values of their elements. I created walls, a ball and paddles and drew them to the screen one every available frame. There was no frame limiting, and the only improvement I made to the code it was inspired from was the use of a function to remove the output carot from the display and a `<Windows.h>` method to move the cursor faster. I also implemented the most basic AI I've ever created: a paddle who had a chance to move in the direction opposite of its target, the ball.

<p align="center"><img src="https://camo.githubusercontent.com/a837346fc5b8920a6bf6c7270b0775527b0d239c89faed7d503f1b3befb431d8/68747470733a2f2f692e6779617a6f2e636f6d2f35623537343461616132393661653538363966323831623734313461643461382e676966"></p>

##### <p align="center">A recently designed game of pong I made in about ten minutes.</p>
<br>

<hr>

### <p align="center">Tetris</p>
<br>

&emsp;&emsp;After messing with some options for awhile I had the idea of recreating more complex games. With _Tetris_, it was really a matter of learning the unique characteristics of a game with more features within it. I had to understand collision, specifically projecting collision a frame ahead and then determining the resulting logic, proper **r**andom **n**umber **g**eneration (which, unlike with JavaScript or Python, was a lot less random when performed quickly due to its reliance on `<ctime>`) and most importantly: `draw()` improvements.

<p align="center"><img src="https://camo.githubusercontent.com/d3dc1f76f02c98dfb00a8810f06892832868f76a67638d1718c473b1b15e9f4c/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f3439333836363835353336333131373035372f3534393036323730303531373239343130372f47616d65706c61792d312e676966"></p>

##### <p align="center">_Tetris_ displayed using ASCII; along with the carot before its removal.</p>

<br>
Initially I used more ASCII, although I started to incorporate the extended ASCII chart. I learned by asking questions in search engines such as, "can you change the color of ASCII output?". Turns out, you can do this and much more. This was also the project wherein I finally utilized the aforementioned `<chrono.h>`. 

<p align="center"><img src="https://user-images.githubusercontent.com/44079959/59775479-4ce3a500-927f-11e9-8871-479e8500e695.png"></p>

##### <p align="center">A later version mostly utilizing square-shaped pixel projections.</p>
<br>

More importantly than all that, however, were the imrpovements I made to the output. Instead of relying on ASCII, I started using pixel projections, mostly lines and squares, to make actual sprites. Though this quickly had to be improved, since the responsible methods had tons of overhead and were very slow when creating more complex images. The answer: bitmaps. By using bitmap sprite sheets, I was essentially creating games with a very novel approach. I created evenly-sized sprites on a sheet, indexed them as constant data and relied on them for the output of the game. After a few design changes, the _Tetris_ that stands today was created.

<p align="center"><img src="https://camo.githubusercontent.com/45dd0977870a249a4fbb1b4f8f56c14a088d8118f7ea95a62651399c0bd9d336/68747470733a2f2f692e6779617a6f2e636f6d2f37386537643164393331326661313037396635383265623861626335663332362e676966"></p>


##### <p align="center">A fun, animated menu screen.</p>
<br>

It must not be understated how useful this project was to me as a student. Not only did it teach me more than anything thus far, but it was one of the most exciting and fulfilling projects I've ever made. Being able to turn my ideas into reality, even to a small degree, was exciting and part of the reaosn why I still program to this day.

<hr>

### <p align="center">Pacman</p>
<br>

&emsp;&emsp;Admittedly this project went incomplete, for one very important reason: the work that was never completed was tedious. As disappointing as it sounds, I, as a student with barely any time to myself, did not feel interesting in programmaging, from scratch, lengthy and complex cutscenes. Despite this, a lot of features that went above and beyond the core concept of the game were made. Proper level counters, mimicked bugs present in the original arcade version of _Pacman_, pixel-perfect collision considerations, etcetera. This project includes the most complex sprite sheet of all four games, and took a lot of research into rules and design of the game. Not having any useful tools or access to the code directly at the time, this information was compiled using cross-reference research. 

<p align="center"><img src="https://user-images.githubusercontent.com/44079959/59776935-aa78f100-9281-11e9-9c64-e8aadf9b4e88.png"></p>

##### <p align="center">The original build of _Console Pacman_.</p>

<br>

Unlike the previous games on this list, I tried to make this as _visual accurate_ to its original as possible. Because both this version and the original relied on 24bit sprites, it wasn't very hard once I figured out how it all worked. The hardest challenge overall was recreating the complex targeting AI that the _ghosts_ within the games rely on, something I hope to go more in-depth on in the future.

<p align="center"><img src="https://camo.githubusercontent.com/588cc76b64041772bebb8665cd0aac3834f0c937162bc80bba1ad66a65ddec76/68747470733a2f2f63646e2e646973636f72646170702e636f6d2f6174746163686d656e74732f3533313631393332383736303631303832362f3633343431303530323836343234303634302f756e6b6e6f776e2e706e67"></p>

##### <p align="center">The final build.</p>

<br>

<hr>

### <p align="center">MineSweeper</p>
<br>

&emsp;&emsp;This project, unlike the rest which took considerable time, took me two days to develop. I applied everything I learned previously, with the only unique concept applied being recursion. Though, I took a lot of liberty with the sprite creation; having created entirely original sprites with no direct inspiration, save for the smiley face that is a staple to the original _MineSweeper_.

<p align="center"><img src="https://user-images.githubusercontent.com/44079959/64381362-05102680-d001-11e9-8e60-8b7c178b8daf.png"></p>

##### <p align="center">_Console MineSweeper_ mid gameplay.</p>
<br>

Overall this project turned out nicely, though not without its flaws. Its compact and simple, and still fun to play. I genuinely recommend it as an interesting project for new programmers that connects a ton of concepts, like RNG and recursion, without introducing more complex ones.

<hr>

### <p align="center">Five Nights at Freddy's</p>
<br>

&emsp;&emsp;Based on the cult-classic of 2014; instead of being a direct recreation of another game in the C++ language, this was a re-imagining of the mechanics present in the original. Stripping the atmospheric horror and limiting the game to its core logical mechanics, _Console Five Nights at Freddy's_ was an interesting way of applying randomized artificial intelligence. Nothing was too complex, though still had to be researched similarly to _Console Pacman_'s development. Some liberties had to be taken as a result of the perspective switch, but overall the gameplay feels the same. Most interestingly, this actually a user to run a simulation, of sorts, of the original. This type of "recreation for the sake of teaching" use case is something I explored in later projects, such as _Pacman in Game Maker_.

<p align="center"><img src="https://camo.githubusercontent.com/e36bf535e69ecb4b6fbbfa65ba2c002d884562edae421d6bac608c81ea32ea9b/68747470733a2f2f6779617a6f2e636f6d2f31336432323163396636383133376661383335313564353237316134303864372e676966"></p>

##### <p align="center">An example of the camera switching mechanic in the game.</p>
<br>

### <p align="center">Final Thoughts</p>
<br>

&emsp;&emsp;The idea of making a pgame in the Windows console is not new, its not unique and its not necessarily complex. However, I truly value this experience as it introduced me not only to new and interesting concepts that I had yet to learn, but the amount of work someone can complete when inspired and excited to do so. There are many project ideas I have not completed or have never begun, and who knows if I'll ever finish them. But I do know that the ones I put the most love into and commit as much as possible,  are the ones that allow me to express my interests in fun, useful and interesting ways.