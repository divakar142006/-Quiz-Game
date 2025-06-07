# 🧠 Quiz Game

A simple interactive command-line **Quiz Game** built with Python. It presents users with multiple-choice questions to test their knowledge on various topics, keeps track of scores, and provides feedback at the end.

---

## 📋 Features

- Multiple-choice questions
- Instant feedback on answers
- Score tracking
- Percentage score at the end
- Modular code structure

---

## 📁 Project Structure
quiz_game/
├── questions.py # Contains the quiz questions
├── quiz.py # Contains game logic
└── run_quiz.py # Main file to run the game
## 🚀 How to Run

1. **Clone the repository** or download the project folder.

2. **Navigate** to the project directory:
   ```bash
   cd quiz_game
   python run_quiz.py
Question 1: What is the capital of France?
A. Berlin
B. London
C. Paris
D. Rome
Your answer (A/B/C/D): C
✅ Correct!

---

Let me know if you'd like the actual project zipped up or if you want me to generate the GUI or JSON-based version!
PROGRAM
from questions import questions_data

class QuizGame:
    def __init__(self):
        self.score = 0
        self.total_questions = len(questions_data)

    def start(self):
        print("🧠 Welcome to the Quiz Game!")
        print("-----------------------------")
        for idx, q in enumerate(questions_data, start=1):
            print(f"\nQuestion {idx}: {q['question']}")
            for option in q['options']:
                print(option)
            answer = input("Your answer (A/B/C/D): ").strip().upper()

            if answer == q['answer']:
                print("✅ Correct!")
                self.score += 1
            else:
                print(f"❌ Wrong! The correct answer was {q['answer']}.")

        self.show_results()

    def show_results(self):
        print("\n🎉 Quiz Completed!")
        print(f"Your Score: {self.score}/{self.total_questions}")
        percentage = (self.score / self.total_questions) * 100
        print(f"Percentage: {percentage:.2f}%")
        if percentage == 100:
            print("🌟 Excellent!")
        elif percentage >= 60:
            print("👍 Good job!")
        else:
            print("📘 Better luck next time.")



