<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Syrian Soul - 8 Teams</title>

<style>
*{
  box-sizing:border-box;
}

body{
  margin:0;
  background:#07070c;
  color:white;
  font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Arial,sans-serif;
}

.app{
  max-width:520px;
  min-height:100vh;
  margin:auto;
  padding:20px 16px 45px;
  background:
    radial-gradient(circle at top,#40135b 0,#100b18 35%,#07070c 70%);
}

.header{
  display:flex;
  align-items:center;
  gap:12px;
  margin-bottom:20px;
}

.logo{
  width:50px;
  height:50px;
  border-radius:17px;
  display:grid;
  place-items:center;
  font-size:25px;
  background:linear-gradient(135deg,#a855f7,#ec4899);
}

.header h1{
  margin:0;
  font-size:22px;
}

.header small{
  color:#aaa;
}

.balance{
  margin:15px 0;
  padding:15px;
  border-radius:18px;
  background:#ffffff0d;
  border:1px solid #ffffff12;
  text-align:center;
}

.balance strong{
  color:#ffd75a;
  font-size:20px;
}

.game{
  padding:20px 15px;
  border-radius:25px;
  background:#ffffff08;
  border:1px solid #ffffff12;
}

.game-title{
  text-align:center;
}

.game-title h2{
  margin:5px 0;
  font-size:25px;
}

.game-title p{
  color:#aaa;
  font-size:13px;
}

.teams{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10px;
  margin-top:18px;
}

.team{
  padding:14px 8px;
  border-radius:18px;
  background:#ffffff09;
  border:1px solid #ffffff12;
  color:white;
  transition:.2s;
}

.team.selected{
  border:2px solid #d946ef;
  background:#a855f722;
  transform:scale(1.03);
}

.flag{
  font-size:30px;
}

.team-name{
  display:block;
  margin-top:7px;
  font-weight:bold;
}

.selected-text{
  margin-top:16px;
  min-height:24px;
  text-align:center;
  color:#d879ff;
  font-weight:bold;
}

.wheel-area{
  display:flex;
  justify-content:center;
  margin:25px 0;
}

.wheel{
  width:210px;
  height:210px;
  border-radius:50%;
  position:relative;
  border:7px solid #fff;
  background:conic-gradient(
    #9333ea 0deg 45deg,
    #ec4899 45deg 90deg,
    #2563eb 90deg 135deg,
    #16a34a 135deg 180deg,
    #f59e0b 180deg 225deg,
    #dc2626 225deg 270deg,
    #0891b2 270deg 315deg,
    #7c3aed 315deg 360deg
  );
  box-shadow:0 0 40px #a855f766;
  transition:transform 4s cubic-bezier(.15,.8,.2,1);
}

.wheel-center{
  position:absolute;
  width:62px;
  height:62px;
  left:50%;
  top:50%;
  transform:translate(-50%,-50%);
  border-radius:50%;
  background:#0c0b12;
  display:grid;
  place-items:center;
  font-size:25px;
  border:3px solid white;
}

.pointer{
  width:0;
  height:0;
  border-left:13px solid transparent;
  border-right:13px solid transparent;
  border-top:25px solid white;
  position:absolute;
  top:-16px;
  left:50%;
  transform:translateX(-50%);
  z-index:2;
  filter:drop-shadow(0 2px 5px #000);
}

.start{
  width:100%;
  padding:15px;
  border:0;
  border-radius:16px;
  background:linear-gradient(90deg,#9333ea,#db2777);
  color:white;
  font-size:17px;
  font-weight:bold;
}

.start:disabled{
  opacity:.5;
}

.result{
  display:none;
  margin-top:18px;
  padding:20px;
  border-radius:20px;
  text-align:center;
  background:linear-gradient(135deg,#7e22ce,#be185d);
}

.result.show{
  display:block;
  animation:pop .4s ease;
}

.result .winner{
  font-size:38px;
}

.result h2{
  margin:8px 0;
}

.new-round{
  margin-top:12px;
  padding:12px 20px;
  border:0;
  border-radius:14px;
  background:white;
  color:#741bb5;
  font-weight:bold;
}

.note{
  text-align:center;
  color:#777;
  font-size:11px;
  margin-top:20px;
}

@keyframes pop{
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
    <small>روحك… مكانها هون</small>
  </div>
</div>

<div class="balance">
  🪙 رصيدك الافتراضي:
  <strong id="coins">1,000</strong>
</div>

<div class="game">

<div class="game-title">
  <h2>⚽ تحدي الـ 8 فرق</h2>
  <p>اختار فريقك وشوف مين رح يفوز بالجولة 🎯</p>
</div>

<div class="teams" id="teams">

<button class="team" onclick="selectTeam(0)">
  <span class="flag">🇸🇾</span>
  <span class="team-name">Syria</span>
</button>

<button class="team" onclick="selectTeam(1)">
  <span class="flag">🇧🇷</span>
  <span class="team-name">Brazil</span>
</button>

<button class="team" onclick="selectTeam(2)">
  <span class="flag">🇦🇷</span>
  <span class="team-name">Argentina</span>
</button>

<button class="team" onclick="selectTeam(3)">
  <span class="flag">🇫🇷</span>
  <span class="team-name">France</span>
</button>

<button class="team" onclick="selectTeam(4)">
  <span class="flag">🇩🇪</span>
  <span class="team-name">Germany</span>
</button>

<button class="team" onclick="selectTeam(5)">
  <span class="flag">🇪🇸</span>
  <span class="team-name">Spain</span>
</button>

<button class="team" onclick="selectTeam(6)">
  <span class="flag">🇵🇹</span>
  <span class="team-name">Portugal</span>
</button>

<button class="team" onclick="selectTeam(7)">
  <span class="flag">🇮🇹</span>
  <span class="team-name">Italy</span>
</button>

</div>

<div class="selected-text" id="selectedText">
اختار فريق أولاً 👆
</div>

<div class="wheel-area">

<div class="wheel" id="wheel">
  <div class="pointer"></div>
  <div class="wheel-center">⚽</div>
</div>

</div>

<button class="start" id="startButton" onclick="startGame()" disabled>
ابدأ الجولة 🎯
</button>

<div class="result" id="result">

<div class="winner" id="winnerFlag">🏆</div>

<h2 id="winnerName">الفائز</h2>

<p id="resultText"></p>

<button class="new-round" onclick="newRound()">
جولة جديدة 🔄
</button>

</div>

</div>

<div class="note">
لعبة ترفيهية عشوائية بعملات افتراضية فقط — بدون أموال حقيقية.
</div>

</div>

<script>

const teams = [
  {name:"Syria", flag:"🇸🇾"},
  {name:"Brazil", flag:"🇧🇷"},
  {name:"Argentina", flag:"🇦🇷"},
  {name:"France", flag:"🇫🇷"},
  {name:"Germany", flag:"🇩🇪"},
  {name:"Spain", flag:"🇪🇸"},
  {name:"Portugal", flag:"🇵🇹"},
  {name:"Italy", flag:"🇮🇹"}
];

let selected = null;
let coins = 1000;
let rotation = 0;

function selectTeam(index){

  selected = index;

  document.querySelectorAll(".team").forEach((button,i)=>{
    button.classList.toggle("selected",i === index);
  });

  document.getElementById("selectedText").textContent =
    "اختيارك: " + teams[index].flag + " " + teams[index].name;

  document.getElementById("startButton").disabled = false;

  document.getElementById("result").classList.remove("show");
}

function startGame(){

  if(selected === null){
    alert("اختار فريق أولاً");
    return;
  }

  const button = document.getElementById("startButton");

  button.disabled = true;

  document.getElementById("result").classList.remove("show");

  const winner = Math.floor(Math.random() * 8);

  const segment = 360 / 8;

  const targetAngle =
    360 - (winner * segment + segment / 2);

  rotation += 1440 + targetAngle;

  document.getElementById("wheel").style.transform =
    "rotate(" + rotation + "deg)";

  setTimeout(()=>{

    const winnerTeam = teams[winner];

    document.getElementById("winnerFlag").textContent =
      winnerTeam.flag;

    document.getElementById("winnerName").textContent =
      winnerTeam.name + " يفوز! 🏆";

    if(winner === selected){

      coins += 100;

      document.getElementById("resultText").textContent =
        "🎉 مبروك! فريقك فاز بالجولة +100 🪙";

    }else{

      document.getElementById("resultText").textContent =
        "الفائز هو " +
        winnerTeam.flag +
        " " +
        winnerTeam.name +
        ". حظ أوفر بالجولة القادمة!";

    }

    document.getElementById("coins").textContent =
      coins.toLocaleString();

    document.getElementById("result").classList.add("show");

    button.disabled = false;

  },4200);

}

function newRound(){

  selected = null;

  document.querySelectorAll(".team").forEach(button=>{
    button.classList.remove("selected");
  });

  document.getElementById("selectedText").textContent =
    "اختار فريق أولاً 👆";

  document.getElementById("startButton").disabled = true;

  document.getElementById("result").classList.remove("show");

}

</script>

</body>
</html>
