<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Syrian Soul - Tiger vs Lion</title>

<style>
*{
  box-sizing:border-box;
}

body{
  margin:0;
  min-height:100vh;
  background:#07070b;
  color:white;
  font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Arial,sans-serif;
}

.app{
  max-width:520px;
  min-height:100vh;
  margin:auto;
  padding:20px 16px 40px;
  background:
    radial-gradient(circle at 50% 0,#43134f 0,#120b18 35%,#07070b 72%);
}

/* HEADER */

.header{
  display:flex;
  align-items:center;
  gap:12px;
  margin-bottom:18px;
}

.logo{
  width:50px;
  height:50px;
  border-radius:17px;
  display:grid;
  place-items:center;
  font-size:25px;
  background:linear-gradient(135deg,#a855f7,#ec4899);
  box-shadow:0 8px 30px #a855f755;
}

.header h1{
  margin:0;
  font-size:21px;
}

.header small{
  color:#aaa;
}

/* BALANCE */

.balance{
  padding:13px;
  text-align:center;
  border-radius:17px;
  background:#ffffff09;
  border:1px solid #ffffff12;
  margin-bottom:15px;
}

.balance span{
  color:#ffd65c;
  font-weight:bold;
}

/* GAME */

.game{
  padding:18px;
  border-radius:26px;
  background:#ffffff08;
  border:1px solid #ffffff12;
}

.title{
  text-align:center;
}

.title h2{
  margin:5px 0;
  font-size:25px;
}

.title p{
  margin:5px 0;
  color:#aaa;
  font-size:13px;
}

/* PLAYERS */

.players{
  display:flex;
  justify-content:space-between;
  margin:20px 0;
}

.player{
  text-align:center;
  width:31%;
}

.player .animal{
  height:95px;
  border-radius:22px;
  display:grid;
  place-items:center;
  font-size:48px;
  background:#ffffff0b;
  border:1px solid #ffffff12;
}

.tiger .animal{
  box-shadow:0 0 25px #f9731640;
}

.lion .animal{
  box-shadow:0 0 25px #eab30840;
}

.draw .animal{
  box-shadow:0 0 25px #a855f740;
}

.player h3{
  margin:8px 0 0;
}

.player small{
  color:#aaa;
}

/* SPINNER */

.spinner-area{
  margin:25px 0;
  position:relative;
  overflow:hidden;
  border-radius:22px;
  border:2px solid #ffffff18;
  background:#050509;
  padding:14px 0;
}

.pointer{
  position:absolute;
  top:0;
  bottom:0;
  left:50%;
  width:4px;
  transform:translateX(-50%);
  background:#fff;
  box-shadow:0 0 18px #fff;
  z-index:5;
}

.pointer:before,
.pointer:after{
  content:"";
  position:absolute;
  left:50%;
  transform:translateX(-50%);
  border-left:9px solid transparent;
  border-right:9px solid transparent;
}

.pointer:before{
  top:0;
  border-top:13px solid #fff;
}

.pointer:after{
  bottom:0;
  border-bottom:13px solid #fff;
}

.track{
  display:flex;
  width:max-content;
  transform:translateX(0);
}

.item{
  width:120px;
  height:100px;
  margin:0 6px;
  border-radius:18px;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  background:#ffffff0b;
  border:1px solid #ffffff12;
}

.item .emoji{
  font-size:38px;
}

.item span{
  margin-top:4px;
  font-size:12px;
  color:#bbb;
}

/* BUTTON */

.start{
  width:100%;
  padding:15px;
  border:0;
  border-radius:16px;
  color:white;
  background:linear-gradient(90deg,#9333ea,#db2777);
  font-size:17px;
  font-weight:bold;
}

.start:disabled{
  opacity:.45;
}

/* RESULT */

.result{
  display:none;
  margin-top:18px;
  padding:22px;
  text-align:center;
  border-radius:22px;
  background:linear-gradient(135deg,#7e22ce,#be185d);
}

.result.show{
  display:block;
  animation:resultIn .5s ease;
}

.result .big{
  font-size:60px;
}

.result h2{
  margin:7px 0;
}

.result p{
  color:#f8eefe;
}

.again{
  padding:12px 20px;
  border:0;
  border-radius:14px;
  background:white;
  color:#741bb5;
  font-weight:bold;
}

/* INFO */

.info{
  margin-top:18px;
  padding:14px;
  border-radius:17px;
  background:#ffffff06;
  border:1px solid #ffffff0c;
  text-align:center;
  color:#888;
  font-size:11px;
}

@keyframes resultIn{
  from{
    opacity:0;
    transform:scale(.8);
  }
  to{
    opacity:1;
    transform:scale(1);
  }
}
</style>
</head>

<body>

<div class="app">

<div class="header">
  <div class="logo">✦</div>

  <div>
    <h1>Syrian Soul</h1>
    <small>Tiger vs Lion</small>
  </div>
</div>

<div class="balance">
  🪙 العملات الافتراضية:
  <span id="coins">1,000</span>
</div>

<div class="game">

<div class="title">
  <h2>🐯 النمر × الأسد 🦁</h2>
  <p>اختيار عشوائي ترفيهي مع نتيجة تعادل ⚖️</p>
</div>

<!-- الخيارات -->

<div class="players">

<div class="player tiger">
  <div class="animal">🐯</div>
  <h3>النمر</h3>
  <small>TIGER</small>
</div>

<div class="player draw">
  <div class="animal">⚖️</div>
  <h3>تعادل</h3>
  <small>DRAW</small>
</div>

<div class="player lion">
  <div class="animal">🦁</div>
  <h3>الأسد</h3>
  <small>LION</small>
</div>

</div>

<!-- الفتل -->

<div class="spinner-area">

<div class="pointer"></div>

<div class="track" id="track">

<div class="item"><div class="emoji">🐯</div><span>النمر</span></div>
<div class="item"><div class="emoji">⚖️</div><span>تعادل</span></div>
<div class="item"><div class="emoji">🦁</div><span>الأسد</span></div>

<div class="item"><div class="emoji">🐯</div><span>النمر</span></div>
<div class="item"><div class="emoji">⚖️</div><span>تعادل</span></div>
<div class="item"><div class="emoji">🦁</div><span>الأسد</span></div>

<div class="item"><div class="emoji">🐯</div><span>النمر</span></div>
<div class="item"><div class="emoji">⚖️</div><span>تعادل</span></div>
<div class="item"><div class="emoji">🦁</div><span>الأسد</span></div>

<div class="item"><div class="emoji">🐯</div><span>النمر</span></div>
<div class="item"><div class="emoji">⚖️</div><span>تعادل</span></div>
<div class="item"><div class="emoji">🦁</div><span>الأسد</span></div>

<div class="item"><div class="emoji">🐯</div><span>النمر</span></div>
<div class="item"><div class="emoji">⚖️</div><span>تعادل</span></div>
<div class="item"><div class="emoji">🦁</div><span>الأسد</span></div>

<div class="item"><div class="emoji">🐯</div><span>النمر</span></div>
<div class="item"><div class="emoji">⚖️</div><span>تعادل</span></div>
<div class="item"><div class="emoji">🦁</div><span>الأسد</span></div>

</div>

</div>

<button class="start" id="startButton" onclick="startRound()">
ابدأ الجولة 🔥
</button>

<div class="result" id="result">

<div class="big" id="resultEmoji">🏆</div>

<h2 id="resultTitle">النتيجة</h2>

<p id="resultText"></p>

<button class="again" onclick="newRound()">
جولة جديدة 🔄
</button>

</div>

</div>

<div class="info">
اللعبة الحالية نسخة تجريبية بعملات افتراضية فقط.
</div>

</div>

<script>

const outcomes = [
  {
    name:"النمر",
    emoji:"🐯"
  },
  {
    name:"تعادل",
    emoji:"⚖️"
  },
  {
    name:"الأسد",
    emoji:"🦁"
  }
];

let coins = 1000;
let spinning = false;

function startRound(){

  if(spinning) return;

  spinning = true;

  const button =
    document.getElementById("startButton");

  button.disabled = true;

  document.getElementById("result")
    .classList.remove("show");

  /*
    اختيار عشوائي محلي.
    في V2 الحقيقي سيتم استبداله
    بنتيجة قادمة من الـBackend.
  */

  const winner =
    Math.floor(Math.random() * outcomes.length);

  const track =
    document.getElementById("track");

  /*
    إعادة الحركة إلى البداية
  */

  track.style.transition = "none";
  track.style.transform = "translateX(0)";

  void track.offsetWidth;

  /*
    كل عنصر عرضه 132px تقريباً.
    نختار نتيجة عشوائية ضمن السلسلة.
  */

  const position =
    12 + winner;

  const move =
    -(position * 132);

  track.style.transition =
    "transform 4.5s cubic-bezier(.12,.75,.18,1)";

  track.style.transform =
    "translateX(" + move + "px)";

  setTimeout(function(){

    showResult(winner);

    spinning = false;
    button.disabled = false;

  },4700);
}

function showResult(index){

  const result =
    outcomes[index];

  document.getElementById("resultEmoji")
    .textContent = result.emoji;

  document.getElementById("resultTitle")
    .textContent = result.name;

  if(index === 1){

    document.getElementById("resultText")
      .textContent =
      "⚖️ انتهت الجولة بالتعادل!";

  }else{

    document.getElementById("resultText")
      .textContent =
      "🏆 الفائز في الجولة هو " +
      result.emoji + " " +
      result.name;

  }

  document.getElementById("result")
    .classList.add("show");
}

function newRound(){

  document.getElementById("result")
    .classList.remove("show");

  const track =
    document.getElementById("track");

  track.style.transition = "none";
  track.style.transform = "translateX(0)";

}

</script>

</body>
</html>
