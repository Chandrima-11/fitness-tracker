# fitness-tracker
# fitness_tracker.py

class User:
    def __init__(self, username):
        self.username = username
        self.steps = 0
        self.calories_burned = 0
        self.daily_goal = 10000  # Default daily step goal

    def record_steps(self, num_steps):
        self.steps += num_steps
        self.calories_burned += num_steps * 0.05

    def set_daily_goal(self, goal):
        self.daily_goal = goal

    def get_summary(self):
        return f"{self.username}'s Stats:\nSteps: {self.steps} | Calories Burned: {self.calories_burned:.2f}"

def main():
    username = input("Enter your username: ")
    user = User(username)

    while True:
        print("\n1. Record Steps")
        print("2. Set Daily Goal")
        print("3. View Stats")
        print("4. Exit")
        choice = input("Enter your choice (1/2/3/4): ")

        if choice == "1":
            steps = int(input("Enter the number of steps: "))
            user.record_steps(steps)
        elif choice == "2":
            goal = int(input("Enter your daily step goal: "))
            user.set_daily_goal(goal)
        elif choice == "3":
            print(user.get_summary())
        elif choice == "4":
            print("Thank you for using the Fitness Tracker!")
            break
        else:
            print("Invalid choice. Please select 1, 2, 3, or 4.")

if __name__ == "__main__":
    main()
