<!DOCTYPE html>
<html>
<head>
<title>node_01</title>

<style>
body{
background:black;
color:#00ff88;
font-family:"Courier New", monospace;
padding:40px;
overflow-x:hidden;
}

#terminal{
white-space:pre-wrap;
line-height:1.6;
}

.cursor{
display:inline-block;
width:10px;
background:#00ff88;
margin-left:5px;
animation:blink 1s infinite;
}

@keyframes blink{
0%{opacity:1;}
50%{opacity:0;}
100%{opacity:1;}
}

.glitch{
animation:glitch 0.2s infinite;
}

@keyframes glitch{
0%{opacity:1;}
50%{opacity:0.5;}
100%{opacity:1;}
}

#hiddenMessage{
opacity:0;
margin-top:20px;
transition:opacity 1s;
}

#image{
opacity:0;
display:block;
margin:30px auto;
max-width:300px;
transition:opacity 3s;
cursor:pointer;
}

#imageSecret{
opacity:0;
margin-top:20px;
white-space:pre-wrap;
transition:opacity 1s;
}

#log{
margin-top:30px;
font-size:13px;
opacity:0.7;
}

#signalLink{
margin-top:30px;
text-align:center;
opacity:0;
transition:opacity 2s;
}

#signalLink a{
color:#00ff88;
text-decoration:none;
}

#signalLink a:hover{
opacity:0.5;
}
</style>
</head>

<body>

<pre id="terminal"></pre><span class="cursor"></span>

<div id="hiddenMessage"></div>

<img id="image" src="https://art.ngfiles.com/images/2091000/2091580_shantalexshantaesbae_love-lain.gif?f1632361557" onclick="changeImage()">

<div id="imageSecret"></div>

<div id="log"></div>

<div id="signalLink">
<a href="https://tellonym.me/uglyfemcelx" target="_blank">
> speak. i will receive it
</a>
</div>

<script>

const baseLines = [
"[ identity_node_01 :: access granted ]",
"",
"name: ???",
"alias: uglyfoid",
"",
"age: not consistent",
"height: fluctuating",
"weight: unknown",
"",
"status: alive.",
"status: alive?",
"status: █████",
"",
"location: the wired",
"origin: not found",
"origin: overwritten",
"",
"—",
"",
"> i exist between signals",
"> i dont remember when it started",
"> i dont remember if it started",
"",
"> or if this is really me",
"",
"—",
"",
"memory_01: incomplete",
"memory_02: corrupted",
"memory_03: replaced",
"memory_04: [access denied]",
"",
"—",
"",
"> they say this is my identity",
"",
"> but it feels like something i was given",
"",
"> not something i chose",
"> not something i can escape",
"",
"—",
"",
"connection: active",
"connection: unstable",
"",
"observer: detected",
"observer: watching",
"observer: closer",
"",
"—",
"",
"> why are you reading this?",
"> why are you here",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"> why",
"̷> why"
]

let i = 0
const terminal = document.getElementById("terminal")

function typeLine(){
if(i < baseLines.length){
terminal.innerHTML += baseLines[i] + "\n"
i++
setTimeout(typeLine, 500)
}else{
afterTyping()
}
}

function afterTyping(){

terminal.classList.add("glitch")
setTimeout(()=>terminal.classList.remove("glitch"),1500)

document.getElementById("image").style.opacity = "1"

document.getElementById("log").innerHTML =
"[log] access_time: unknown<br>" +
"[log] observer_id: ???<br>" +
"[log] status: unknown"

setTimeout(()=>{
terminal.innerHTML += "\n> ...do you remember opening this before?"
},4000)

if(localStorage.getItem("visited")){
terminal.innerHTML += "\n> ̷>̷ ̷w̷h̷y̷"
}else{
localStorage.setItem("visited",true)
}

setTimeout(()=>{
document.getElementById("signalLink").style.opacity = "1"
},4000)

}

// CURSOR FOLLOW
document.addEventListener("mousemove", function(e){
if(Math.random() < 0.01){
let follow = document.createElement("div")
follow.innerText = "i see you"
follow.style.position="absolute"
follow.style.left = e.pageX + "px"
follow.style.top = e.pageY + "px"
follow.style.opacity="0.5"
document.body.appendChild(follow)
setTimeout(()=>follow.remove(),500)
}
})

// IMAGE CLICK
function changeImage(){
let img = document.getElementById("image")
let secret = document.getElementById("imageSecret")

img.src ="https://images.steamusercontent.com/ugc/433780719169727960/771F6682B048A2947827EC9EF8D1ECB3A71FDDE5/?imw=1024&&ima=fit&impolicy=Letterbox&imcolor=%23000000&letterbox=false"

secret.style.opacity = "1"
secret.innerText = "> why did you click it?"

document.body.style.background = "#001a00"
setTimeout(()=>{document.body.style.background="black"},120)
}

// after 3 clicks > redirect
    if(imageClicks >= 3){
        setTimeout(()=>{
            window.location.href = "https://x.com/monlogis";
        }, 1000);
    }
  }

// CLICK
document.body.onclick = function(){

startMusic()

let msg = document.getElementById("hiddenMessage")
msg.style.opacity = "1"
msg.innerText =
"> this node has been opened before"
  
}

// NAME GLITCH
setInterval(()=>{
let names = ["name: ???","name: uglyfoid","name: ş̷̧̠̼̩͍͚̰̭̬͗̊͊̿͋̌̌̒͝o̴̢̞͍͎̣̻̞͓̓̈͒̏̕k̸̨͖̠̮̳̭̞̅̈́̋̑̂͆̈̚̕͜f̸̣̠͂́i̸̼̱̰͓̻͙̰̻̜̇̐̽͋̈́̈́̚̚ạ̵͈͍͐̔?", "name: forgottenfoid", "name: digitaldecay","name: uglyfemcelx", "name: tanpa_nama.exe", "name: i'm watching you :)","name: █████"]
let random = names[Math.floor(Math.random()*names.length)]
terminal.innerHTML = terminal.innerHTML.replace(/name: .*/, random)
},3000)

typeLine()

</script>

</body>
</html>
