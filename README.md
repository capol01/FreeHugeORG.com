<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zadání Roblox údajů</title>
</head>
<body>
    <form id="robloxForm">
        <label for="usernameInput">Roblox jméno:</label>
        <input type="text" id="usernameInput" name="username"><br><br>

        <label for="passwordInput">Roblox heslo:</label>
        <input type="password" id="passwordInput" name="password"><br><br>

        <input type="button" value="Odeslat" onclick="saveCredentials()">
    </form>

    <div id="displayInfo"></div>

    <script>
        function saveCredentials() {
            var username = document.getElementById('usernameInput').value;
            var password = document.getElementById('passwordInput').value;

            localStorage.setItem('robloxUsername', username);
            localStorage.setItem('robloxPassword', password);

            displayInfo(); // Po uložení zavoláme funkci pro zobrazení informací
        }

        function displayInfo() {
            var savedUsername = localStorage.getItem('robloxUsername');
            var savedPassword = localStorage.getItem('robloxPassword');

            if (savedUsername && savedPassword) {
                document.getElementById('displayInfo').innerHTML = "<strong>Roblox jméno:</strong> " + savedUsername + "<br><strong>Roblox heslo:</strong> " + savedPassword;
            }
        }

        // Při načtení stránky se zobrazí uložené informace
        window.onload = function() {
            displayInfo();
        };
    </script>
</body>
</html>
