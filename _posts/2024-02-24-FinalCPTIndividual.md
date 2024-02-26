---
toc: False
comments: True
layout: post
title: Individual Final CPT 
description: CSP Tri 2 Final 
courses: { compsci: {week: 24} }
type: tangibles
---

# Project Overview: 
## ByteJam: Cayden, Saaras, Eric, Sri, Austin 

Our CPT project was focused on creating a user friendly game dashboard populated with as many games as possible for the user to sign in and play at their lesiure. Inital planning inclded that of a facial recognizition software through which the user signs in and enters their induvidual game dashboard wherein they can play a multitute of games as per their liking.

Throughout the journey of this project we faced quite a few errors and bugs which we managed to fix by Night at the Musuem. Our games plethera of games include those such as, tic tak toe, mathnopoly, crossword, bakkarat, spin the wheel and many more.

## My Feature: 

**Crosswords**

For the game dashboard i worked on two games, tic tac toe and crosswords. They two games are known many many and work in a simple way. The tic tac toe game uses user input by assigning X or O to the user and then using a pre defined set of mapping it checks for the 3 down or acorss or diagonnal pattern for the win. A harder version calcualtes the player's move and according plays the ai to make sure the player does not win. A sort of check function which as the name suggests checks if the user is close to winning and plays accrodingly.

**Tic Tac Toe**

For the crosswords, it was not the exact gameplay of regular crossword but rather a rip off. The user is prompted with hints for the word and it given a timer to figure out the word. Alltough a bit buggy the corssword game aims to check for hte user's skill in identifying the words rather than being dependent on the board itslef. Overall with the hint the user must guess a certain amount of words in a specific amount of time.

