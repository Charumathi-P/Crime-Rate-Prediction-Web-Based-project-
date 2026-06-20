Crime-Rate-Prediction/
│
├── index.html
├── style.css
├── script.js
├── README.md
│
├── Backend/
│   ├── HomeController.cs
│   ├── CrimePredictionController.cs
│   └── Database.cs
│
├── Models/
│   ├── CrimeData.cs
│   └── PredictionModel.cs
│
├── Database/
│   └── CrimeDB.sql
│
└── ML/
└── CrimePredictionModel.cs

---

Sample HTML (index.html)

<!DOCTYPE html>

<html>
<head>
    <title>Crime Rate Prediction</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Crime Rate Prediction System</h1>

```
<form>
    <input type="text" placeholder="Enter Location">
    <button type="submit">Predict Crime Rate</button>
</form>

<div id="result"></div>

<script src="script.js"></script>
```

</body>
</html>

---

Sample CSS (style.css)

body{
font-family: Arial, sans-serif;
text-align:center;
margin-top:50px;
}

input{
padding:10px;
}

button{
padding:10px 20px;
}

---

Sample JavaScript (script.js)

function predictCrime(){
document.getElementById("result").innerHTML =
"Predicted Crime Risk: Medium";
}

---

Sample C# Model (CrimeData.cs)

public class CrimeData
{
public string Location { get; set; }
public int CrimeCount { get; set; }
public string CrimeType { get; set; }
}

---

Sample Prediction Model (PredictionModel.cs)

public class PredictionModel
{
public string Location { get; set; }
public double PredictedCrimeRate { get; set; }
}

---

Sample SQL Table

CREATE TABLE CrimeData (
Id INT PRIMARY KEY IDENTITY(1,1),
Location VARCHAR(100),
CrimeType VARCHAR(100),
CrimeCount INT,
CrimeDate DATE
);

---

README Description

A web-based Crime Rate Prediction System that analyzes historical crime data using machine learning techniques to forecast future crime trends and identify potential hotspots. Developed using HTML, CSS, JavaScript, C#, ASP.NET, SQL Server, and Machine Learning concepts.
