<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>Untuk Kamu ❤️</title>

<style>
body {
    margin: 0;
    overflow: hidden;
    font-family: 'Comic Sans MS', cursive;
    background: linear-gradient(to top, #ffd1dc, #ffe6f0);
    text-align: center;
}

/* Konten utama */
.container {
    position: relative;
    z-index: 2;
    padding-top: 80px;
}

h1 {
    font-size: 45px;
    color: #ff4d6d;
}

p {
    font-size: 20px;
    color: #444;
}

/* Tombol */
button {
    padding: 12px 25px;
    font-size: 18px;
    border: none;
    background: #ff4d6d;
    color: white;
    border-radius: 20px;
    cursor: pointer;
    margin-top: 20px;
}

button:hover {
    background: #ff1e4d;
}

/* Pesan */
#message {
    display: none;
    margin-top: 30px;
    font-size: 22px;
    color: #d6336c;
}

/* Love meter */
#loveMeter {
    font-size: 30px;
    margin-top: 15px;
}

/* Bunga jatuh */
.flower {
    position: fixed;
    top: -50px;
    animation: fall linear infinite;
    z-index: 1;
}

@keyframes fall {
    0% { transform: translateY(0) rotate(0); }
    100% { transform: translateY(100vh) rotate(360deg); }
}

/* Hati terbang */
.heart {
    position: fixed;
    color: red;
    animation: floatUp 4s linear forwards;
}

@keyframes floatUp {
    0% { opacity: 1; transform: translateY(0); }
    100% { opacity: 0; transform: translateY(-200px); }
}

</style>
</head>

<body>

<div class="container">
    <h1>Hai NAMA_DIA 💕</h1>
    <p>Dari: NAMA_KAMU 💌</p>

    <p>Aku punya sesuatu buat kamu...</p>

    <button onclick="startLove()">Klik di sini ya 😳</button>

    <div id="message">
        💖 Aku sayang kamu 💖 <br><br>
        Dari sekian banyak hal di dunia ini, <br>
        kamu adalah yang paling aku syukuri 🥰 <br><br>
        Jangan pergi ya... 💞
        
        <div id="loveMeter">❤️</div>
    </div>
</div>

<!-- Musik -->
<audio id="music" loop>
    <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mpeg">
</audio>

<script>
function startLove() {
    document.getElementById("message").style.display = "block";
    document.getElementById("music").play();

    increaseLove();
    heartsExplosion();
}

// Love meter naik
let love = 1;
function increaseLove() {
    setInterval(() => {
        if (love < 20) {
            love++;
            document.getElementById("loveMeter").innerHTML = "❤️".repeat(love);
        }
    }, 500);
}

// Bunga jatuh
function createFlower() {
    const flower = document.createElement("div");
    flower.classList.add("flower");
    flower.innerHTML = ["🌸","🌺","💮"][Math.floor(Math.random()*3)];

    flower.style.left = Math.random() * window.innerWidth + "px";
    flower.style.fontSize = (15 + Math.random() * 25) + "px";
    flower.style.animationDuration = (4 + Math.random() * 4) + "s";

    document.body.appendChild(flower);

    setTimeout(() => flower.remove(), 8000);
}
setInterval(createFlower, 300);

// Hati terbang saat klik
function heartsExplosion() {
    for (let i = 0; i < 20; i++) {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "❤️";

        heart.style.left = Math.random() * window.innerWidth + "px";
        heart.style.top = "60%";
        heart.style.fontSize = (15 + Math.random() * 20) + "px";

        document.body.appendChild(heart);

        setTimeout(() => heart.remove(), 4000);
    }
}
</script>

</body>
</html>