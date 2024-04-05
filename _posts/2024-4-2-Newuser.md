---
toc: true
comments: false
layout: post
title: New User
description: 
type: hacks
courses: { compsci: {week: 29} }
image: images/plan-dice-760.jpg
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Create New User</title>
    <style>
        form {
            width: 300px;
            margin: 50px auto;
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

<form id="createUserForm">
    <input type="text" id="newUid" placeholder="User ID">
    <input type="text" id="newUsername" placeholder="Username">
    <input type="password" id="newPassword" placeholder="Password">
    <button type="submit">Create New User</button>
</form>

<script>
    document.getElementById("createUserForm").addEventListener("submit", async function(event) {
        event.preventDefault(); // Prevent form submission
        
        const newUid = document.getElementById("newUid").value;
        const newUsername = document.getElementById("newUsername").value;
        const newPassword = document.getElementById("newPassword").value;

        try {
            const response = await fetch('http://127.0.0.1:8086/api/users', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({ uid: newUid, _name: newUsername, password: newPassword })
            });

            if (response.ok) {
                console.log('New user created successfully');
            } else {
                console.error('Failed to create new user');
            }
        } catch (error) {
            console.error('Error:', error);
        }
    });
</script>

</body>
</html>
