---
toc: true
comments: false
layout: post
title: Database Testing
description: 
type: tangibles
courses: { compsci: {week: 29} }
image: images/plan-dice-760.jpg
---
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Post Game Points</title>
</head>
<body>
    <h2>Enter Game Points</h2>
    <input type="number" id="gamePointsInput" placeholder="Enter game points">
    <button onclick="postGamePoints()">Submit</button>
    <script>
        function postGamePoints() {
            const gamePoints = document.getElementById("gamePointsInput").value;
            if (gamePoints === "") {
                alert("Please enter game points");
                return;
            }

            const postData = {
                database: "game_points",
                value: parseInt(gamePoints)
            };

            fetch("http://127.0.0.1:8085/users", {
                method: "POST",
                headers: {
                    "Content-Type": "application/json"
                },
                body: JSON.stringify(postData)
            })
            .then(response => {
                if (!response.ok) {
                    throw new Error("Failed to post game points");
                }
                alert("Game points posted successfully");
            })
            .catch(error => {
                alert(error.message);
            });
        }
    </script>
</body>
</html>




