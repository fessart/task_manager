// Define an array to store the tasks.
let tasks = [];

// Function to add a new task to the task list.
function addTask(taskName) {
  if (taskName.trim() !== "") {
    tasks.push({ name: taskName, completed: false });
    console.log("Task added: " + taskName);
  } else {
    console.log("Task name cannot be empty!");
  }
}

// Function to mark a task as completed.
function completeTask(taskIndex) {
  if (taskIndex >= 0 && taskIndex < tasks.length) {
    tasks[taskIndex].completed = true;
    console.log("Task completed: " + tasks[taskIndex].name);
  } else {
    console.log("Invalid task index!");
  }
}

// Function to delete a task from the list.
function deleteTask(taskIndex) {
  if (taskIndex >= 0 && taskIndex < tasks.length) {
    const deletedTask = tasks.splice(taskIndex, 1);
    console.log("Task deleted: " + deletedTask[0].name);
  } else {
    console.log("Invalid task index!");
  }
}

// Function to list all tasks and their status.
function listTasks() {
  console.log("Tasks:");
  for (let i = 0; i < tasks.length; i++) {
    const status = tasks[i].completed ? "[X]" : "[ ]";
    console.log(i + 1 + ". " + status + " " + tasks[i].name);
  }
}

// Adding tasks using the addTask function.
addTask("Buy groceries");
addTask("Finish coding project");
addTask("Call mom");

// Marking the first task as completed.
completeTask(0);

// Listing the tasks.
listTasks();

// Deleting the second task.
deleteTask(1);

// Listing the updated tasks.
listTasks();
