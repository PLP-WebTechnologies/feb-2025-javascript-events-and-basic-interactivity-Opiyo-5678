# feb-2025-avasjcript-events-and-basic-interactivity

 a simple To-Do List App using JavaScript events and basic interactivity. The app will allow users to:

Add tasks

Mark tasks as completed

Delete tasks


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
        }
        .container {
            max-width: 400px;
            margin: auto;
            background: #f4f4f4;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        ul {
            list-style: none;
            padding: 0;
        }
        li {
            display: flex;
            justify-content: space-between;
            background: white;
            padding: 10px;
            margin: 5px 0;
            border-radius: 5px;
            cursor: pointer;
        }
        .completed {
            text-decoration: line-through;
            color: gray;
        }
        button {
            background: red;
            color: white;
            border: none;
            padding: 5px;
            cursor: pointer;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>To-Do List</h2>
        <input type="text" id="taskInput" placeholder="Add a new task...">
        <button onclick="addTask()">Add</button>
        <ul id="taskList"></ul>
    </div>

    <script>
        function addTask() {
            let taskInput = document.getElementById("taskInput");
            let taskText = taskInput.value.trim();
            
            if (taskText === "") {
                alert("Please enter a task!");
                return;
            }
            
            let li = document.createElement("li");
            li.textContent = taskText;
            
            li.addEventListener("click", function() {
                this.classList.toggle("completed");
            });
            
            let deleteBtn = document.createElement("button");
            deleteBtn.textContent = "X";
            deleteBtn.onclick = function() {
                li.remove();
            };
            
            li.appendChild(deleteBtn);
            document.getElementById("taskList").appendChild(li);
            
            taskInput.value = "";
        }
    </script>
</body>
</html>
