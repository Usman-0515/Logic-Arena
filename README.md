# Logic-Arena
Console-Based Quiz game (PF Final Project)
# 🎮 LogicArena – Console Quiz Game (C++ Project)

LogicArena is a **console-based quiz game** built entirely in **C++ using only fundamental programming concepts**: arrays, file handling, loops, conditions, and functions.  
Developed as part of the *Programming Fundamentals* course.

---

## ⭐ Features

### 🎯 Quiz System
- 3 Subjects: **Science**, **Computer**, **IQ**
- 3 Difficulty Levels: **Easy**, **Medium**, **Hard**
- Loads **30 questions** per file
- **Randomized** question selection (10 per quiz)
- **10-second timer** on each question
- Automatically handles lowercase / uppercase answers

---

### 🏆 Scoring
- **+2** for correct answers  
- Wrong answer penalty:
  - Easy: −2  
  - Medium: −3  
  - Hard: −5  

#### 🎉 Streak Bonuses
- **3 consecutive correct → +5 points**
- **5 consecutive correct → +15 points**

---

### 🧰 Lifelines (once per quiz)
- **50/50** → removes two incorrect options  
- **Time Extend** → +10 extra seconds  
- **Skip Question**  
- **Swap Question**

---

### 📜 Review Mode
After each quiz, users can review:
- Only the **incorrect questions**
- Their selected answer
- The correct answer

---

### 📊 Leaderboard
- Saves player name and score  
- Automatically updates score if the player replays  
- Displays **Top 5** highest scores  
- Uses file handling (`leaderboard.txt`)

---

### 🧾 Quiz Logs
Every quiz attempt is stored in `quizlogs.txt`, including:
- Player name  
- Subject  
- Difficulty  
- Score  
- Asked question indexes  
- Player answers  
- Correct answers  

---

### 🔐 Admin Mode (Under Development)
- Password protected  
- Will include:
  - Reset leaderboard  
  - View quiz logs  
  - Manage questions  

---

## 📁 Project Structure

LogicArena/
│
├── main.cpp
│
├── leaderboard.txt
├── quizlogs.txt
│
├── science_easy.txt
├── science_medium.txt
├── science_hard.txt
│
├── computer_easy.txt
├── computer_medium.txt
├── computer_hard.txt
│
├── iq_easy.txt
├── iq_medium.txt
└── iq_hard.txt
##Function Structure (main.cpp)
main.cpp
│
├── menu()                      
│   → Displays main menu
│
├── subject()                  
│   → Takes subject input (Science/Computer/IQ)
│
├── difficulty()               
│   → Takes difficulty input (Easy/Medium/Hard)
│
├── loadQuestions()            
│   → Loads 30 questions from the selected file using file handling
│
├── displayQuestion()          
│   → Core quiz engine (timer, lifelines, streaks, answer checking)
│
│   ├── showlifelines()
│   │    → Displays 50/50, Skip, Swap, Time Extend
│   │
│   ├── applyswap()
│   │    → Replaces current question with a new one
│   │
│   └── reviewWrong()
│        → Shows incorrect questions after quiz
│
├── saveScore()                
│   → Saves or updates player scores in leaderboard.txt
│
├── Leaderboard()              
│   → Reads all scores, sorts them, and prints Top 5
│
├── adminmode()                
│   → (Under development) password-locked admin area
│
└── saveQuizLog()              
    → Saves session details (user answers, correct answers, question index)
