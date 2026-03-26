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
font-size:15px;
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

/* glitch effect */
.glitch{
animation:glitch 0.2s infinite;
}

@keyframes glitch{
0%{opacity:1;}
50%{opacity:0.6;}
100%{opacity:1;}
}
</style>

</head>
<body>

<pre id="terminal"></pre><span class="cursor"></span>

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
"> if you are reading this",
"",
"> then you are already inside",
"",
"> there is no \"outside\" anymore"
]

let i = 0
const terminal = document.getElementById("terminal")

function typeLine(){
if(i < lines.length){
terminal.innerHTML += lines[i] + "\n"
i++
setTimeout(typeLine, 500)
}else{
glitchEffect()
}
}

function glitchEffect(){
terminal.classList.add("glitch")
setTimeout(()=>{
terminal.classList.remove("glitch")
},2000)
}

typeLine()

</script>

</body>
</html>
