---
toc: True
comments: True
layout: post
title: Trimester 2 Induvidual Review
description: None
type: tangibles
courses: {'compsci': {'week': 24}}
---

[<h2>Trimester 2 Induvidual Review Blog</h2>

<h3>Project Overview: Game Console</h3>

**Team: Cayden, Saaras, Eric, Austin**


Our CPT project was focused on creating a user friendly game dashboard populated with as many games as possible for the user to sign in and play at their lesiure. Inital planning inclded that of a facial recognizition software through which the user signs in and enters their induvidual game dashboard wherein they can play a multitute of games as per their liking.
<br>
Throughout the journey of this project we faced quite a few errors and bugs which we managed to fix by Night at the Musuem. Our games plethera of games include those such as, tic tak toe, mathnopoly, crossword, bakkarat, spin the wheel and many more.


<h3>My Feature: Tic Tac Toe & Crosswords</h3>

**Crosswords**

For the game dashboard i worked on two games, tic tac toe and crosswords. They two games are known many many and work in a simple way. The tic tac toe game uses user input by assigning X or O to the user and then using a pre defined set of mapping it checks for the 3 down or acorss or diagonnal pattern for the win. A harder version calcualtes the player's move and according plays the ai to make sure the player does not win. A sort of check function which as the name suggests checks if the user is close to winning and plays accrodingly.

**Tic Tac Toe**

For the crosswords, it was not the exact gameplay of regular crossword but rather a rip off. The user is prompted with hints for the word and it given a timer to figure out the word. Alltough a bit buggy the corssword game aims to check for hte user's skill in identifying the words rather than being dependent on the board itslef. Overall with the hint the user must guess a certain amount of words in a specific amount of time.

<h3>Crosswords</h3>

**Component A: Program Code**


```python
<html>
    <body>
        <table>
            <thead>
            <tr>
                <th>Requirments</th>
                <th>Completed</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>Instructions for input from the user (including user actions that trigger events)</td>
                    <td>
                        "The check answer function takes the answer inputted into the user box and compares it with the mapping that exist in the code above. I fhte answer is correct the user is allowed to move on to the next hint and the correct word in displayed on the crossword box and if the suer in incorrect then the screen prompts them to recheck their answer or they are allowed to give up using the give up button which links to another function that links the correct word to an alert and the corssword box. THe check fucniton is as below."
                        <img src="https://github.com/srivaidyas/student2.0/blob/main/images/Screenshot%202024-02-25%20at%207.50.53%E2%80%AFPM.png">
                        "Focusing on the two main aspects of this code that really take into consideration the user input"
                        <img>
                        <img>
                        1. The checkAnswer() function retrieves the value entered by the user in the input box using document.querySelector('.input-box').value.trim().toUpperCase(). 
                        2. An event listener is set up to listen for keyup events in the input box. When the user presses the Enter key, the checkAnswer() function is called to check the user's answer.
                        3. THe answer is cross referenced along iwht the provided mappings for the correct answer
                        4. Subsequent actions are triggered
                    </td>
                </tr>
            </tbody>
        </table>
    </body>
```
](2024-2-25-Tri2_Induvidual_Review_IPYNB_2_.md)