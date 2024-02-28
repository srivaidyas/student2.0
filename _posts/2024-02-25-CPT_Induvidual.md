---
toc: False
comments: true
layout: post
title: Final CPT Review Blog
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
| Instructions for input from the user (including user actions that trigger events) |This JavaScript code defines a function checkAnswer() for validating user input in a crossword puzzle game. It retrieves the user's input and compares it to the correct answer, updating the puzzle accordingly. The function handles moving to the next hint or word, marking completed words, and ending the game when all answers are correct or after 11 questions. It also sets up an event listener for user input, triggering the answer check when the user hits Enter. Overall, the code manages user interaction in a crossword puzzle game, ensuring progression and feedback based on the correct of answers. ![codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-27%20at%2011.32.11%E2%80%AFAM.png)|



| Use of at least one list (or other collection type) to represent a collection of data that is stored and used to manage program complexity and help fulfill the program’s purpose | This JavaScript code defines collections of data using objects and lists to manage a crossword puzzle game. It utilizes a dictionary-like object boxLetterMapping to ma p box IDs to corresponding letters in the puzzle. Additionally, it also uses the nested objects wordHints to store hints categorized by direction (Across or Down). The hintBoxMapping object also uses the numerical keys to represent hint numbers, mapping them to the respective boxes in the puzzle. These collections effectively organize puzzle data, making the easy retrieval and manipulation within the game logic. Overall, the code demonstrates easy and organized use of collections to handle complex puzzle structures and hints, which mkes for the fucntinality of the game more effeint and better. ![Codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%208.07.52%E2%80%AFPM.png) | 




| One procedure that contributes to the program’s intended purpose, where you have defined: the procedure’s name, the return type (if necessary), one or more parameters | The checkAnswer() function acts as the main mechanism for validating user input against the correct word that is part with with the displayed hint. Through careful comparison, it evaluates whether the user's guess matches the expected solution and triggers appropriate actions accordingly. This function not only ensures the accuracy of the crossword puzzle but also an immersive gaming experience by dynamically updating the grid in response to user interactions. - Basically it llike updates teh crossword with the new words after it is responded correctly. --- Its  design facilitates seamless  with other game features, promoting code maintainability. Moreover, by incorporating logic to handle transitions between hints and words, the function contributes to the overall flow and progression of the crossword game, making the game cool to play for the user themselves. ![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%208.20.02%E2%80%AFPM.png) |


| The populateHintBox() function within the codebase exemplifies sequencing, selection, and iteration. It sequentially populates hint boxes based on the current game state and hint index. Selection is evident as it alternates between across and down hints based on the hint index parity. The function iterates through hint indices, ensuring each hint is displayed in sequence. It selects hints dynamically, adapting to the current game state and hint index. Through its systematic approach, the function orchestrates the population of hint boxes, demonstrating effective sequencing, selection, and iteration within the crossword game's logic. ![Codepic]()|



| Calls to your student-developed procedure | Calling to the hint box function ![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%208.20.47%E2%80%AFPM.png) |


| Instructions for textual output based on input and program functionality | These alerts inform the user if they got th eword ocrrect or not ans also if and when they use the give up button time is taken off from them ![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/a9483e1972dcf96449c6713eac1834c2351795ee/images/Screenshot%202024-02-25%20at%208.55.49%E2%80%AFPM.png)  --- ![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/a9483e1972dcf96449c6713eac1834c2351795ee/images/Screenshot%202024-02-25%20at%208.56.25%E2%80%AFPM.png) ---- ![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/a9483e1972dcf96449c6713eac1834c2351795ee/images/Screenshot%202024-02-25%20at%208.57.48%E2%80%AFPM.png) ---- |



