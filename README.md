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
}

#log{
margin-top:30px;
font-size:13px;
opacity:0.7;
}

</style>



</head>
<body>

<audio id="bgm" loop>
  <source src="https://files.catbox.moe/3m9b3p.mp3" type="audio/mpeg">
</audio>

<pre id="terminal"></pre><span class="cursor"></span>

<div id="hiddenMessage"></div>

<img id="image" src="https://art.ngfiles.com/images/2091000/2091580_shantalexshantaesbae_love-lain.gif?f1632361557" 
onclick="changeImage()">

<div id="imageSecret"></div>

<div id="log"></div>

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
"> i don’t remember when it started",
"> i don’t remember if it started",
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
"̷>̷ ̷w̷h̷y̷"
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

// glitch effect
terminal.classList.add("glitch")
setTimeout(()=>terminal.classList.remove("glitch"),1500)

// image
document.getElementById("image").style.opacity = "1"

// logs
document.getElementById("log").innerHTML =
"[log] access_time: unknown<br>" +
"[log] observer_id: ???<br>" +
"[log] status: unknown"

// strong flicker
let term = document.getElementById("terminal")
setTimeout(()=>{
term.style.opacity="0.1"
setTimeout(()=>{
term.style.opacity="1"
setTimeout(()=>{
term.style.opacity="0.3"
setTimeout(()=>{
term.style.opacity="1"
},80)
},80)
},80)
},500)

// random glitch messages
setInterval(()=>{
let glitchText = document.createElement("div")
let messages = ["[signal lost]","i'm watching you","i'm closer than you think"]
glitchText.innerText = messages[Math.floor(Math.random()*messages.length)]
glitchText.style.position = "absolute"
glitchText.style.left = Math.random()*window.innerWidth + "px"
glitchText.style.top = Math.random()*window.innerHeight + "px"
glitchText.style.opacity = "0.7"
document.body.appendChild(glitchText)
setTimeout(()=>glitchText.remove(),800)
},5000)

// screen flash
setInterval(()=>{
let flash = document.createElement("div")
flash.style.position="fixed"
flash.style.top="0"
flash.style.left="0"
flash.style.width="100%"
flash.style.height="100%"
flash.style.background="#00ff88"
flash.style.opacity="0.05"
flash.style.pointerEvents="none"
document.body.appendChild(flash)
setTimeout(()=>flash.remove(),100)
},8000)

// final whisper
setTimeout(()=>{
terminal.innerHTML += "\n> ...do you remember opening this before?"
},4000)

// returning visitor
if(localStorage.getItem("visited")){
terminal.innerHTML += "\n> welcome back"
}else{
localStorage.setItem("visited",true)
}

// cursor tracking message
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

}


// CLICKABLE IMAGE FUNCTION
function changeImage(){

let img = document.getElementById("image")
let secret = document.getElementById("imageSecret")

img.src = "https://images.steamusercontent.com/ugc/433780719169727960/771F6682B048A2947827EC9EF8D1ECB3A71FDDE5/?imw=1024&&ima=fit&impolicy=Letterbox&imcolor=%23000000&letterbox=false"

secret.style.opacity = "1"
secret.innerText =
"> image corrupted\n" +
"> switching layer\n" +
"> why..."

// glitch flash
document.body.style.background = "#001a00"
setTimeout(()=>{
document.body.style.background = "black"
},120)

}


// hidden message
document.body.onclick = function(){
let msg = document.getElementById("hiddenMessage")
msg.style.opacity = "1"
msg.innerText =
"> this file has been opened before\n" +
"> you were already here\n" +
"> every visit has been recorded\n" +
"> even the ones you don’t remember\n" +
"> the w̴͎͖̆̀l̶̞̖̖̣̜̫̩̻̱̉̉̍͋̈́̊͗̕͝͝į̷̟͔̀̉̈͗̾͌́̕͝͝ř̸͓̲̗̳͚̩̘̳̤̟́̍͊͌̇͘̚͝ę̸̡̜̪̤̥̲̐̈́̂̽̑͆͜d̸̬̓̄͒̃ keeps everything\n" +
"> including you"
}

// identity glitch
setInterval(()=>{
let names = ["name: ???","name: uglyfoid","name: s̶̛͉̀̐̈̓͊́̈̊̿͜o̸̳͗͐̚̕kif̵̠̭̬͉̞́̓́͒͆̄̉̍͐̆i̵̡̛̻̮̮̬͇͓̥͈͒̄̏͂̄̀͝à̷̛̺̬͆͊̍̿͑̚̚̚?̷̗͍̮̩̎","name: i'm watching you :)", "name: ERROR", "name: █████"]
let random = names[Math.floor(Math.random()*names.length)]
terminal.innerHTML = terminal.innerHTML.replace(/name: .*/, random)
},3000)

typeLine()

// MUSIC SYSTEM
let music = document.getElementById("bgm")
let currentVolume = 0.05
let musicStarted = false

function startMusic(){

if(musicStarted) return
musicStarted = true

music.volume = currentVolume
music.play()

// slowly increase volume
setInterval(()=>{
if(currentVolume < 0.35){
currentVolume += 0.01
music.volume = currentVolume
}
},2000)

// random distortion
setInterval(()=>{
if(Math.random() < 0.4){

let speed = 0.7 + Math.random()*0.8
music.playbackRate = speed

music.volume = Math.random()*0.4

setTimeout(()=>{
music.playbackRate = 1
music.volume = currentVolume
},200)

}
},3000)

}

document.body.onclick = function(){
startMusic()

// your existing code...
  
}

  
</script>


</body>
</html>
