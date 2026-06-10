<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Please Forgive Me ❤️</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    font-family:'Poppins',sans-serif;
    background:linear-gradient(135deg,#ffd6e7,#ffeef5);
    min-height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    overflow:hidden;
}

.container{
    text-align:center;
    padding:30px;
    max-width:700px;
}

img{
    width:220px;
    margin-bottom:20px;
    border-radius:20px;
}

h1{
    color:#ff3d7f;
    margin-bottom:15px;
}

p{
    font-size:1.1rem;
    color:#555;
}

.buttons{
    margin-top:30px;
    position:relative;
}

button{
    border:none;
    padding:15px 35px;
    border-radius:15px;
    font-size:1.1rem;
    cursor:pointer;
    transition:.25s;
}

#yesBtn{
    background:#4CAF50;
    color:white;
}

#noBtn{
    background:#ff4d6d;
    color:white;
    margin-left:15px;
}

.floating-heart{
    position:fixed;
    animation:floatUp 4s linear forwards;
}

@keyframes floatUp{
    from{
        transform:translateY(0);
        opacity:1;
    }
    to{
        transform:translateY(-120vh);
        opacity:0;
    }
}
</style>
</head>
<body>

<div class="container">

    <!-- Replace with your own photo/GIF -->
    <img src="https://media.tenor.com/0AVbKGY_MxMAAAAC/cute-bear.gif">

    <h1 id="title">I'm Really Sorry ❤️</h1>

    <p id="message">
        I know I messed up and I genuinely feel bad about it.
        You mean a lot to me.
    </p>

    <div class="buttons">
        <button id="yesBtn">I Forgive You ❤️</button>
        <button id="noBtn">No 😤</button>
    </div>

</div>

<script>

const noBtn = document.getElementById("noBtn");
const yesBtn = document.getElementById("yesBtn");
const message = document.getElementById("message");

const texts = [
"Are you sure? 🥺",
"Really sure? 😭",
"Please think again ❤️",
"I'll buy you snacks 🍫",
"I'll send you memes 🥹",
"You're my favorite person 😭",
"Don't do this to me 😔",
"Last chance 😭❤️",
"Pretty please? 🥺",
"Okay now you're just being mean 😭"
];

let count = 0;
let scale = 1;

function moveNoButton(){

    message.textContent = texts[Math.min(count,texts.length-1)];

    const x = Math.random() * (window.innerWidth - 150);
    const y = Math.random() * (window.innerHeight - 100);

    noBtn.style.position = "fixed";
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";

    scale += 0.18;
    yesBtn.style.transform = `scale(${scale})`;

    count++;
}

noBtn.addEventListener("mouseover", moveNoButton);
noBtn.addEventListener("click", moveNoButton);

yesBtn.addEventListener("click", ()=>{

document.body.innerHTML = `
<div style="
height:100vh;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
text-align:center;
padding:30px;
background:linear-gradient(135deg,#ffd6e7,#fff0f7);
font-family:Poppins;
">
<h1 style="font-size:4rem;color:#ff3d7f;">
YAYYYYY ❤️
</h1>

<h2 style="margin-top:10px;">
Thank you for forgiving me 🥺
</h2>

<p style="
max-width:600px;
margin-top:20px;
font-size:1.1rem;
line-height:1.8;
">
I know I won't always be perfect,
but I promise I'll always care about you,
listen to you, and keep trying to be better.
❤️
</p>

<h3 style="margin-top:25px;">
Love You 💕
</h3>
</div>
`;

setInterval(()=>{
const heart=document.createElement("div");
heart.className="floating-heart";
heart.innerHTML="❤️";

heart.style.left=Math.random()*window.innerWidth+"px";
heart.style.bottom="-50px";
heart.style.fontSize=(20+Math.random()*40)+"px";

document.body.appendChild(heart);

setTimeout(()=>{
heart.remove();
},4000);

},120);

});

</script>

</body>
</html>
</body>
</html>
