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


| Instructions for input from the user (including user actions that trigger events) |This JavaScript code defines a function checkAnswer() for validating user input in a crossword puzzle game. It retrieves the user's input and compares it to the correct answer, updating the puzzle accordingly. The function handles moving to the next hint or word, marking completed words, and ending the game when all answers are correct or after 11 questions. It also sets up an event listener for user input, triggering the answer check when the user hits Enter. Overall, the code manages user interaction in a crossword puzzle game, ensuring proogress and feedback based on the correct of answers. ![codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-27%20at%2011.32.11%E2%80%AFAM.png)|



| Use of at least one list (or other collection type) to represent a collection of data that is stored and used to manage program complexity and help fulfill the program’s purpose | This JavaScript code defines collections of data using objects and lists to manage a crossword puzzle game. It uses the a dictionary-like object boxLetterMapping to ma p box IDs to corresponding letters in the puzzle. Additionally, it also uses the nested objects wordHints to store hints categorized by direction (Across or Down). The hintBoxMapping object also uses the numerical keys to represent hint numbers, mapping them to the respective boxes in the puzzle. These collections effectively organize puzzle data, making the easy retrieval and its use within the game logic. ![Codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%208.07.52%E2%80%AFPM.png) | 




| One procedure that contributes to the program’s intended purpose, where you have defined: the procedure’s name, the return type (if necessary), one or more parameters | The checkAnswer() function acts as the main function for validating user input against the correct word that is part with with the displayed hint. Through  comparison, it evaluates whether the user's guess matches the expected solution and triggers appropriate actions accordingly. This function not only ensures the accuracy of the crossword puzzle but also a a really cool expericence for the user as it dynamically updates the grid in response to user interactions. - Basically it llike updates teh crossword with the new words after it is responded correctly. --- It intergrates with  with other game features, which promote code maintainability and easy to read code. The login which takes care of the trasitions allows for the user to continue playing until they guess al the words they have to guess. ![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-25%20at%208.20.02%E2%80%AFPM.png) |


| An algorithm that includes sequencing, selection, and iteration that is in the body of the selected procedure	| The populateHintBox() function within the codebase exemplifies sequencing, selection, and iteration. It keeps giving hints in the hint boxes based on the current game state and hint index. Selection is evident as it alternates between across and down hints based on the hint index. The function therefore iterates through hint indexes, ensuring each hint is displayed in sequence. And thus through this, the function provides continues hints in the hint boxes with an exmaple of how seqeunceing is used in the code. ![Codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-28%20at%202.40.38%E2%80%AFPM.png)|



| Calls to your student-developed procedure | Calling to the check answer function ![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-28%20at%202.40.38%E2%80%AFPM.png) |


| Instructions for textual output based on input and program functionality | The section of the code primarily responsible for gettingg instructions for textual output based on input and program functionality is within within the checkAnswer() function. Upon calling of this function, this function retrieves the user's input from the input box and the currently displayed hint from the hint box. It proceeds to compare the user's input with the correct solution, determining whether it matches. If the input matches the correct word, the function provides congratulatory messages, indicating the correctness of the answer. In cases where the user's input does not match the solution, the function prompts the userr for retrying the word. Through these steps, the checkAnswer() function does the generation of appropriate instructions, thereby giving user interaction and feedback within the crossword puzzle game's functionality.![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-28%20at%202.47.14%E2%80%AFPM.png)|



| Instructions for visual output based on input and program functionality | Shows a new hint and updates the word on the crossword box after the user gets it right or uses the give up button ![CodePic](https://raw.githubusercontent.com/srivaidyas/student2.0/ce571ea346ef6ead917ebd74f6e46f0fad6625f8/images/Screenshot%202024-02-25%20at%209.00.14%E2%80%AFPM.png) --- ![123](https://raw.githubusercontent.com/srivaidyas/student2.0/ce571ea346ef6ead917ebd74f6e46f0fad6625f8/images/Screenshot%202024-02-25%20at%208.59.57%E2%80%AFPM.png) |

| Instructions for timeout| REstarts the game ![Codepic](https://raw.githubusercontent.com/srivaidyas/student2.0/main/images/Screenshot%202024-02-26%20at%2012.06.27%E2%80%AFPM.png)|

| Note| Many of the college board requirments are satisfied byt he checkanswer() function|

<br><br>

## Component A (Tic Tac Toe): Program Code  
| Requirements | Completed | 
| --------------- | -----------------| 
|  Instructions for input from the user (including user actions that trigger events) | The boxClickHandler(event) function manages user interaction by responding to clicks on the Tic Tac Toe game board. It captures the clicked box element and its position, ensuring it's a valid move before updating the game state. Following the player's move, it checks for win or tie conditions to determine the game's outcome. This function facilitates a seamless gameplay experience by allowing users to interact with the game interface and progress through the match based on their selections. ![CodePic]() | 

| Use of at least one list (or other collection type) to represent a collection of data that is stored and used to manage program complexity and help fulfill the program’s purpose | The cont winngingCombination defines all the possible ways that the use or the AI can win. This is a key mapping because without this mapping the code would not be able to function as would stay at a staelment standstill after all the boxes are coverd with the ai or the user symbols ![CodePic]() | 




| One procedure that contributes to the program’s intended purpose, where you have defined: the procedure’s name, the return type (if necessary), one or more parameters | The main procedure tat contributes to the program's intended purpose in the chekWin function. THis function cross verifies the combination on the baord to the combination of the winning ones as defined by the contant above. This is a jey function as without this, the game would never have an acutally winner and both sides would jsut ocntrinue to play untill the board is just filled with X and O! ![CodePic]()|


| An algorithm that includes sequencing, selection, and iteration that is in the body of the selected procedure |In the makeAIMove() function, the AI follows a step-by-step approach to decide its next move. First, it checks which cells on the game board are empty and available for selection. Then, it evaluates potential moves, considering strategies like blocking the opponent's winning moves or attempting to win itself. Once it has made a decision, it places its symbol in the chosen cell. This sequence of actions ensures the AI's strategic gameplay in Tic Tac Toe. ![CodePic]() |



| Calls to your student-developed procedure | At the end of the code the game's intialization code is called through. This activates all the other function deinfed above. Additioanlly at many parts of the code, the makeAIMovewithDelay function is also being called, this function is a part of the AI movement, and thus encapsulates most of how the AI is supposed to move with an added twist of it move 500 later or 0.5 seconds later ![CodePic]() ![CodePic]() |


| Instructions for textual output based on input and program functionality | Within the checkWin function is the textual output for every desired outcome in the baord, if the plahyer wins the screen alerts the user that they have won and if the programs identifies that the AI has won then it alerts that the AI has won to the user. Additionally it also updates the AI and Player money on the screen for everywin , not really money but rather a poitn system where the player or the ai is granted a point based on when they win.![CodePic]()|


|Instructions for visual output based on input and program functionality| Within the board itslef the displayWinningCombination function is what creates the visually appealing nature of the tic tac toe wherein the user and the ai symbols are clearly displayed for the user to see and play against. With every move by the player this function idefities when the boxes are and the player or the ai wins the winning combination is identified and the player or the ai is alerted ![CodePic]()|

| Instructions for time out and restar to fthe game| After every win the baord is reset with the point system still intact and a new symbol alloted for the AI and the user to play against. ie the assign roles function ![CodePic]()|

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
