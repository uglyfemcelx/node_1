
</body>
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

<pre id="terminal"></pre><span class="cursor"></span>
<div id="hiddenMessage"></div>
<img id="image" src="https://i.imgur.com/8Km9tLL.png">
<div id="log"></div>

<script>

const lines = [
"[ identity_node_01 :: access granted ]",
"",
"name: ???",
"alias: uglyfoid",
"",
"age: not consistent",
"height: fluctuating",
"weight: unknown",
"",
"status: alive?",
"status: alive.",
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
"> why are you here?"
]

let i = 0
const terminal = document.getElementById("terminal")

function typeLine(){
if(i < lines.length){
terminal.innerHTML += lines[i] + "\n"
i++
setTimeout(typeLine, 400)
}else{
finish()
}
}

function finish(){
document.getElementById("image").style.opacity = "1"

document.getElementById("log").innerHTML =
"[log] access_time: unknown<br>" +
"[log] observer_id: ???<br>" +
"[log] status: being watched"
}

// click message
document.body.addEventListener("click", function(){
let msg = document.getElementById("hiddenMessage")
msg.style.opacity = "1"
msg.innerText = "> this file has been opened before"
})

typeLine()

</script>

</body>
</html></html>
