# SuperStarTrek - Perl port
This is a "faithful" port to Perl of the 1978 BASIC code of Super Star Trek by Bob Leedom. It is based on the code published in BASIC COMPUTER GAMES - Microcomputer Edition, edited by David H. Ahl.

## What is Super Star Trek
Super Star Trek is an old text-only game, an early example of a turn-based space strategy sim, written in BASIC.
In this game, you are the captain of the starship Enterprise, and your mission is to scout the federation space and eliminate all the invading Klingon ships.
You will have to manage the ship energy carefully, use phasers and torpedoes to destroy the Klingons, and find starbases to repair damages and replenish your energy.

## The story of the game
The first Star Trek game was written by Mike Mayfield in 1971 for the Sigma 7 mainframe. In 1974 Bob Leedom improved the code; he added some new features and called it Super Star Trek.
The program listing appeared in the famous 1978 book BASIC COMPUTER GAMES - Microcomputer Edition, edited by David Ahl.
The book's success and the birth of the home computers in 1977 made Super Star Trek one of the most popular games written in BASIC ever created.

For more info about the game, its story, and how to play it, have a look at this article I wrote: [Rediscovering the 1978 Super Star Trek game](https://gamesnostalgia.com/story/182/rediscovering-the-1978-text-only-super-star-trek-game)

For the ones that are interested in the original code, I added it in the folder "original-version". I downloaded it from [Vintage Basic](http://vintage-basic.net/games.html)


## About the port
There are literally thousands of different versions of Super Star Trek. During the years, it has been rewritten, ported, and improved many times.
But I could not find a version that was a faithful conversion of the 1978 code that appeared in the book, so I decided to write it.
My first attempt was mostly a 1-to-1 conversion, but I continued working on it. In the last version, all "goto"s have disappeared, they became if-then-else blocks, loops, and functions. Once I got familiar with the code, I gave meaningful names to most of the variables. I also added a lot of comments.
Additionally, in the BASIC code, all variables are global, and subroutines (GOSUB) were reading parameters as global var. When appropriate, I transformed these global variables into proper function parameters.
The code now is very different, but I paid attention to not change the mechanics or the math behind the game algorithm. The game should play exactly like the BASIC version.

Finally, the code is in Perl, but it's very generic. You should be able to convert it into any other language.

There are two versions:
- superstartrek-plain.pl : plain conversion from BASIC to Perl, runs at "full speed", so text is scrolling very fast. If you want to play it, you should NOT use this version, better to play the other version
- superstartrek.pl : the default version doesn't really offer you a faithful experience. When I tried the Commodore 64 version, I noticed that the text was scrolling much slower, and there is also a small delay before the quadrant screen is rendered. I tried to recreate this experience using a `smallDelay()` function and replacing most of the `print` with a `telePrint()` function (telePrint prints the line and then wait a bit). If you want to play it, use this!


## What's next
I'm not planning to add more features. There are already plenty of enhanced/improved versions of Super Star Trek on the Internet, with all sort of additions, including Romulan ships, clocking devices, supernovae, death rays and more. Probably I'd like to improve the experience, not sure how. For sure I'd like to see Bones talking. Dr McCoy is the only one that never speaks.
I'd like also to lean a new language porting the game, maybe LUA is a good choice. Let's see.



Happy startrekking!


