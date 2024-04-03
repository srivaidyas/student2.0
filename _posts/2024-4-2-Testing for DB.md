---
toc: true
comments: false
layout: post
title: Database Testing
description: 
type: hacks
courses: { compsci: {week: 29} }
image: images/plan-dice-760.jpg
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>User Table</title>
    <style>
        table {
            border-collapse: collapse;
            width: 50%;
            margin: 20px auto;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: left;
        }
        th {
            background-color: #f2f2f2;
        }
    </style>
</head>
<body>

<table id="userTable">
    <thead>
        <tr>
            <th>User Name</th>
            <th>Tic Tac Toe Points</th>
        </tr>
    </thead>
    <tbody id="userDataBody">
        <!-- User data will be inserted here dynamically -->
    </tbody>
</table>

<script>
    // Function to fetch user data from API
    async function fetchUserData() {
        try {
            const response = await fetch('http://127.0.0.1:8086/api/users', {
                method: 'GET', // Specify the GET method
            });
            const data = await response.json();
            return data;
        } catch (error) {
            console.error('Error fetching user data:', error);
        }
    }

    // Function to render user data in the table
    async function renderUserData() {
        const userData = await fetchUserData();
        const tableBody = document.getElementById('userDataBody');
        tableBody.innerHTML = ''; // Clear previous data

        userData.forEach(user => {
            const row = document.createElement('tr');
            row.innerHTML = `
                <td>${user._name}</td>
                <td>${user._tic_tac_toe_points}</td>
            `;
            tableBody.appendChild(row);
        });
    }

    // Render initial data
    renderUserData();
</script>

</body>
</html>



