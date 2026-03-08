# 8-Martieee
<html lang="ro">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>La mulți ani de 8 Martie 🌸</title>

<style>

body{
margin:0;
font-family: 'Segoe UI', sans-serif;
background: linear-gradient(180deg,#ffd6e7,#fff);
overflow:hidden;
display:flex;
align-items:center;
justify-content:center;
height:100vh;
text-align:center;
}

/* CARD */

.card{
background:white;
padding:30px 25px;
border-radius:25px;
box-shadow:0 25px 60px rgba(255,100,150,0.25);
max-width:520px;
width:90%;
z-index:5;
}

h1{
color:#d6336c;
font-size:26px;
margin-bottom:10px;
}

.message{
font-size:18px;
line-height:1.6;
color:#5a1a36;
min-height:180px;
}

/* INIMA */

.heart{
width:30px;
height:30px;
background:#ff2f74;
transform:rotate(-45deg);
margin:20px auto;
animation:beat 1.2s infinite;
position:relative;
}

.heart:before,
.heart:after{
content:"";
width:30px;
height:30px;
background:#ff2f74;
border-radius:50%;
position:absolute;
}

.heart:before{top:-15px;}
.heart:after{left:15px;}

@keyframes beat{
0%,100%{transform:rotate(-45deg) scale(1);}
50%{transform:rotate(-45deg) scale(1.2);}
}

/* BUTOANE */

button{
margin-top:15px;
padding:12px 20px;
border:none;
border-radius:25px;
background:#ff2f74;
color:white;
font-size:16px;
cursor:pointer;
}

/* POPUP DECLARATIE */

.overlay{
position:fixed;
inset:0;
background:rgba(0,0,0,0.5);
display:none;
align-items:center;
justify-content:center;
z-index:20;
}

.popup{
background:white;
padding:30px;
border-radius:20px;
max-width:350px;
line-height:1.6;
}

/* PETALE CARE CAD */

.flower{
position:absolute;
top:-10%;
font-size:22px;
animation:fall linear forwards;
}

@keyframes fall{
to{
transform:translateY(110vh) rotate(360deg);
}
}

.signature{
position:fixed;
bottom:10px;
right:15px;
font-size:14px;
color:#7a274b;
}

.music{
position:fixed;
left:15px;
bottom:10px;
}

</style>
</head>

<body>

<div class="card">

<h1>La mulți ani de 8 Martie 🌸</h1>

<div class="heart"></div>

<p class="message" id="text"></p>

<button onclick="openLove()">Un mic mesaj pentru tine ❤️</button>

</div>

<div class="overlay" id="overlay">
<div class="popup">

<h2>Pentru tine 💐</h2>

<p>
La mulți ani de 8 Martie, iubirea mea.

Îți doresc o primăvară plină de lumină, zâmbete și momente frumoase,
exact așa cum ești tu pentru mine.

Vreau să știi că mă simt cel mai norocos om din lume
pentru că faci parte din viața mea.

Prezența ta îmi face zilele mai frumoase,
iar zâmbetul tău îmi aduce liniște și fericire.

Îți mulțumesc că exiști,
că îmi ești alături
și că faci lumea mea mai bună doar prin simplul fapt că ești tu.

Sper ca fiecare zi din viața ta să fie plină de iubire,
iar eu voi fi mereu aici să te fac să te simți apreciată,
iubită și specială.

La mulți ani, floarea mea. ❤️
</p>

<button onclick="closeLove()">Te iubesc</button>

</div>
</div>

<div class="signature">
Cu drag, nebunu' tău ❤️
</div>

<div class="music">
<button onclick="toggleMusic()">🎵 Muzică</button>
</div>

<!-- player youtube -->
<div id="player"></div>
<script src="https://www.youtube.com/iframe_api"></script>

<script>

/* TEXT CINEMATIC */

const mesaj = `Iubirea mea,

Astăzi este o zi specială,
dar pentru mine fiecare zi în care te am în viața mea
este deja un motiv de sărbătoare.

Îți doresc o primăvară plină de lumină,
zâmbete și momente frumoase.

Sunt recunoscător în fiecare zi
că destinul te-a adus în viața mea.

Prezența ta îmi face lumea mai frumoasă
și inima mai liniștită.

La mulți ani de 8 Martie,
floarea mea. 🌸`;

let i=0;

function type(){
if(i < mesaj.length){
document.getElementById("text").innerHTML += mesaj.charAt(i);
i++;
setTimeout(type,35);
}
}

type();

/* PETALE CONTINUE */

function flowerRain(){

const flower=document.createElement("div");

flower.classList.add("flower");

const symbols=["🌸","🌷","🌹","💮"];

flower.innerHTML=symbols[Math.floor(Math.random()*symbols.length)];

flower.style.left=Math.random()*100+"vw";

flower.style.animationDuration=(Math.random()*5+5)+"s";

document.body.appendChild(flower);

setTimeout(()=>{
flower.remove();
},9000);

}

setInterval(flowerRain,500);

/* FLORI LA ATINGERE */

function spawnFlower(x,y){

const f=document.createElement("div");

f.style.position="fixed";
f.style.left=x+"px";
f.style.top=y+"px";
f.style.fontSize="24px";
f.innerHTML="🌸";

document.body.appendChild(f);

setTimeout(()=>{f.remove();},1000);

}

document.addEventListener("touchstart",e=>{
spawnFlower(e.touches[0].clientX,e.touches[0].clientY);
});

document.addEventListener("click",e=>{
spawnFlower(e.clientX,e.clientY);
});

/* POPUP */

function openLove(){
document.getElementById("overlay").style.display="flex";
}

function closeLove(){
document.getElementById("overlay").style.display="none";
}

/* YOUTUBE MUSIC */

let player;
let playing=false;

function onYouTubeIframeAPIReady(){
player=new YT.Player('player',{
height:'0',
width:'0',
videoId:'SM-N4pmi73A'
});
}

function toggleMusic(){

if(!playing){
player.playVideo();
playing=true;
}
else{
player.pauseVideo();
playing=false;
}

}

</script>

</body>
</html>
