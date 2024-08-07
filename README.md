questions = [
    {
        "question": "What is the longest river in the world?",
        "options": ["Nile river", "Amazon river", "Yellow river", "Niger river"],
        "answer": "A"
    },
    {
        "question": "What is the largest planet in our solar system?",
        "options": ["A. Earth", "B. Jupiter", "C. Mars", "D. Venus"],
        "answer": "B"
    },
    {
        "question": "What is the capital of Portugal?",
        "options": ["New Delhi", "Baku", "Luanda", "Lisbon"],
        "answer": "D"
    }
]
score = 0

def display_question(question):
    print(question["question"])
    for option in question["options"]:
        print(option)
    
def get_user_input():
    while True:
        answer = input("Your answer (A, B, C, or D): ").upper()
        if answer in ["A", "B", "C", "D"]:
            return answer
        else:
            print("Invalid input. Please enter A, B, C, or D.")

def check_answer(question, user_answer):
    if user_answer == question["answer"]:
        print("Correct!")
        return True
    else:
        print(f"Wrong! The correct answer is {question['answer']}.")
        return False

def display_final_score(score, total_questions):
    print(f"\nYour final score is {score} out of {total_questions}.")

for question in questions:
    display_question(question)
    user_answer = get_user_input()
    if check_answer(question, user_answer):
        score += 1
        
display_final_score(score, len(questions))
