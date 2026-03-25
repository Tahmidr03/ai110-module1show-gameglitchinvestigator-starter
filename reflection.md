# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

When I first ran the game, it looked normal visually, but the gameplay felt broken and confusing. The hints did not match the guesses, which made it impossible to trust the feedback. One major bug was that the hints were reversed, so if I guessed higher than the secret number, it would sometimes tell me to go higher instead of lower. Another issue was that the attempts counter started at the wrong number, which made it seem like I was losing attempts without doing anything. I also noticed the score behaved strangely and sometimes increased even when I guessed incorrectly.

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

I used ChatGPT and Copilot as my main AI tools during this project. One correct suggestion was to move the logic functions like `check_guess` and `update_score` into `logic_utils.py`, which made the code cleaner and easier to debug. I verified this by running the game and seeing that the logic worked correctly after separating it from the UI. One misleading suggestion was related to the scoring logic, where the AI suggested a system that sometimes rewarded incorrect guesses. I noticed this was wrong by testing the game manually and seeing the score increase when it should not have, so I fixed it myself.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

I decided a bug was fixed by both manually testing the game and checking if the behavior matched what I expected. For example, I tested guessing a number higher than the secret and confirmed that it correctly told me to go lower. I also ran pytest to verify that the logic functions like `check_guess` returned the correct outcomes for different inputs. One test I ran checked that guessing 60 when the secret is 50 returns "Too High," which confirmed the logic was working. AI helped me by suggesting test cases, but I still had to understand and verify that the tests were actually checking the correct behavior.

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

I learned that Streamlit reruns the entire script every time the user interacts with the app, like clicking a button. This means that variables will reset unless they are stored in `st.session_state`. I would explain it like this: every time you click something, the app restarts from the top, but session state is like memory that keeps important values from being lost. Without using session state, things like the secret number or score would keep resetting and break the game.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

One habit I want to reuse is testing my code frequently after making small changes instead of waiting until the end. Next time, I would be more careful about trusting AI suggestions and double-check the logic immediately instead of assuming it is correct. This project showed me that AI-generated code is not always reliable and can contain subtle bugs. I learned that I need to carefully review and test everything instead of blindly trusting what the AI gives me.
