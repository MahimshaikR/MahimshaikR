#To-Do List Application
#Tasks-1
tasks = []

def show_menu():
    print("\n--- To-Do List Menu ---")
    print("1. View tasks")
    print("2. Add a task")
    print("3. Remove a task")
    print("4. Exit")

def view_tasks():
    if not tasks:
        print("\nYour to-do list is empty!")
    else:
        print("\nYour Tasks:")
        for i, task in enumerate(tasks, start=1):
            print(f"{i}. {task}")

def add_task():
    task = input("\nEnter the task you want to add: ")
    tasks.append(task)
    print(f"Task '{task}' added successfully!")

def remove_task():
    view_tasks()
    if tasks:
        try:
            task_number = int(input("\nEnter the number of the task to remove: "))
            if 1 <= task_number <= len(tasks):
                removed_task = tasks.pop(task_number - 1)
                print(f"Task '{removed_task}' removed successfully!")
            else:
                print("Invalid task number!")
        except ValueError:
            print("Please enter a valid number!")

def main():
    while True:
        show_menu()
        choice = input("\nEnter your choice (1-4): ")

        if choice == "1":
            view_tasks()
        elif choice == "2":
            add_task()
        elif choice == "3":
            remove_task()
        elif choice == "4":
            print("\nGoodbye! Have a productive day!")
            break
        else:
            print("Invalid choice! Please try again.")

if __name__ == "__main__":
    main()
