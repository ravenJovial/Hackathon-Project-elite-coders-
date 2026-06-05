# Hackathon-Project-elite-coders-
hello
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Smart Study Planner</title>

<style>
body{
    font-family: Arial, sans-serif;
    background:#f4f4f4;
    display:flex;
    justify-content:center;
    align-items:center;
    min-height:100vh;
}
.container{
    background:white;
    padding:20px;
    border-radius:12px;
    width:400px;
    box-shadow:0 0 15px rgba(0,0,0,0.1);
}
h2{text-align:center;}
input,button{
    width:100%;
    padding:10px;
    margin-top:10px;
}
button{
    background:#007bff;
    color:white;
    border:none;
    cursor:pointer;
}
.task{
    margin-top:10px;
    padding:10px;
    background:#eef;
    border-radius:8px;
}
.high{border-left:5px solid red;}
.medium{border-left:5px solid orange;}
.low{border-left:5px solid green;}
</style>
</head>

<body>

<div class="container">
    <h2>Smart Study Planner</h2>

    <input type="text" id="taskName" placeholder="Enter Subject/Task">
    <input type="number" id="hours" placeholder="Hours Left for Exam">
    <button onclick="addTask()">Generate Priority</button>

    <div id="tasks"></div>
</div>

<script>
function addTask(){
    let task=document.getElementById("taskName").value;
    let hours=parseInt(document.getElementById("hours").value);

    if(!task || !hours){
        alert("Fill all fields");
        return;
    }

    let priority="Low";
    let cls="low";

    if(hours<=24){
        priority="High";
        cls="high";
    }
    else if(hours<=72){
        priority="Medium";
        cls="medium";
    }

    let div=document.createElement("div");
    div.className="task "+cls;
    div.innerHTML=
    `<b>${task}</b><br>
    Priority: ${priority}<br>
    Hours Remaining: ${hours}`;

    document.getElementById("tasks").appendChild(div);

    document.getElementById("taskName").value="";
    document.getElementById("hours").value="";
}
</script>

</body>
</html>
