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
  padding: 0;
  text-align: center;
  font-family: Arial, sans-serif;
  background: linear-gradient(to top right, #ff9a9e, #fad0c4);
  overflow: hidden;
}

h1 {
  margin-top: 100px;
  color: white;
  font-size: 32px;
}

button {
  padding: 15px 25px;
  font-size: 18px;
  margin: 15px;
  border: none;
  border-radius: 10px;
  cursor: pointer;
}

#yes {
  background-color: #ff4d6d;
  color: white;
}

#no {
  position: absolute;
  background-color: black;
  color: white;
}

/* inimioare */
.heart {
  position: absolute;
  color: red;
  animation: float 5s linear infinite;
}

@keyframes float {
  from {
    transform: translateY(100vh);
    opacity: 1;
  }
  to {
    transform: translateY(-10vh);
    opacity: 0;
  }
}
</style>
</head>

<body>

<h1>Vrei să ne împăcăm și să fii zâna mea? 🧚‍♀️</h1>

<button id="yes" onclick="love()">DA 💖</button>
<button id="no" onmouseover="moveButton()">NU 😈</button>

<script>
function moveButton() {
  const button = document.getElementById("no");
  const x = Math.random() * (window.innerWidth - 100);
  const y = Math.random() * (window.innerHeight - 50);
  button.style.left = x + "px";
  button.style.top = y + "px";
}

function love() {
  document.body.innerHTML = "<h1 style='color:white;margin-top:150px;'>Știam eu... Te iubesc 💖</h1>";
}

/* inimioare animate */
function createHeart() {
  const heart = document.createElement("div");
  heart.classList.add("heart");
  heart.innerHTML = "💖";
  heart.style.left = Math.random() * 100 + "vw";
  heart.style.fontSize = Math.random() * 20 + 20 + "px";
  document.body.appendChild(heart);

  setTimeout(() => {
    heart.remove();
  }, 5000);
}

setInterval(createHeart, 300);
</script>

</body>
</html>