| Instructions for visual output based on input and program functionality | Shows a new hint and updates the word on the crossword box after the user gets it right or uses the give up button ![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/ce571ea346ef6ead917ebd74f6e46f0fad6625f8/images/Screenshot%202024-02-25%20at%209.00.14%E2%80%AFPM.png) --- ![123](https://raw.githubusercontent.com/srivaidyas/student2.0/ce571ea346ef6ead917ebd74f6e46f0fad6625f8/images/Screenshot%202024-02-25%20at%208.59.57%E2%80%AFPM.png) |

| Instructions for timeout| REstarts the game ![Codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-26%20at%2012.06.27%E2%80%AFPM.png)|

<br><br>

## Component A (Tic Tac Toe): Program Code 

| Requirements | Completed | 
| --------------- | -----------------| 
| Instructions for input from the user (including user actions that trigger events) | The following code details out the function checks for the user input on the boxes and then also checks for where the user wins or not. The second portion is what is triggered after the user the ai is triggered to play on.<br>![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%209.17.33%E2%80%AFPM.png) ------ ![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%209.19.38%E2%80%AFPM.png)|



| Use of at least one list (or other collection type) to represent a collection of data that is stored and used to manage program complexity and help fulfill the program’s purpose | These lits details out all the possible combination for a win by either the player or the ai all the 3 box combinations ![Codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%209.21.44%E2%80%AFPM.png) | 




| One procedure that contributes to the program’s intended purpose, where you have defined: the procedure’s name, the return type (if necessary), one or more parameters | The code below details out the ai move, wiout the ai move the game would not continue and thus this procedure contributed most to the program's intendfed purpose which keeps the game going on and the user challeged with teh ai moves and thus try their best to win the game. ![Codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%209.24.59%E2%80%AFPM.png) ---- ![Codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%209.25.22%E2%80%AFPM.png) |


| An algorithm that includes sequencing, selection, and iteration that is in the body of the selected procedure | The check win function is the one here that uses the if and ewlse statments. This algorithm involves sequencing (step-by-step execution), selection (conditional checks), and iteration (looping over winning combinations) to determine if a player has won or if the game has ended in a tie. ![Codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%209.31.03%E2%80%AFPM.png) |



| Calls to your student-developed procedure | The boxClickHandler function controls player moves in the Tic Tac Toe game. It starts by gathering information about the clicked box and its position in the grid. After verifying that the box is empty and updating with the player's symbol, it checks for win conditions and ties using checkWin. If neither condition is met, it triggers the AI's move with a delay via makeAIMoveWithDelay. This function serves as a central hub for managing player interactions, game state updates, and AI responses, ensuring a smooth gameplay experience. ![Codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%209.34.21%E2%80%AFPM.png) |


| Instructions for textual output based on input and program functionality | Alerts teh user if they win or teh ai wins, inside the check fucntion ![Codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%209.36.53%E2%80%AFPM.png)|


|Instructions for visual output based on input and program functionality| Allows the the ai dot or the user dot to be place in teh board accroing to where the user clicks and the ai is played ![Codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%209.39.27%E2%80%AFPM.png) ---- ![Codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%209.40.40%E2%80%AFPM.png) ----  ![Codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%209.40.08%E2%80%AFPM.png)|

| Instructions for time out| REstarts the game ![Codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-26%20at%2012.03.59%E2%80%AFPM.png)|

## Component B: Video 

[Video Link](https://www.youtube.com/watch?v=Ue5uVJKyZpk)

| Requirements | Completed | 
| --------------- | -----------------| 
| Input to your program | Yes - Show Submit Answer into Answer Box or click on box |
| At least one aspect of the functionality of your program | Yes - Show that Game Functions as Expected W/O Bugs |
| Output produced by your program | Yes   |
| Your video may NOT contain: Any distinguishing information about yourself, Voice narration (though text captions are encouraged) | Yes |
| Your video must be: Either .webm, .mp4, .wmv, .avi, or .mov format | No - Could'nt figure out a way to intergate subtitile without the use of Youtube |
| No more than 1 minute in length | Yes - 1 Minute Long |
| No more than 30MB in file size | Yes - Youtube|
