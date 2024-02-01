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
      <input id="newWhatGradeInput" type="text" class="input-text" placeholder="What Grade">
      <input id="newEmailInput" type="email" class="input-text" placeholder="Email">
      <input id="newDOBInput" type="date" class="input-text" placeholder="Date of Birth">
      <select id="newGenderSelect" class="input-text">
        <option value="male">Male</option>
        <option value="female">Female</option>
        <option value="other">Other</option>
      </select>
      <button id="registerNewUserButton" class="button" onclick="registerUser()">Register</button>
      <button id="returnToLoginButton" class="button" onclick="returnToLogin()">Return to Login</button>
    </div>
  </div>

  <script>
    function showRegistrationForm() {
      // Hide login fields
      document.getElementById("usernameInput").style.display = "none";
      document.getElementById("passwordInput").style.display = "none";
      document.getElementById("loginButton").style.display = "none";
      document.getElementById("registerButton").style.display = "none";

      // Show registration fields
      document.getElementById("registrationForm").style.display = "block";
    }

    function registerUser() {
      const newUsername = document.getElementById("newUsernameInput").value;
      const newPassword = document.getElementById("newPasswordInput").value;
      const newWhatGrade = document.getElementById("newWhatGradeInput").value;
      const newEmail = document.getElementById("newEmailInput").value;
      const newDOB = document.getElementById("newDOBInput").value;
      const newGender = document.getElementById("newGenderSelect").value;

      // Make a POST request to register a new user
      fetch('http://127.0.0.1:5000/users', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          username: newUsername,
          password: newPassword,
          what_grade: newWhatGrade,
          email: newEmail,
          date_of_birth: newDOB,
          gender: newGender,
        }),
      })
      .then(response => response.json())
      .then(data => {
        console.log('User registration successful:', data);
        alert('Registration successful!');
        // Optionally, you can show a success message or redirect the user
        showLoginFields();
      })
      .catch(error => {
        console.error('Error registering user:', error);
        alert('Registration failed. Please try again.');
        // Handle error, show error message, etc.
      });
    }

    function showLoginFields() {
      // Show login fields
      document.getElementById("usernameInput").style.display = "block";
      document.getElementById("passwordInput").style.display = "block";
      document.getElementById("loginButton").style.display = "block";
      document.getElementById("registerButton").style.display = "block";

      // Hide registration fields
      document.getElementById("registrationForm").style.display = "none";
    }

    function returnToLogin() {
      showLoginFields();
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
          alert('Login successful');
          
          // Redirect the user to another link after successful login
          window.location.href = 'https://srivaidyas.github.io/student2.0/AD_compsci.html';
        } else {
          console.log('Login failed');
          alert('Login failed, please check your credentials');
        }
      })
      .catch(error => {
        console.error('Error:', error);
      });
    }
  </script>
</body>
</html>

