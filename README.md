<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SuccessAI</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial,sans-serif;
}

body{
    background:linear-gradient(135deg,#0f172a,#1e293b);
    color:white;
}

.hero{
    height:100vh;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    text-align:center;
    padding:20px;
}

.hero h1{
    font-size:4rem;
    margin-bottom:20px;
}

.hero p{
    font-size:1.3rem;
    max-width:700px;
    margin-bottom:30px;
}

button{
    padding:15px 40px;
    font-size:1.2rem;
    border:none;
    border-radius:50px;
    cursor:pointer;
    transition:0.3s;
}

button:hover{
    transform:scale(1.05);
}

#loadingScreen,
#resultScreen{
    position:fixed;
    top:0;
    left:0;
    width:100%;
    height:100%;
    display:none;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    background:black;
    z-index:1000;
}

#loadingText{
    font-size:2rem;
    margin-bottom:20px;
}

.loader{
    width:350px;
    height:30px;
    border:2px solid white;
}

.bar{
    height:100%;
    width:0%;
    background:#00ff00;
}

#percent{
    margin-top:15px;
    font-size:1.5rem;
}

#resultScreen h2{
    font-size:4rem;
    margin-bottom:30px;
}

#resultScreen p{
    font-size:2rem;
    text-align:center;
    line-height:1.8;
}
</style>
</head>

<body>

<section class="hero">
    <h1>SuccessAI</h1>

    <p>
        World's Most Advanced Future Prediction AI.
        Analyze your future success, career potential,
        and life trajectory in seconds.
    </p>

    <button onclick="startAnalysis()">
        Get Started Free
    </button>
</section>

<div id="loadingScreen">
    <div id="loadingText">Analyzing Your Future...</div>

    <div class="loader">
        <div class="bar" id="progressBar"></div>
    </div>

    <div id="percent">0%</div>
</div>

<div id="resultScreen">
    <h2>ANALYSIS COMPLETE</h2>

    <p>
        AI Detected: Exam in 2 Days.<br><br>

        57<br><br>

        Padhai Karo.<br><br>

        Yeh Sab Karne Se Fayda Nahi Hai.
    </p>
</div>

<script>
function startAnalysis()
{
    document.querySelector(".hero").style.display = "none";
    document.getElementById("loadingScreen").style.display = "flex";

    let progress = 0;

    let interval = setInterval(function()
    {
        progress++;

        document.getElementById("progressBar").style.width = progress + "%";
        document.getElementById("percent").innerHTML = progress + "%";

        if(progress >= 100)
        {
            clearInterval(interval);

            setTimeout(function()
            {
                document.getElementById("loadingScreen").style.display = "none";
                document.getElementById("resultScreen").style.display = "flex";
            }, 500);
        }

    }, 50);
}
</script>

</body>
</html>