[Collegeboard Requirements](https://apcentral.collegeboard.org/media/pdf/ap-csp-student-task-directions.pdf)

## Component A (Crosswords): Program Code 

| Requirements | Completed | 
| --------------- | -----------------| 
| Instructions for input from the user (including user actions that trigger events) |"The check answer function takes the answer inputted into the user box and compares it with the mapping that exist in the code above. I fhte answer is correct the user is allowed to move on to the next hint and the correct word in displayed on the crossword box and if the suer in incorrect then the screen prompts them to recheck their answer or they are allowed to give up using the give up button which links to another function that links the correct word to an alert and the corssword box. THe check fucniton is as below."<br>![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%207.50.53%E2%80%AFPM.png) ---------------- ![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%207.51.18%E2%80%AFPM.png)-----![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%207.51.40%E2%80%AFPM.png)-----![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%207.51.56%E2%80%AFPM.png) 1. The checkAnswer() function retrieves the value entered by the user in the input box using document.querySelector('.input-box').value.trim().toUpperCase(). <br> 2. An event listener is set up to listen for keyup events in the input box. When the user presses the Enter key, the checkAnswer() function is called to check the user's answer. <br>3. THe answer is cross referenced along iwht the provided mappings for the correct answer <br>4. Subsequent actions are triggered|



| Use of at least one list (or other collection type) to represent a collection of data that is stored and used to manage program complexity and help fulfill the program’s purpose | This code uses a variety of mapping to function. First and foremost it assigns values to the boxes themsleves, eahc value is defined by thte box number and the letter to which it corresponds to ![CodePic](https://media.discordapp.net/attachments/974516458300256316/1211222387861758002/list.png?ex=65ed69c0&is=65daf4c0&hm=eb9299bdf9bc6a28ebce7d5b0fe0091944633dabaff0ba6488ff250021b8f494&=&format=webp&quality=lossless&width=872&height=1306) Then next mapping deals with the cliues themsleves, each clue is given a number acorrding to the possible of the word in teh corssword box, the clue is then typed accordingly.![CodePic](https://media.discordapp.net/attachments/974516458300256316/1211222387861758002/list.png?ex=65ed69c0&is=65daf4c0&hm=eb9299bdf9bc6a28ebce7d5b0fe0091944633dabaff0ba6488ff250021b8f494&=&format=webp&quality=lossless&width=872&height=1306) Last but not the least the two mappings defined above are then taken into consideration when making the most imporatant mapping of them all, the words with their correspoding clues. IN this mappings, the numbers of the hints defined in the mapping above and the boxes with their letters also defined above are uses to construct the word itslef, the hint along iwth the box numbers where the word resides in. ![CodePic](https://media.discordapp.net/attachments/974516458300256316/1211222387861758002/list.png?ex=65ed69c0&is=65daf4c0&hm=eb9299bdf9bc6a28ebce7d5b0fe0091944633dabaff0ba6488ff250021b8f494&=&format=webp&quality=lossless&width=872&height=1306) OVerall these mapping provided fro the easy answer checking by the program and can be verfified for accuracy in the console with a simple console message. ![CodePic](https://media.discordapp.net/attachments/974516458300256316/1211222387861758002/list.png?ex=65ed69c0&is=65daf4c0&hm=eb9299bdf9bc6a28ebce7d5b0fe0091944633dabaff0ba6488ff250021b8f494&=&format=webp&quality=lossless&width=872&height=1306)  | 




| One procedure that contributes to the program’s intended purpose, where you have defined: the procedure’s name, the return type (if necessary), one or more parameters | This code takes the parameters: Token, Steps in order to update player/ai position and total money. If the token is the player, then the steps given will update the playerposition, vice versa. It will also update and display the total amount of money the player/AI has. It also handles winning and losing. When playermoney/aimoney reaches 500, a notification will appear with either You win or You lose, and reset the game after. The submitanswer function mentioned above calls this procedure.  ![CodePic](https://media.discordapp.net/attachments/974516458300256316/1211222388184973342/procedure.png?ex=65ed69c0&is=65daf4c0&hm=0a40071a28e12eae8483c4ddd97e80f6c8913b835752ff2f0427894085ddcb49&=&format=webp&quality=lossless&width=1664&height=1306) |
| An algorithm that includes sequencing, selection, and iteration that is in the body of the selected procedure | Selection: If/Else Statements, since the code is choosing to either move player and ai if the player answered correctly, or just move the ai if the player did not answer correctly. Iteration: SetTimeout Function, since it allows the program to repeat by moving the ai, and changing the displayed question while updating the display of who's turn it is after a delay. ![CodePic](https://media.discordapp.net/attachments/974516458300256316/1211222388474122350/calls.png?ex=65ed69c0&is=65daf4c0&hm=3f8dc064b318d2781ef69b730d51472ea75cb02080bb33863a898d5fecd0feaa&=&format=webp&quality=lossless&width=1916&height=1306) |
| Calls to your student-developed procedure | Calling move function. ![CodePic](https://media.discordapp.net/attachments/974516458300256316/1211222388474122350/calls.png?ex=65ed69c0&is=65daf4c0&hm=3f8dc064b318d2781ef69b730d51472ea75cb02080bb33863a898d5fecd0feaa&=&format=webp&quality=lossless&width=1916&height=1306) |
| Instructions for textual output based on input and program functionality | Textually inform user if they won/lost. ![CodePic](https://media.discordapp.net/attachments/974516458300256316/1211222388763791390/textual_output.png?ex=65ed69c0&is=65daf4c0&hm=82237624f81da02eae42c929bbbc16bad1849b7760d02e06fe660726fafac354&=&format=webp&quality=lossless&width=1544&height=752) |
| Instructions for visual output based on input and program functionality | Update position of player/ai on visual board. ![CodePic](https://media.discordapp.net/attachments/974516458300256316/1211222389082423356/visual_output.png?ex=65ed69c0&is=65daf4c0&hm=f5af7a71f35a1a1effcdf78d02d0edb4c31e0d0809a01170d19299f6ddaf7a57&=&format=webp&quality=lossless&width=2392&height=1306) |

## Component B: Video 

[Video Link](https://drive.google.com/file/d/1ABuaUy8QQnu4C5bEtYBdWsV4WsEGpEy8/view?usp=sharing)

| Requirements | Completed | 
| --------------- | -----------------| 
| Input to your program | Y - Show Submit Answer into Answer Box |
| At least one aspect of the functionality of your program | Y - Show that Game Functions as Expected W/O Bugs |
| Output produced by your program | Y - Show Visual Movement, Display Steps Moved, Money Gained, Show Victory/Loss Notification |
| Your video may NOT contain: Any distinguishing information about yourself, Voice narration (though text captions are encouraged) | Y |
| Your video must be: Either .webm, .mp4, .wmv, .avi, or .mov format | Y - .mp4 File |
| No more than 1 minute in length | Y - 1 Minute Long |
| No more than 30MB in file size | Y - 28 MB|


