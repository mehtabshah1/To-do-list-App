# To-do-list-App
This is a simple and user-friendly To-Do List application built using Python. The project allows users to manage daily tasks efficientlly — add, view, update, and delete tasks with ease. It's perfect for beginners looking to understand basic Python programming and file handling (or GUI development, if applicable).
<!-- beginners  freindl project -->
# To-Do List Application
# Written by [Mehtab shah] - Beginner Python Project

# Stores all tasks
tasks = []

# Displays the main menu
def show_menu():
    print("\n====== TO-DO LIST MENU ======")
    print("1. Add a new task")
    print("2. Show all tasks")
    print("3. Remove a task")
    print("4. Exit the program")
    print("=============================")

# Adds a new task to the list
def add_task():
    task = input("Enter the task you want to add: ")
    tasks.append(task)
    print(f"Task added: {task}")

# Shows all current tasks
def show_tasks():
    if not tasks:
        print("Your task list is empty.")
    else:
        print("\nHere are your tasks:")
        for index, task in enumerate(tasks, start=1):
            print(f"{index}. {task}")

# Removes a task based on user input
def remove_task():
    if not tasks:
        print("There are no tasks to remove.")
        return
    show_tasks()
    try:
        number = int(input("Enter the number of the task to remove: "))
        if 1 <= number <= len(tasks):
            removed = tasks.pop(number - 1)
            print(f"Task removed: {removed}")
        else:
            print("Invalid task number.")
    except ValueError:
        print("Please enter a valid number.")

# Main loop
def main():
    print("Welcome to your personal To-Do List app!")
    while True:
        show_menu()
        choice = input("Choose an option (1-4): ")

        if choice == "1":
            add_task()
        elif choice == "2":
            show_tasks()
        elif choice == "3":
            remove_task()
        elif choice == "4":
            print("Thank you for using the To-Do List app. Goodbye!")
            break
        else:
            print("Invalid input. Please choose a number between 1 and 4.")

# Entry point
if __name__ == "__main__":
    main()
