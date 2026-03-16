# 💭 Reflection: Game Glitch Investigator

## 1. What was broken when you started?
BUG 1:
Expected: The "Attempts" counter starts off at 0 before the user inputs any guesses and is incremented with each guess until the number of attempts is equal to the number of attempts associated with the difficulty.
Actual: The "Attempts" counter starts off at 1 and increases with each guess EXCEPT the first and second-to-last, stopping on the correct value (based on difficulty)

BUG2:
Expected: "Make a guess" instructions display a range of numbers for the user to guess from that aligns with the current difficulty level.
Actual: "Make a guess" instructions display "Guess a number between 1 and 100" regardless of the difficulty level.

---

## 2. How did you use AI as a teammate?
AI TOOL:
Claude

CORRECT AI SUGGESTION:
Since the update_score function was so confused, I was having a hard time understanding what the original scoring system was supposed to be. I asked the AI to explain the original direction of the function and, after reading the description, I decided to ask the AI to suggest an entirely new scoring system, and it correctly suggested a simplified scoring system. To verify it, I ensured that the system removed the possibility of negative scores and provided code that was functional through testing.

INCORRECT/MISLEADING AI SUGGESTION:
I decided that I wanted the "Developer Debug Info" section to display the score that the player WOULD receive if they won the game on that turn.
I asked the AI to help with this and it gaslit me and tried for a good few minutes to reassure me that the code did, in fact, accurately track the score and provided multiple "fixed" versions of the code that did not actually fix the code when I ran the game to verify.
It was not until I experiemented further with the game that I realized that the score DID update, but only if you added an extra submission after the game was complete.
From there, I was able to provide that information to the AI and it only took a couple more prompts to get the Score working.

---

## 3. Debugging and testing your fixes
To decide whether a bug was really fixed, I compared my experience running the game to what I expected from the game. I ran into an issue with the balloons not being displayed upon wins, and it ended up coming down to an issue with then I was rerunning. 
This helped me connect the dots with where some of my other errors were coming from later on as well as informed what tests I did (focusing on bugs in the program that might be caused by incorrect rerunning). 
AI helped me design and understand my tests by acting as a teacher and explaining what the issue was with rerunning to begin with.

---

## 4. What did you learn about Streamlit and state?
I think that a reason for the changing secret number in the original app probably had something to do with the session state being cleared by the reruns.
Streamlit "reruns" are (like the name suggests) literally rerunning the entire script to keep the interface updated. They happen automatically with user interactions or you can call them manually with streamlit.rerun() or st.rerun() if you imported streamlit as st.
To finally get a stable secret number, AI ended up suggesting that I consolidate all of the billions of lines checking if different values were already in the state into one init function so that im not constantly debugging one part of my code and then realizing that I just created more bugs by resetting something else I had already debugged.

---

## 5. Looking ahead: your developer habits
One strategy I want to reuse in future projects is providing the AI with as much information as possible. Honestly, I used to take for granted how much AI was able to correctly assume. However, upon suffering through the torture of having the left half of my screen red with errors and the right half actively trying to gaslight me to my face by insisting that the AI generated code works, I am likely to be less trusting of AI responses and more likely to provide AI with additional information to increase the accuracy of the generated code.