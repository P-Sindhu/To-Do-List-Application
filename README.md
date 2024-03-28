# To-Do-List-Application

```python
class TodoList:
    def __init__(self):
        self.tasks = []
```
Here, a class named `TodoList` is defined. It represents a todo list. The `__init__` method is a constructor method, which initializes a new instance of the `TodoList` class. It initializes an empty list `self.tasks` to store the tasks.

```python
    def add_task(self, task):
        self.tasks.append(task)
```
This method `add_task` is used to add a new task to the todo list. It takes a parameter `task`, which is the task to be added, and appends it to the `self.tasks` list.

```python
    def complete_task(self, task_index):
        if 0 <= task_index < len(self.tasks):
            self.tasks[task_index] += " (Completed)"
        else:
            print("Invalid task index.")
```
The `complete_task` method marks a task as completed. It takes an index (`task_index`) as input, which represents the position of the task to be marked as completed. If the index is valid (i.e., within the range of existing tasks), it appends "(Completed)" to the task's description. Otherwise, it prints "Invalid task index."

```python
    def remove_task(self, task_index):
        if 0 <= task_index < len(self.tasks):
            del self.tasks[task_index]
        else:
            print("Invalid task index.")
```
The `remove_task` method removes a task from the todo list. Similar to `complete_task`, it takes an index (`task_index`) as input, representing the position of the task to be removed. If the index is valid, it removes the task at that index from the `self.tasks` list. Otherwise, it prints "Invalid task index."

```python
    def display_tasks(self):
        print("Tasks:")
        for index, task in enumerate(self.tasks):
            print(f"{index + 1}. {task}")
```
The `display_tasks` method is used to display all the tasks in the todo list. It iterates over each task in `self.tasks` using the `enumerate` function to get both the index and the task itself. Then, it prints each task along with its index.

The `main` function is where the user interacts with the todo list through a simple command-line interface:

```python
def main():
    todo_list = TodoList()

    while True:
        print("\nOptions:")
        print("1. Add Task")
        print("2. Complete Task")
        print("3. Remove Task")
        print("4. Display Tasks")
        print("5. Quit")

        choice = input("Enter your choice: ")

        if choice == '1':
            task = input("Enter the task: ")
            todo_list.add_task(task)
        elif choice == '2':
            task_index = int(input("Enter the index of the task to complete: ")) - 1
            todo_list.complete_task(task_index)
        elif choice == '3':
            task_index = int(input("Enter the index of the task to remove: ")) - 1
            todo_list.remove_task(task_index)
        elif choice == '4':
            todo_list.display_tasks()
        elif choice == '5':
            print("Exiting...")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
```
This function creates an instance of `TodoList`, then enters a loop where it repeatedly displays a menu of options for the user to interact with the todo list. Depending on the user's choice, it calls the corresponding method of the `TodoList` instance (`add_task`, `complete_task`, `remove_task`, or `display_tasks`). If the user chooses to quit (`choice == '5'`), the loop exits and the program ends.
