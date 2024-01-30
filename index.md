---
layout: login
search_exclude: true
---


<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" type="text/css" href="your_stylesheet.css">
  <title>Login Page</title>
</head>
<body>
  <div class="container" style="text-align: center;">
    <h1>Welcome to Sri's Blog</h1>
    <input id="usernameInput" type="text" class="input-text" placeholder="Username">
    <input id="passwordInput" type="password" class="input-text" placeholder="Password">
    <button id="loginButton" class="button" onclick="loginUser()">Login</button>
    <button id="registerButton" class="button register-button" onclick="showRegistrationForm()">Register New User</button>

    <!-- Registration Form (Hidden by default) -->
    <div id="registrationForm" style="display: none;">
      <h2>Register New User</h2>
      <input id="newUsernameInput" type="text" class="input-text" placeholder="New Username">
      <input id="newPasswordInput" type="password" class="input-text" placeholder="New Password">
      <button id="registerNewUserButton" class="button" onclick="registerUser()">Register</button>
    </div>
  </div>

  <script>
    function showRegistrationForm() {
      document.getElementById("registrationForm").style.display = "block";
    }

    function registerUser() {
      const newUsername = document.getElementById("newUsernameInput").value;
      const newPassword = document.getElementById("newPasswordInput").value;

      // Make a POST request to register a new user
      fetch('http://127.0.0.1:5000/users', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          username: newUsername,
          password: newPassword,
        }),
      })
      .then(response => response.json())
      .then(data => {
        console.log('User registration successful:', data);
        alert('Registration successful!');
        // Optionally, you can show a success message or redirect the user
      })
      .catch(error => {
        console.error('Error registering user:', error);
        alert('Registration failed. Please try again.');
        // Handle error, show error message, etc.
      });
    }

    function loginUser() {
      const username = document.getElementById("usernameInput").value;
      const password = document.getElementById("passwordInput").value;

      // Make a POST request to check login credentials
      fetch('http://127.0.0.1:5000/login', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          username: username,
          password: password,
        }),
      })
      .then(response => {
        if (response.ok) {
          console.log('Login successful');
          alert('Login succesful, redirecting you to the main page');
          // Optionally, you can redirect the user to another link
          window.location.href = 'https://srivaidyas.github.io/student2.0/AD_compsci.html';
        } else {
          console.log('Login failed');
          alert('Login failed, please check you credentials');
          // Optionally, you can show an error message
        }
      })
      .catch(error => {
        console.error('Error:', error);
        // Handle error, show error message, etc.
      });
    }
  </script>
</body>
</html>
