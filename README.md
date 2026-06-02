<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>العد التنازلي لكأس العالم 2026</title>

<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&display=swap" rel="stylesheet">

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Cairo',sans-serif;
}

body{
    min-height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    text-align:center;
    color:white;

    background:
    linear-gradient(rgba(0,0,0,.65), rgba(0,0,0,.75)),
    url('https://images.unsplash.com/photo-1574629810360-7efbbe195018?auto=format&fit=crop&w=1600&q=80');

    background-size:cover;
    background-position:center;
}

.container{
    width:95%;
    max-width:900px;
    padding:30px;
    backdrop-filter:blur(8px);
    background:rgba(0,0,0,0.35);
    border:1px solid rgba(255,255,255,0.15);
    border-radius:25px;
}

.name{
    font-size:3rem;
    font-weight:900;
    color:#FFD700;
    margin-bottom:10px;
    text-shadow:0 0 15px rgba(255,215,0,.7);
}

.title{
    font-size:2rem;
    font-weight:700;
    margin-bottom:30px;
}

.countdown{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:15px;
}

.box{
    background:rgba(255,255,255,0.08);
    padding:20px;
    border-radius:20px;
}

.number{
    font-size:3rem;
    font-weight:900;
}

.label{
    font-size:1rem;
    opacity:.9;
}

.footer{
    margin-top:25px;
    font-size:1rem;
    opacity:.8;
}

@media(max-width:700px){
    .countdown{
        grid-template-columns:repeat(2,1fr);
    }

    .name{
        font-size:2rem;
    }

    .title{
        font-size:1.4rem;
    }
}
</style>
</head>

<body>

<div class="container">

    <div class="name">أيوب فكري</div>

    <div class="title">
        العد التنازلي لانطلاق كأس العالم 2026
    </div>

    <div class="countdown">

        <div class="box">
            <div class="number" id="days">0</div>
            <div class="label">يوم</div>
        </div>

        <div class="box">
            <div class="number" id="hours">0</div>
            <div class="label">ساعة</div>
        </div>

        <div class="box">
            <div class="number" id="minutes">0</div>
            <div class="label">دقيقة</div>
        </div>

        <div class="box">
            <div class="number" id="seconds">0</div>
            <div class="label">ثانية</div>
        </div>

    </div>

    <div class="footer">
        FIFA World Cup 2026™
    </div>

</div>

<script>

const worldCup = new Date("2026-06-11T00:00:00").getTime();

setInterval(function(){

    const now = new Date().getTime();
    const diff = worldCup - now;

    const days = Math.floor(diff / (1000*60*60*24));
    const hours = Math.floor((diff % (1000*60*60*24)) / (1000*60*60));
    const minutes = Math.floor((diff % (1000*60*60)) / (1000*60));
    const seconds = Math.floor((diff % (1000*60)) / 1000);

    document.getElementById("days").innerHTML = days;
    document.getElementById("hours").innerHTML = hours;
    document.getElementById("minutes").innerHTML = minutes;
    document.getElementById("seconds").innerHTML = seconds;

},1000);

</script>

</body>
</html>
