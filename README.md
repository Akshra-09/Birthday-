# Birthday-
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- ✨ Google Font -->
<link href="https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap" rel="stylesheet">

<title>Happy Birthday ❤️</title>

<style>
body{
    margin:0;
    font-family:'Segoe UI';
    background:black;
    color:white;
}

/* PAGES */
.page{
    display:none;
    height:100vh;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    text-align:center;
}
.active{display:flex}

/* 💖 FIRST PAGE */
.flex{
    display:flex;
    align-items:center;
    gap:20px;
}
.hero-img{
    width:150px;
    border-radius:20px;
}

/* 💌 LETTER PAGE */
.paper{
    background:#fff;
    color:#000;
    padding:20px;
    width:250px;
    border-radius:10px;
    font-family:'Dancing Script', cursive;
    font-size:20px;
    box-shadow:0 0 20px pink;
}

/* BUTTON */
button{
    padding:10px 20px;
    border:none;
    border-radius:20px;
    background:#ff6b9c;
    color:white;
    margin:10px;
    cursor:pointer;
}

/* 🌸 FLOWERS */
.flower{
    position:fixed;
    top:-10px;
    font-size:24px;
    animation:fall 5s linear infinite;
}
@keyframes fall{
    0%{transform:translateY(0);}
    100%{transform:translateY(100vh);}
}
</style>
</head>

<body>

<!-- 🎶 MUSIC -->
<audio id="music" loop>
<source src="song.mp3">
</audio>

<!-- 💖 PAGE 1 -->
<div class="page active" id="p1">
    <div class="flex">
        <img src="photo1.jpg" class="hero-img">
        <div>
            <h2>Happy Birthday My Love ❤️</h2>
            <p>Click the letter 💌</p>
            <div style="font-size:60px;cursor:pointer" onclick="nextPage(2)">💌</div>
        </div>
    </div>
</div>

<!-- 💌 PAGE 2 -->
<div class="page" id="p2">
    <div class="flex">
        <div class="paper">
            Happy Birthday my love ❤️<br><br>
            “Happy Birthday to the most annoying person in the world.😏
You irritate me, tease me, make fun of me, and test my patience every single day… yet somehow you’re still my favorite person ever.😭❤️
No matter how much I complain about you, life feels incomplete without your stupid jokes, your drama, and your presence.🥹🫶🏻
Thank you for loving me in the most chaotic yet beautiful way possible.😚🫂
Stay happy, stay crazy, and stay mine forever.
Lysm, idiot.🧿😭🫂💌”
        </div>
        <div>
            <img src="photo2.jpg" width="120">
            <img src="photo3.jpg" width="120">
        </div>
    </div>
    <button onclick="nextPage(3)">Next ➡️</button>
</div>

<!-- PAGE 3 -->
<div class="page" id="p3">
    <h2>Our Memories 🎥</h2>

    <video controls width="500">
        <source src="video1.mp4" type="video/mp4">
    </video>

    <button onclick="nextPage(4)">Next ➡️</button>
</div>

<!-- PAGE 4 -->
<div class="page" id="p4">
    <h2>Do you want a surprise gift? 🎁</h2>

    <div>
        <button onclick="sayNo()">No 😢</button>
        <button onclick="nextPage(5)">Yes ❤️</button>
    </div>

    <div>
        <img src="photo4.jpg"
        width="120">
    </div>
<div>
    <lp id="msg"></p>
</div>


<!-- 🔐 PASSWORD -->
<div class="page" id="p5">
    <h2>Enter Password 🔐</h2>
    <input type="password" id="pass">
    <br>
    <button onclick="check()">Unlock</button>
    <p id="error"></p>
</div>

<!-- 🌸 FLOWER PAGE -->
<div class="page" id="p6">
    </div>
        <div>
            <img src="photo5.jpg" width="120">
        </div>
    <div>
        <h2>🌸 These flowers are for you 💖</h2>
         <p>You are more beautiful than all of them ❤️</p>
         <button onclick="nextPage(7)">Next          ➡️</button>
</div>

<!-- 🎬 FINAL -->
<div class="page" id="p7">
    <h2>Final Surprise 🎬</h2>
    <video src="final.mp4" 
    controls width="500"></video>
    <button onclick="nextPage(8)">Next ➡️</button>
</div>

<!-- ❤️ END -->
<div class="page" id="p8">
    <h2>Thank You For Everything ❤️</h2>
    <p>I love you forever💗🥹</p>
</div>

<script>
/* MUSIC */
document.body.addEventListener("click",()=>{
    document.getElementById("music").play();
},{once:true});

/* PAGE SWITCH */
function nextPage(n){
    document.querySelectorAll(".page").forEach(p=>p.classList.remove("active"));
    document.getElementById("p"+n).classList.add("active");
}

/* NO BUTTON */
function sayNo(){
    document.getElementById("msg").innerHTML="Please say yes 🥹❤️";
}

/* PASSWORD */
function check(){
    let p=document.getElementById("pass").value;
    if(p==="kg11/2005"){
        nextPage(6);
        flowers();
    } else {
        document.getElementById("error").innerHTML="Wrong password 😢";
    }
}

/* FLOWERS */
function flowers(){
    setInterval(()=>{
        let f=document.createElement("div");
        f.className="flower";
        f.innerHTML="🌸";
        f.style.left=Math.random()*100+"vw";
        document.body.appendChild(f);
        setTimeout(()=>f.remove(),5000);
    },300);
}
</script>

</body>
</html>
