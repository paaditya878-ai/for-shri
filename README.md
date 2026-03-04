# for-shri
<!DOCTYPE html>
<html>
<head>
<title>For Shri 🤍</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300&family=Playfair+Display:wght@500&display=swap');

body{
margin:0;
padding:0;
font-family:'Poppins',sans-serif;
background: linear-gradient(135deg,#1f1c2c,#928dab);
color:white;
text-align:center;
overflow:hidden;
}

/* Glass box */
.box{
position:absolute;
top:50%;
left:50%;
transform:translate(-50%,-50%);
background:rgba(255,255,255,0.1);
backdrop-filter:blur(15px);
padding:40px;
border-radius:25px;
box-shadow:0 0 40px rgba(0,0,0,0.4);
width:340px;
animation:fade 1.5s ease-in-out;
}

@keyframes fade{
from{opacity:0; transform:translateY(20px);}
to{opacity:1; transform:translateY(0);}
}

input{
padding:10px;
border:none;
border-radius:20px;
text-align:center;
outline:none;
width:80%;
}

button{
margin-top:15px;
padding:10px 20px;
border:none;
border-radius:20px;
background:#ff6ec4;
color:white;
cursor:pointer;
transition:0.3s;
}

button:hover{
background:#ff2d95;
transform:scale(1.1);
}

.page{display:none;}

.photo img{
width:250px;
border-radius:20px;
margin-top:15px;
box-shadow:0 0 30px rgba(255,255,255,0.6);
transition:0.4s;
}

.photo img:hover{
transform:scale(1.05);
}

.heart{
position:absolute;
color:#ff6ec4;
animation:float 5s linear infinite;
}

@keyframes float{
0%{transform:translateY(100vh);opacity:1;}
100%{transform:translateY(-10vh);opacity:0;}
}
</style>
</head>

<body>

<!-- LOGIN -->
<div class="box" id="login">
<h2>Only for Shri 🤍</h2>
<input type="password" id="pass" placeholder="Enter Secret Code">
<br>
<button onclick="unlock()">Unlock</button>
<p id="msg"></p>
</div>

<!-- QUESTION PAGE -->
<div class="box page" id="question">
<h2>Shri 💖</h2>
<p>Kya Aaditya tumko pasand hai? 😌</p>
<button onclick="nextPage()">Haan 💕</button>
<button onclick="nextPage()">Bilkul Haan 💖</button>
</div>

<!-- FINAL PAGE -->
<div class="box page" id="final">
<h2>Shri 👑</h2>

<div class="photo">
<img src="IMG_1564.JPG">
<img src="IMG_1478.jpg">
</div>

<p style="margin-top:15px;">
Tu meri duniya hai.  
Tu meri Malkin hai.  
Aur Aaditya sirf tera hai 💗
</p>
</div>

<script>
function unlock(){
if(document.getElementById("pass").value==="0621"){
document.getElementById("login").style.display="none";
document.getElementById("question").style.display="block";
}else{
document.getElementById("msg").innerHTML="Wrong code 😌";
}
}

function nextPage(){
document.getElementById("question").style.display="none";
document.getElementById("final").style.display="block";
}

function hearts(){
var h=document.createElement("div");
h.className="heart";
h.innerHTML="❤";
h.style.left=Math.random()*100+"vw";
h.style.fontSize=(Math.random()*20+10)+"px";
document.body.appendChild(h);
setTimeout(()=>{h.remove();},5000);
}
setInterval(hearts,400);
</script>

</body>
</html>
