---
toc: true
comments: false
layout: post
title: Decrypter
description: 
type: hacks
courses: { compsci: {week: 36} }
image: images/plan-dice-760.jpg
---

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Decrypter</title>
<style>
    body {
        font-family: 'Roboto', sans-serif;
        background-color: #000;
        color: #fff;
    }
    input[type="text"] {
        padding: 15px;
        font-size: 18px;
        width: 70%;
        max-width: 500px;
        box-sizing: border-box;
        border: none;
        border-radius: 20px;
        text-align: center;
        box-shadow: 0 0 0 2px #fff; /* 2px white outline */
    }
    /* Styling for Fetch Data button */
    button {
        background-color: #4CAF50; /* Green */
        border: none;
        color: white;
        padding: 15px 32px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 16px;
        margin: 4px 2px;
        cursor: pointer;
        border-radius: 20px;
        transition: background-color 0.3s ease;
    }

    button:hover {
        background-color: #45a049; /* Darker green */
    }
</style>
</head>
<body>

<h1>Decrypter</h1>
<br><br>
<center>
<input type="text" id="recordIdInput" placeholder="Enter Record ID">
<button onclick="fetchData()">Fetch Data</button>
</center>

<div id="output"></div>

<script>
function fetchData() {
    var recordId = document.getElementById("recordIdInput").value;
    fetch(`/encrypted_data/${recordId}`)
    .then(response => {
        if (!response.ok) {
            throw new Error('Network response was not ok');
        }
        return response.json();
    })
    .then(data => {
        // Extract raw_data from the fetched data
        var raw_data = data.raw_data;
        // Display raw_data in output div
        document.getElementById("output").innerHTML = "<h2>Raw Data:</h2>" + raw_data;
    })
    .catch(error => {
        console.error('There was a problem with the fetch operation:', error);
        // Display error message
        document.getElementById("output").innerHTML = "Error fetching data. Please try again.";
    });
}
</script>

</body>
</html>


