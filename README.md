<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login Form</title>
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
    <p id="message"></p>

    <script>
        document.getElementById('loginForm').addEventListener('submit', function(event) {
            event.preventDefault(); // Prevent default form submission

            // Fetch input values
            var username = document.getElementById('username').value;
            var password = document.getElementById('password').value;

            // Basic validation
            if (username === '' || password === '') {
                document.getElementById('message').innerHTML = "Please enter both username and password.";
                return;
            }

            // Store data in localStorage
            localStorage.setItem('username', username);
            localStorage.setItem('password', password);

            // Display message
            document.getElementById('message').innerHTML = "Your login data has been stored.";

            // Reset form
            document.getElementById('loginForm').reset();
        });

        // Load stored login data on page load
        window.onload = function() {
            var storedUsername = localStorage.getItem('username');
            var storedPassword = localStorage.getItem('password');

            if (storedUsername && storedPassword) {
                document.getElementById('message').innerHTML = "Your stored login data:<br>";
                document.getElementById('message').innerHTML += "Username: " + storedUsername + "<br>";
                document.getElementById('message').innerHTML += "Password: " + storedPassword + "<br>";
            }
        };
    </script>
</body>
</html>
