# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

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
When I asked the AI which lines I need to modify to fix all issues with bounds and attempts (not being aligned with the difficulty), it left out a few lines in its recommendations. To verify, I read experiemented with the program myself and noticed areas where the bounds may be an issue. I then read over those sections of code and was able to catch that the AI had skipped some lines and ask about those issues specifically.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
