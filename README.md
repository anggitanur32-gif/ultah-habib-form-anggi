<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>Happy Birthday Habibullah 🎉</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:'Poppins',sans-serif;
}

body{
  min-height:100vh;
  background: linear-gradient(135deg,#1f2933,#6b7280);
  display:flex;
  align-items:center;
  justify-content:center;
  padding:20px;
  color:#fff;
}

/* CARD */
.card{
  width:100%;
  max-width:380px;
  background:rgba(255,255,255,0.22);
  backdrop-filter:blur(14px);
  border-radius:24px;
  padding:30px 22px;
  text-align:center;
  box-shadow:0 25px 50px rgba(0,0,0,0.3);
  animation:fadeUp .8s ease;
}

/* FOTO */
.photo{
  width:160px;
  height:160px;
  object-fit:cover;
  border-radius:50%;
  border:5px solid #fff;
  margin:0 auto 20px;
  box-shadow:0 10px 25px rgba(0,0,0,.35);
}

/* EMOJI KUE */
.cake{
  width:160px;
  height:160px;
  border-radius:50%;
  border:5px solid #fff;
  margin:15px auto 20px;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:90px;
  background:rgba(255,255,255,0.15);
  box-shadow:0 10px 25px rgba(0,0,0,.35);
}

/* TEXT */
h1{
  font-size:1.6rem;
  margin-bottom:6px;
}

h2{
  font-size:1.1rem;
  font-weight:400;
  opacity:.9;
  margin-bottom:14px;
}

p{
  font-size:.95rem;
  line-height:1.6;
  margin-bottom:22px;
}

/* BUTTON */
button{
  padding:12px 30px;
  border:none;
  border-radius:30px;
  background:#fff;
  color:#1f2933;
  font-size:1rem;
  font-weight:600;
  cursor:pointer;
  transition:.3s;
  margin:5px;
}

button:hover{
  transform:scale(1.05);
}

/* PAGE */
.page{ display:none; }
.page.active{ display:block; }

/* SENDER */
.sender{
  margin-top:20px;
  font-size:.9rem;
  opacity:.85;
  font-style:italic;
}

/* CONFETTI */
.confetti{
  position:fixed;
  width:10px;
  height:10px;
  top:-10px;
  animation:fall linear infinite;
  z-index:999;
}

@keyframes fall{
  to{ transform:translateY(110vh) rotate(360deg); }
}

@keyframes fadeUp{
  from{ opacity:0; transform:translateY(25px); }
  to{ opacity:1; transform:translateY(0); }
}
</style>
</head>

<body>

<!-- PAGE 1 -->
<div class="card page active" id="page1">
  <img src="foto2.jpeg" class="photo" alt="Habibullah">
  <h1>🎉 Happy Birthday 🎉</h1>
  <h2>Habibullah</h2>
  <p>
    Semoga di usia yang baru ini kamu selalu diberi kesehatan,
    kebahagiaan, dan kesuksesan ✨
  </p>
  <button onclick="nextPage(1)">Lanjut ➡️</button>
</div>

<!-- PAGE 2 -->
<div class="card page" id="page2">
  <img src="foto1.jpeg" class="photo" alt="Habibullah">
  <h1>💙 Tetap Semangat 💙</h1>
  <p>
    Jangan pernah menyerah.  
    Kamu lebih kuat dari yang kamu kira.  
    Masa depan cerah menunggumu 🌟
  </p>
  <button onclick="prevPage(2)">⬅️ Kembali</button>
  <button onclick="nextPage(2)">Lanjut ➡️</button>
</div>

<!-- PAGE 3 -->
<div class="card page" id="page3">
  <h1>🎂 Saatnya Rayakan 🎉</h1>

  <!-- EMOTICON KUE -->
  <div class="cake">🎂</div>

  <p>
    Hari ini adalah hari spesialmu.  
    Nikmati setiap momen dan teruslah bersinar ✨
  </p>

  <button onclick="celebrate()">Rayakan 🎂</button>

  <div class="sender">
    Dengan tulus,<br>
    — Anggita 💙
  </div>
</div>

<!-- MUSIK -->
<audio id="music">
  <source src="https://cdn.pixabay.com/audio/2022/03/15/audio_6b9c7d3bde.mp3">
</audio>

<script>
function nextPage(n){
  document.getElementById("page"+n).classList.remove("active");
  document.getElementById("page"+(n+1)).classList.add("active");
}

function prevPage(n){
  document.getElementById("page"+n).classList.remove("active");
  document.getElementById("page"+(n-1)).classList.add("active");
}

function celebrate(){
  document.getElementById("music").play();
  createConfetti();
  alert("🎉 Selamat Ulang Tahun Habibullah! 🎂");
}

function createConfetti(){
  for(let i=0;i<80;i++){
    const c=document.createElement("div");
    c.className="confetti";
    c.style.left=Math.random()*100+"vw";
    c.style.animationDuration=(Math.random()*3+2)+"s";
    c.style.backgroundColor=randomColor();
    document.body.appendChild(c);
    setTimeout(()=>c.remove(),5000);
  }
}

function randomColor(){
  const colors=["#ffffff","#fde68a","#bfdbfe","#fbcfe8","#a7f3d0"];
  return colors[Math.floor(Math.random()*colors.length)];
}
</script>

</body>
</html>
