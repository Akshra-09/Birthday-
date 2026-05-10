<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<link href="https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap" rel="stylesheet">

<title>Happy Birthday ❤️</title>

<style>
body{
    margin:0;
    font-family:'Segoe UI';
    background:black;
    color:white;
    overflow:hidden;
}

/* PAGES */
.page{
    display:none;
    height:100vh;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    text-align:center;
    padding:20px;
}
.active{
    display:flex;
}

/* FLEX */
.flex{
    display:flex;
    align-items:center;
    justify-content:center;
    gap:20px;
    flex-wrap:wrap;
}

/* IMAGE */
.hero-img{
    width:150px;
    border-radius:20px;
}

/* LETTER */
.paper{
    background:#fff;
    color:#000;
    padding:20px;
    width:260px;
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
    font-size:16px;
}

/* FLOWERS */
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

video{
    border-radius:20px;
}
</style>
</head>

<body>

<!-- MUSIC -->
<audio id="music" loop>
    <source src="song.mp3" type="audio/mpeg">
</audio>

<!-- PAGE 1 -->
<div class="page active" id="p1">
    <div class="flex">
        <img src="photo1.jpg" class="hero-img">

        <div>
            <h2>Happy Birthday My Love ❤️</h2>
            <p>Click the letter 💌</p>

            <div style="font-size:60px;cursor:pointer"
            onclick="nextPage(2)">💌</div>
        </div>
    </div>
</div>

<!-- PAGE 2 -->
<div class="page" id="p2">

    <div class="flex">

        <div class="paper">
            Happy Birthday my love ❤️<br><br>

            “Happy Birthday to the most annoying person in the world 😏<br><br>

            You irritate me, tease me, make fun of me, and test my patience every single day… yet somehow you’re still my favorite person ever 😭❤️<br><br>

            No matter how much I complain about you, life feels incomplete without your stupid jokes, your drama, and your presence 🥹🫶🏻<br><br>

            Thank you for loving me in the most chaotic yet beautiful way possible 😚🫂<br><br>

            Stay happy, stay crazy, and stay mine forever.<br><br>

            Lysm, idiot 🧿😭🫂💌”
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

    <img src="photo4.jpg" width="120">

    <p id="msg"></p>

</div>

<!-- PAGE 5 -->
<div class="page" id="p5">

    <h2>Enter Password 🔐</h2>

    <input type="password" id="pass">

    <br>

    <button onclick="check()">Unlock</button>

    <p id="error"></p>

</div>

<!-- PAGE 6 -->
<div class="page" id="p6">

    <img src="photo5.jpg" width="120">

    <h2>🌸 These flowers are for you 💖</h2>

    <p>You are more beautiful than all of them ❤️</p>

    <button onclick="nextPage(7)">Next ➡️</button>

</div>

<!-- PAGE 7 -->
<div class="page" id="p7">

    <h2>Final Surprise 🎬</h2>

    <video controls width="500">
        <source src="final.mp4" type="video/mp4">
    </video>

    <button onclick="nextPage(8)">Next ➡️</button>

</div>

<!-- PAGE 8 -->
<div class="page" id="p8">

    <h2>Thank You For Everything ❤️</h2>

    <p>I love you forever 💗🥹</p>

</div>

<script>

/* MUSIC */
document.body.addEventListener("click", () => {
    document.getElementById("music").play();
}, {once:true});

/* PAGE SWITCH */
function nextPage(n){
    document.querySelectorAll(".page").forEach(page=>{
        page.classList.remove("active");
    });

    document.getElementById("p"+n).classList.add("active");
}

/* NO BUTTON */
function sayNo(){
    document.getElementById("msg").innerHTML =
    "Please say yes 🥹❤️";
}

/* PASSWORD */
function check(){

    let p = document.getElementById("pass").value;

    if(p === "kg11/2005"){

        nextPage(6);
        flowers();

    }else{

        document.getElementById("error").innerHTML =
        "Wrong password 😢";
    }
}

/* FLOWERS */
function flowers(){

    setInterval(()=>{

        let f = document.createElement("div");

        f.className = "flower";

        f.innerHTML = "🌸";

        f.style.left = Math.random()*100 + "vw";

        document.body.appendChild(f);

        setTimeout(()=>{
            f.remove();
        },5000);

    },300);
}

</script>

</body>
</html>
