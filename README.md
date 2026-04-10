# intrebare
index.html
<!DOCTYPE html>
<html lang="ro">
<head>
<meta charset="UTF-8">
<title>Pentru tine 💖</title>

<style>
body {
  margin: 0;
  text-align: center;
  font-family: Arial;
  background: linear-gradient(to top right, #ff758c, #ff7eb3);
  overflow: hidden;
  color: white;
}

h1 {
  margin-top: 100px;
  font-size: 32px;
}

button {
  padding: 15px 25px;
  font-size: 18px;
  margin: 15px;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  transition: 0.3s;
}

#yes {
  background-color: #ff4d6d;
}

#no {
  background-color: black;
  position: absolute;
}

/* inimioare */
.heart {
  position: absolute;
  animation: float 5s linear infinite;
}

@keyframes float {
  from { transform: translateY(100vh); opacity: 1; }
  to { transform: translateY(-10vh); opacity: 0; }
}
</style>
</head>

<body>

<h1 id="text">Vrei să ne împăcăm și să fii zâna mea? 🧚‍♀️</h1>

<button id="yes" onclick="yesClick()">DA 💖</button>
<button id="no" onclick="noClick()">NU 😈</button>

<audio id="music" loop>
  <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mpeg">
</audio>

<script>
let step = 0;

const messages = [
  "Sigur nu vrei? 🥺",
  "Chiar deloc? 😢",
  "Promit că o să fie diferit 💖",
  "Hai te rog… 🥹",
  "Mai dă-mi o șansă 😔",
  "Gândește-te la noi… 💭",
  "Ultima șansă 😳",
];

function noClick() {
  if (step < messages.length) {
    document.getElementById("text").innerText = messages[step];
    step++;

    const btn = document.getElementById("no");
    btn.style.left = Math.random() * (window.innerWidth - 100) + "px";
    btn.style.top = Math.random() * (window.innerHeight - 50) + "px";

    const yes = document.getElementById("yes");
    yes.style.transform = "scale(" + (1 + step * 0.25) + ")";
  } else {
    dramaticEnding();
  }
}

function yesClick() {
  document.getElementById("music").play();

  document.body.innerHTML = `
    <h1 style="margin-top:60px;">Știam eu… 😍</h1>
    <h2>Te iubesc 💖</h2>
    <p>Promit să fie mai bine de data asta 🥺</p>

    <img src="poza.jpg" style="
      margin-top:20px;
      width:300px;
      border-radius:20px;
      box-shadow:0 0 20px rgba(0,0,0,0.3);
    ">

    <p style="margin-top:20px;font-size:18px;">
      Tu și eu… mereu 💞
    </p>
  `;
}

function dramaticEnding() {
  document.body.innerHTML = `
    <h1 style="margin-top:120px;">😭 Ai ales NU...</h1>
    <h2>Dar eu tot te iubesc 💔</h2>
    <p>(Dacă te răzgândești… știi unde mă găsești)</p>
  `;
}

/* inimioare */
function createHeart() {
  const heart = document.createElement("div");
  heart.classList.add("heart");
  heart.innerHTML = "💖";
  heart.style.left = Math.random() * 100 + "vw";
  heart.style.fontSize = Math.random() * 20 + 20 + "px";
  document.body.appendChild(heart);

  setTimeout(() => heart.remove(), 5000);
}

setInterval(createHeart, 300);
</script>

</body>
</html>
