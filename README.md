
<!---
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        h1 {
            text-align: center;
        }
        #todo-list {
            list-style: none;
            padding: 0;
            margin: 0;
        }
        #todo-list li {
            margin-bottom: 10px;
            display: flex;
            align-items: center;
        }
        #todo-list li input[type="checkbox"] {
            margin-right: 10px;
        }
        #todo-list li label {
            line-height: 1.5;
        }
        #todo-list li.completed label {
            text-decoration: line-through;
            color: #ccc;
        }
        #new-todo,
        #add-button {
            padding: 10px;
            border: 1px solid #ddd;
            margin-top: 10px;
            display: block;
            width: 100%;
        }
        #add-button {
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>My To-Do List</h1>
    <ul id="todo-list"></ul>
    <input type="text" id="new-todo" placeholder="Add a new task">
    <button id="add-button">Add</button>
    <script>
        const todoList = document.getElementById('todo-list');
        const newTodoInput = document.getElementById('new-todo');
        const addButton = document.getElementById('add-button');

        let todos = []; // Array to store tasks

        function addTodo(text) {
          // Create a new list item element
          const listItem = document.createElement('li');
          
          // Create a checkbox for marking the task as complete
          const checkbox = document.createElement('input');
          checkbox.type = 'checkbox';
          checkbox.addEventListener('change', function() {
            listItem.classList.toggle('completed');
          });
          
          // Create a label element for the task text
          const label = document.createElement('label');
          label.textContent = text;
          
          // Add the checkbox and label to the list item
          listItem.appendChild(checkbox);
          listItem.appendChild(label);

          // Add the list item to the main list
          todoList.appendChild(listItem);
          
          // Add the task to the todos array
          todos.push({ text: text, completed: false });

          // Save todos to local storage (optional)
          localStorage.setItem('todos', JSON.stringify(todos));  
        }

        addButton.addEventListener('click', function() {
          const newTodoText = newTodoInput.value.trim();
          if (newTodoText) {
            addTodo(newTodoText);
            newTodoInput.value = ''; // Clear the input field
          }
        });

        // Load any existing todos from local storage on page load (optional)
        const storedTodos = localStorage.getItem('todos');
        if (storedTodos) {
          todos = JSON.parse(storedTodos);
          todos.forEach(todo => addTodo(todo.text));
        }
    </script>
</body>
</html>

--->
