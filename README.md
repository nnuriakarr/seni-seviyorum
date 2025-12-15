<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>Pelin benimle çıkar mısın?</title>
<style>
body {
    margin: 0;
    height: 100vh;
    background: linear-gradient(135deg, #ff9a9e, #fad0c4);
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: 'Segoe UI', Arial;
    overflow: hidden;
    position: relative;
}

/* Uçan kalpler */
@keyframes float {
    0% { transform: translateY(0) rotate(0deg); opacity:1;}
    100% { transform: translateY(-800px) rotate(360deg); opacity:0;}
}
.heart {
    position: absolute;
    font-size: 20px;
    animation: float 5s linear infinite;
}

/* Ana kutu */
.box {
    text-align: center;
    background: white;
    padding: 40px;
    border-radius: 25px;
    border: 4px solid #ff4d6d;
    box-shadow: 0 15px 35px rgba(0,0,0,0.25);
    max-width: 350px;
}

h2 {
    color: #ff4d6d;
    margin-bottom: 25px;
}

/* Butonlar */
button {
    padding: 12px 30px;
    font-size: 20px;
    border-radius: 25px;
    border: none;
    cursor: pointer;
    margin: 10px;
    transition: all 0.3s ease;
    font-weight: bold;
}
#yes {
    background: #ff4d6d;
    color: white;
}
#yes:hover {
    transform: scale(1.1);
}
#no {
    background: #ffd700;
    color: #333;
    position: absolute;
}
</style>
</head>
<body>

<div class="box" id="mainBox">
    <h2>Pelin benimle çıkar mısın? 💖</h2>
    <button id="yes" onclick="yesClick()">Evet</button>
    <button id="no" onmouseover="moveNo()">Hayır</button>
</div>

<script>
// Uçan kalpler oluştur
for(let i=0;i<20;i++){
    let heart = document.createElement("div");
    heart.className = "heart";
    heart.style.left = Math.random()*100 + "vw";
    heart.style.fontSize = 15+Math.random()*25 + "px";
    heart.style.animationDuration = 3+Math.random()*5 + "s";
    heart.innerHTML = "❤️";
    document.body.appendChild(heart);
}

// Hayır butonu kaçıyor
function moveNo() {
    const noBtn = document.getElementById("no");
    const x = Math.random() * (window.innerWidth - 100);
    const y = Math.random() * (window.innerHeight - 50);
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
}

// Evet mesajı
function yesClick() {
    document.body.innerHTML = `
    <div style="text-align:center;padding:30px;font-family:'Segoe UI',Arial;">
        <h1 style="color:#ff4d6d;">❤️ Pelin ❤️</h1>
        <p style="font-size:17px; line-height:1.6; color:#444;">
        Pelin, aramızdaki kilometrelere rağmen bana sevmeyi ve sevilmeyi öğrettin.  
        Bunu söylemek için belki biraz erken ama  
        ömrümün sonuna kadar seninle olmak istiyorum.  
        Seni çok seviyorum ❤️❤️
        </p>
    </div>`;
}
</script>

</body>
</html>
