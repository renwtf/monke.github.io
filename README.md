<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Please Forgive Me ❤️</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, sans-serif;
}

body{
    background:linear-gradient(135deg,#ffd6e7,#fff0f5);
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    overflow:hidden;
}

.container{
    text-align:center;
    padding:20px;
    max-width:600px;
}

.gif{
    width:250px;
    border-radius:20px;
    margin-bottom:20px;
}

h1{
    color:#ff4d8d;
    margin-bottom:15px;
}

.message{
    font-size:20px;
    color:#555;
    margin-bottom:30px;
}

.buttons{
    display:flex;
    justify-content:center;
    gap:15px;
}

button{
    border:none;
    padding:15px 30px;
    border-radius:15px;
    cursor:pointer;
    font-size:18px;
    transition:0.25s;
}

#yesBtn{
    background:#4CAF50;
    color:white;
}

#noBtn{
    background:#ff4d6d;
    color:white;
}

.heart{
    position:fixed;
    bottom:-50px;
    animation:floatUp 5s linear forwards;
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

    <img
    class="gif"
    src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExYnRpNGFuNjl3bHg1eTY3enlrajFuYXhoMzZ2Y3JoNmlkYmczN2c4eCZlcD12MV9naWZzX3NlYXJjaCZjdD1n/oi1iF8VmRGo9nHTPl8/giphy.gif"
    alt="cute bear">

    <h1>I'm Sorry ❤️</h1>

    <p class="message">
        I know I havent been the best and I'm genuinely sorry.
        Will you forgive me?
    </p>

    <div class="buttons">
        <button id="yesBtn">Yes ❤️</button>
        <button id="noBtn">No 💔</button>
    </div>

</div>

<script>

const noBtn = document.getElementById("noBtn");
const yesBtn = document.getElementById("yesBtn");

const noMessages = [
"Pakka",
"Really sure?",
"Think abt ittt",
"PLEAASSEEEEE", 
"PRETTYYY PLEAASSEE",
"I'll buy you icecreamm bebe",
"I'll send over some cookieess?",
"You're my favourite personn :(",
"MWUAAHAHH ILL GIV KISSIES",
"NNOOOOOOOOOH",
"MONKEYYYYYYY PLEAASEEUHH"
];

let clickCount = 0;
let yesScale = 1;

function moveNoButton(){

    noBtn.innerText =
        noMessages[Math.min(clickCount, noMessages.length - 1)];

    const maxX = window.innerWidth - noBtn.offsetWidth;
    const maxY = window.innerHeight - noBtn.offsetHeight;

    const randomX = Math.random() * maxX;
    const randomY = Math.random() * maxY;

    noBtn.style.position = "fixed";
    noBtn.style.left = randomX + "px";
    noBtn.style.top = randomY + "px";

    yesScale += 0.15;
    yesBtn.style.transform = `scale(${yesScale})`;

    clickCount++;
}

noBtn.addEventListener("mouseenter", moveNoButton);
noBtn.addEventListener("click", moveNoButton);

yesBtn.addEventListener("click", () => {

document.body.innerHTML = `
<div style="
height:100vh;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
text-align:center;
padding:30px;
background:linear-gradient(135deg,#ffd6e7,#fff0f5);
">

<img
style="width:280px;border-radius:20px;"
src="https://media.tenor.com/5Vq4K8A6vTMAAAAC/bear-love.gif">

<h1 style="
font-size:60px;
color:#ff4d8d;
margin-top:20px;">
WOOOOOOHH :P
</h1>

<h2 style="margin-top:10px;">
I will try to be better bebe.
</h2>

<p style="
max-width:600px;
margin-top:20px;
font-size:20px;
line-height:1.8;">
I know I mess up a lot,
but I really do care about you more than i can describe.
I hope you can forgive me and i'll do my best to make it up to you jaan.
</p>

</div>
`;

setInterval(() => {

    const heart = document.createElement("div");

    heart.innerHTML = "❤️";

    heart.style.position = "fixed";
    heart.style.left = Math.random() * window.innerWidth + "px";
    heart.style.bottom = "-50px";
    heart.style.fontSize = (20 + Math.random() * 40) + "px";
    heart.style.pointerEvents = "none";
    heart.style.zIndex = "9999";

    document.body.appendChild(heart);

    let pos = -50;
    let opacity = 1;

    const float = setInterval(() => {
        pos += 3;
        opacity -= 0.005;

        heart.style.bottom = pos + "px";
        heart.style.opacity = opacity;

        if (pos > window.innerHeight + 100) {
            clearInterval(float);
            heart.remove();
        }
    }, 16);

}, 120);
    
});

</script>

</body>
</html>
