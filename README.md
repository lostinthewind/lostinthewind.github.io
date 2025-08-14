<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Skye's Special Page</title>
<style>
body {
font-family: 'Arial', sans-serif;
background: linear-gradient(120deg, #fce4ec, #f8bbd0);
color: #333;
margin: 0;
padding: 0;
text-align: center;
overflow-x: hidden;
}

header {
background-color: #f48fb1;
padding: 20px;
color: white;
position: relative;
z-index: 2;
}

h1 {
margin: 0;
}

.profile-img {
width: 200px;
height: 200px;
border-radius: 50%;
margin: 20px 0;
object-fit: cover;
transition: transform 0.3s;
position: relative;
z-index: 2;
}

.profile-img:hover {
transform: scale(1.1);
}

.content {
padding: 20px;
position: relative;
z-index: 2;
}

.gallery {
display: flex;
justify-content: center;
gap: 10px;
flex-wrap: wrap;
}

.gallery img {
width: 150px;
height: 150px;
object-fit: cover;
border-radius: 10px;
transition: transform 0.3s;
}

.gallery img:hover {
transform: rotate(10deg) scale(1.1);
}

button {
padding: 10px 20px;
font-size: 16px;
background-color: #f06292;
color: white;
border: none;
border-radius: 8px;
cursor: pointer;
transition: background-color 0.3s;
margin-top: 20px;
}

button:hover {
background-color: #ec407a;
}

footer {
background-color: #f48fb1;
color: white;
padding: 10px;
position: fixed;
bottom: 0;
width: 100%;
z-index: 2;
}

/* Hearts animation */
.heart {
position: absolute;
width: 20px;
height: 20px;
background-color: #f06292;
transform: rotate(45deg);
animation: float 5s linear infinite;
z-index: 1;
}

.heart::before,
.heart::after {
content: '';
position: absolute;
width: 20px;
height: 20px;
background-color: #f06292;
border-radius: 50%;
}

.heart::before {
top: -10px;
left: 0;
}

.heart::after {
left: 10px;
top: 0;
}

@keyframes float {
0% {
transform: translateY(0) rotate(45deg);
opacity: 1;
}
100% {
transform: translateY(-600px) rotate(45deg);
opacity: 0;
}
}
</style>
</head>
<body>
<header>
<h1>Welcome to Skye's Page 💖</h1>
</header>

<div class="content">
<img src="https://via.placeholder.com/200" alt="Skye" class="profile-img">
<p>Hello! I love Skye. 🌸</p>

<h2>Gallery</h2>
<div class="gallery">
<img src="https://via.placeholder.com/150" alt="Image 1">
<img src="https://via.placeholder.com/150" alt="Image 2">
<img src="https://via.placeholder.com/150" alt="Image 3">
</div>

<button onclick="showSurprise()">Click for a Surprise 💌</button>
<p id="surprise-message" style="font-size:18px; color:#f06292; margin-top:10px;"></p>
</div>

<footer>
Made with ❤️ for Skye
</footer>

<script>
function showSurprise() {
const messages = [
"Skye ml! 🌸",
"love! 💖",
"You make the world brighter! ☀️",
"Smile! Someone loves you! 🥰"
];
const randomIndex = Math.floor(Math.random() * messages.length);
document.getElementById('surprise-message').innerText = messages[randomIndex];

// Fun background flash
document.body.style.background = '#ffe0f0';
setTimeout(() => {
document.body.style.background = 'linear-gradient(120deg, #fce4ec, #f8bbd0)';
}, 500);
}

// Create floating hearts
function createHeart() {
const heart = document.createElement('div');
heart.className = 'heart';
heart.style.left = Math.random() * window.innerWidth + 'px';
heart.style.animationDuration = 3 + Math.random() * 5 + 's';
heart.style.width = 10 + Math.random() * 20 + 'px';
heart.style.height = heart.style.width;
document.body.appendChild(heart);

setTimeout(() => {
heart.remove();
}, 8000);
}

setInterval(createHeart, 500);
</script>
</body>
</html>
