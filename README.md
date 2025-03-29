# codesoft
 task 1 (to do list)
 def show_tasks(tasks):
    if not tasks:
        print("No tasks in the list!")
    else:
        for index, task in enumerate(tasks, 1):
            print(f"{index}. {task}")

def add_task(tasks, task):
    tasks.append(task)
    print(f"Task '{task}' added to the list.")

def mark_done(tasks, task_number):
    try:
        task = tasks.pop(task_number - 1)
        print(f"Task '{task}' marked as done!")
    except IndexError:
        print("Invalid task number!")

def main():
    tasks = []
    
    while True:
        print("\nTo-Do List:")
        print("1. Show tasks")
        print("2. Add task")
        print("3. Mark task as done")
        print("4. Exit")

        choice = input("Enter your choice: ")

        if choice == '1':
            show_tasks(tasks)
        elif choice == '2':
            task = input("Enter the task: ")
            add_task(tasks, task)
        elif choice == '3':
            show_tasks(tasks)
            task_number = int(input("Enter task number to mark as done: "))
            mark_done(tasks, task_number)
        elif choice == '4':
            print("Goodbye!")
            break
        else:
            print("Invalid choice! Please try again.")

if __name__ == "__main__":
    main()

