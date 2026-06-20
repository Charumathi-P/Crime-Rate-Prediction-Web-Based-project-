<!DOCTYPE html>
<html>
<head>
    <title>Crime Rate Prediction System</title>

    <style>
        body{
            font-family: Arial, sans-serif;
            background:#f4f4f4;
            text-align:center;
            padding-top:50px;
        }

        .container{
            width:450px;
            margin:auto;
            background:white;
            padding:25px;
            border-radius:10px;
            box-shadow:0 0 10px rgba(0,0,0,0.2);
        }

        h1{
            color:#333;
        }

        input{
            width:80%;
            padding:10px;
            margin:10px;
            border:1px solid #ccc;
            border-radius:5px;
        }

        button{
            padding:10px 20px;
            background:#007bff;
            color:white;
            border:none;
            border-radius:5px;
            cursor:pointer;
        }

        button:hover{
            background:#0056b3;
        }

        #result{
            margin-top:20px;
            font-size:22px;
            font-weight:bold;
        }

        table{
            width:100%;
            margin-top:20px;
            border-collapse:collapse;
        }

        th,td{
            border:1px solid #ddd;
            padding:8px;
        }

        th{
            background:#007bff;
            color:white;
        }
    </style>
</head>

<body>

<div class="container">

    <h1>Crime Rate Prediction System</h1>

    <input type="text"
           id="location"
           placeholder="Enter Location">

    <input type="number"
           id="crimeCount"
           placeholder="Enter Previous Crime Count">

    <br>

    <button onclick="predictCrime()">
        Predict Crime Rate
    </button>

    <h2 id="result"></h2>

    <table>
        <tr>
            <th>Location</th>
            <th>Crime Count</th>
            <th>Prediction</th>
        </tr>
        <tbody id="crimeTable"></tbody>
    </table>

</div>

<script>

function predictCrime()
{
    let location =
    document.getElementById("location").value;

    let crime =
    parseInt(document.getElementById("crimeCount").value);

    if(location === "" || isNaN(crime))
    {
        alert("Please enter all details");
        return;
    }

    let prediction;

    if(crime < 50)
    {
        prediction = "Low Crime Risk";
    }
    else if(crime < 100)
    {
        prediction = "Medium Crime Risk";
    }
    else
    {
        prediction = "High Crime Risk";
    }

    document.getElementById("result").innerHTML =
    prediction;

    let row =
    "<tr>" +
    "<td>" + location + "</td>" +
    "<td>" + crime + "</td>" +
    "<td>" + prediction + "</td>" +
    "</tr>";

    document.getElementById("crimeTable").innerHTML += row;
}

</script>

</body>
</html>
