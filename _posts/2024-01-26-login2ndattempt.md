---
toc: true
comments: false
layout: post
title: Index Page 2
description: 
type: hacks
courses: { compsci: {week: 20} }
---


<html>
  <head>
    <script src="https://code.jquery.com/jquery-3.6.4.min.js"></script>
    <style>
      /* Your existing Sass code here */
    </style>
  </head>
  <body>
    <div class="container" style="text-align: center;">
      <center>
        <h1>Welcome to Sri's Blog</h1>
      </center>
      <div id="registerModal" class="modal" style="display: none;">
        <div class="modal-content">
          <span class="close" onclick="closeRegisterModal()">&times;</span>
          <input
            type="text"
            class="input-text"
            id="registerUsername"
            placeholder="Username"
          />
          <input
            type="password"
            class="input-text"
            id="registerPassword"
            placeholder="Password"
          />
<button class="button" onclick="registerUser()">Register</button>
        </div>
      </div>
      <input
        type="text"
        class="input-text"
        id="loginUsername"
        placeholder="Username"
      />
      <input
        type="password"
        class="input-text"
        id="loginPassword"
        placeholder="Password"
      />
      <button class="button" onclick="login()">Login</button>
      <button
        class="button register-button"
        onclick="openRegisterModal()"
      >
        Register New User
      </button>
    </div>

    <script>
      function openRegisterModal() {
        document.getElementById("registerModal").style.display = "block";
      }

      function closeRegisterModal() {
        document.getElementById("registerModal").style.display = "none";
      }

      function registerUser() {
    var username = $("#registerUsername").val();
    var password = $("#registerPassword").val();

    $.ajax({
        type: "POST",
        url: "http://127.0.0.1:5000/users",
        contentType: "application/json",
        data: JSON.stringify({ username: username, password: password }),
        success: function (data) {
            alert("User registered successfully!");
            closeRegisterModal();  // Ensure the modal is closed after successful registration
        },
        error: function (xhr, status, error) {
            console.error("Error registering user:", error);
            console.log(xhr.responseText);
            alert("Error registering user. Check the console for details.");
        },
    });
}


      function login() {
        var username = $("#loginUsername").val();
        var password = $("#loginPassword").val();

        $.ajax({
          type: "POST",
          url: "http://127.0.0.1:5000/login",
          contentType: "application/json",
          data: JSON.stringify({ username: username, password: password }),
          success: function (data) {
            alert("Login successful!");
            window.location.href =
              "https://srivaidyas.github.io/student2.0/AD_compsci.html";
          },
          error: function (error) {
            alert("Login failed. Please check your credentials.");
          },
        });
      }
    </script>
  </body>
</html>
