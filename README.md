<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login Form</title>
    <style>
        #result {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #ccc;
            display: none;
        }
    </style>
</head>
<body>
    <h2>Login Form</h2>
    <form id="loginForm">
        <label for="username">Username:</label><br>
        <input type="text" id="username" name="username"><br>
        <label for="password">Password:</label><br>
        <input type="password" id="password" name="password"><br><br>
        <input type="submit" value="Submit">
    </form>
    <div id="result">
        <h3>Your Login Data</h3>
        <p id="displayUsername"></p>
        <p id="displayPassword"></p>
    </div>

    <script>
        document.getElementById('loginForm').addEventListener('submit', function(event) {
            event.preventDefault(); // Prevent default form submission

            // Fetch input values
            var username = document.getElementById('username').value;
            var password = document.getElementById('password').value;

            // Display the result
            document.getElementById('displayUsername').innerText = "Username: " + username;
            document.getElementById('displayPassword').innerText = "Password: " + password;
            document.getElementById('result').style.display = 'block';

            // Optionally, clear the form
            document.getElementById('loginForm').reset();
        });
    </script>
</body>
</html>
