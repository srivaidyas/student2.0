---
toc: true
comments: false
layout: post
title: Login Screen Testing
description: 
type: hacks
courses: { compsci: {week: 29} }
image: images/plan-dice-760.jpg
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Authentication</title>
    <style>
        form {
            width: 300px;
            margin: 100px auto;
        }
        input {
            margin-bottom: 10px;
            width: 100%;
            padding: 8px;
        }
        button {
            width: 100%;
            padding: 10px;
            background-color: #007bff;
            color: white;
            border: none;
            cursor: pointer;
        }
    </style>
</head>
<body>

<form id="loginForm">
    <input type="text" id="uid" placeholder="Username">
    <input type="password" id="password" placeholder="Password">
    <button type="submit">Login</button>
</form>

<script>
    document.getElementById("loginForm").addEventListener("submit", async function(event) {
        event.preventDefault(); // Prevent form submission
        
        const uid = document.getElementById("uid").value;
        const password = document.getElementById("password").value;

        try {
            const response = await fetch('http://127.0.0.1:8086/api/users/authenticate', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({ uid, password })
            });

            if (response.ok) {
                // Redirect after successful authentication
                window.location.href = 'http://127.0.0.1:4100/student2.0//2024/04/02/Testing-for-DB.html';
            } else {
                console.error('Authentication failed');
            }
        } catch (error) {
            console.error('Error:', error);
        }
    });
</script>

</body>
</html>
