---
toc: true
comments: false
layout: post
title: ML Project
description: 
type: tangibles
courses: { compsci: {week: 27} }
image: images/plan-dice-760.jpg
---

<html>
<head>
<style>
body {
font-family: 'Poppins', sans-serif;
background-color: #f4f4f4;
color: #333;
line-height: 1.6;
}
h1 {
text-align: center;
font-size: 48px;
margin-bottom: 30px;
color: #2c3e50;
animation: bounce 1s infinite alternate;
}
p#predictionResult {
text-align: center;
font-size: 50px;
margin-top: 20px;
}
.container {
width: 50%;
margin: 0 auto;
}
.input-box {
display: inline-block;
margin-bottom: 20px;
text-align: center;
}
.input-box label {
display: block;
margin-bottom: 5px;
font-size: 18px;
color: #2c3e50;
}
.input-box input {
width: 250px;
padding: 10px;
border: 2px solid #3498db;
border-radius: 10px;
font-size: 16px;
transition: border-color 0.3s;
}
.input-box input:focus {
outline: none;
border-color: #2980b9;
}
.btn {
display: inline-block;
background-color: #27ae60;
color: #fff;
padding: 10px 20px;
border: none;
border-radius: 5px;
cursor: pointer;
font-size: 16px;
transition: background-color 0.3s;
}
.btn:hover {
background-color: #219652;
}
</style>
</head>
<body>
<center>
<h1>Admission Predictor</h1>
<p id="predictionResult"></p>
<div class="container">
<div class="input-box">
<label for="sat">SAT Score:</label><br>
<input type="number" id="sat" name="sat" placeholder="SAT score">
</div>
<div class="input-box">
<label for="gpa">GPA:</label><br>
<input type="number" step="0.01" id="gpa" name="gpa" placeholder="GPA">
</div>
<div class="input-box">
<label for="extracurriculars">Extracurriculars:</label><br>
<input type="number" id="Extracurricular_Activities" name="Extracurricular_Activities" placeholder="Extracurriculars">
</div>
<br>
<button class="btn" id="checkCompatibility">Check</button>
</div>
</center>
<script>
function makePrediction() {
var gpa = document.getElementById("gpa").value;
var sat = document.getElementById("sat").value;
var extracurriculars = document.getElementById("Extracurricular_Activities").value;
if (sat > 1600) {
alert("SAT score cannot exceed 1600");
return;
}
if (gpa > 5) {
alert("GPA cannot exceed 5");
return;
}
var data = {
gpa: gpa,
SAT: sat,
Extracurricular_Activities: extracurriculars
};
fetch('http://127.0.0.1:8086/api/users/Prediction', {
method: 'POST',
headers: {
'Content-Type': 'application/json' 
},
body: JSON.stringify(data)
})
.then(response => {
if (!response.ok) {
throw new Error('Network response was not ok');
}
return response.json();
})
.then(result => {
var predictionResultElement = document.getElementById("predictionResult");
if (result === "Accepted") {
predictionResultElement.style.color = "green";
} else if (result === "Waitlisted") {
predictionResultElement.style.color = "yellow";
} else if (result === "Rejected") {
predictionResultElement.style.color = "red";
}
predictionResultElement.textContent = result;
alert("Prediction successful: " + result); 
})
.catch(error => {
console.error('Error:', error);
alert("Prediction request failed: " + error.message); 
});
}
document.getElementById("checkCompatibility").addEventListener("click", makePrediction);
</script>
</body>
</html>
