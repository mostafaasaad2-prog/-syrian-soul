<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Syrian Soul</title>
<style>
*{box-sizing:border-box}
body{
margin:0;
font-family:Arial,sans-serif;
background:#08080d;
color:white;
}
.container{
max-width:520px;
margin:auto;
min-height:100vh;
padding:25px 18px 100px;
background:radial-gradient(circle at top,#3b1455,#08080d 55%);
}
.logo{
width:55px;height:55px;
border-radius:18px;
display:flex;
align-items:center;
justify-content:center;
font-size:28px;
background:linear-gradient(135deg,#a855f7,#ec4899);
box-shadow:0 10px 30px #a855f755;
}
header{
display:flex;
align-items:center;
gap:12px;
margin-bottom:25px;
}
h1{margin:0;font-size:23px}
small{color:#aaa}
.hero{
padding:25px;
border-radius:28px;
background:linear-gradient(135deg,#7e22ce,#be185d);
box-shadow:0 15px 40px #0006;
}
.hero h2{font-size:27px;margin:0 0 10px}
.hero p{line-height:1.7;color:#f8eefe}
button{
border:0;
cursor:pointer;
}
.cta{
padding:13px 20px;
border-radius:14px;
background:white;
color:#741bb5;
font-weight:bold;
}
.title{
display:flex;
justify-content:space-between;
align-items:center;
margin:25px 0 12px;
}
.title h3{margin:0}
.rooms{
display:grid;
grid-template-columns:1fr 1fr;
gap:12px;
}
.room{
text-align:right;
padding:17px;
min-height:145px;
border-radius:20px;
background:#ffffff0b;
border:1px solid #ffffff12;
color:white;
}
.room span{
display:block;
margin-top:12px;
font-size:12px;
color:#ff7db7;
}
.games{
display:flex;
gap:12px;
overflow:auto;
}
.game{
min-width:145px;
padding:18px;
border-radius:20px;
background:#ffffff0b;
border:1px solid #ffffff12;
color:white;
text-align:right;
}
.card{
margin-top:25px;
padding:17px;
border-radius:22px;
background:#ffffff0b;
border:1px solid #ffffff12;
display:flex;
align-items:center;
gap:12px;
}
.avatar{
width:52px;height:52px;
border-radius:17px;
display:flex;
align-items:center;
justify-content:center;
font-size:25px;
background:linear-gradient(135deg,#f59e0b,#ec4899);
}
.coins{
margin-right:auto;
color:#ffd45a;
font-weight:bold;
}
nav{
position:fixed;
bottom:0;
left:50%;
transform:translateX(-50%);
width:min(520px,100%);
display:grid;
grid-template-columns:repeat(4,1fr);
padding:12px;
background:#09090eee;
backdrop-filter:blur(15px);
border-top:1px solid #ffffff12;
}
nav button{
background:none;
color:#aaa;
font-size:12px;
}
nav button:first-child{color:#d879ff}
nav b{display:block;font-size:21px;margin-bottom:4px}
</style>
</head>

<body>

<div class="container">

<header>
<div class="logo">✦</div>
<div>
<h1>Syrian Soul</h1>
<small>روحك… مكانها هون</small>
</div>
</header>

<div class="hero">
<h2>أهلاً بك في عالمك ✨</h2>
<p>
تعرّف على ناس جدد، ادخل غرفتك المفضلة
وخلّي السهرة تبدأ.
</p>
<button class="cta" onclick="document.getElementById('rooms').scrollIntoView({behavior:'smooth'})">
اكتشف الغرف
</button>
</div>

<div class="card">
<div class="avatar">👤</div>
<div>
<strong>ضيف Syrian Soul</strong>
<br>
<small>مستوى 1 • متصل الآن</small>
</div>
<div class="coins">🪙 1,000</div>
</div>

<div class="title" id="rooms">
<h3>🔥 الغرف النشطة</h3>
<small>عرض الكل</small>
</div>

<div class="rooms">

<button class="room" onclick="alert('🎙️ دخول غرفة ليالي الشام')">
🌙
<h3>ليالي الشام</h3>
<small>سوالف وضحك وموسيقى</small>
<span>● 128 متصل</span>
</button>

<button class="room" onclick="alert('👑 دخول مملكة Lucifer')">
👑
<h3>مملكة Lucifer</h3>
<small>غرفة VIP</small>
<span>● 86 متصل</span>
</button>

<button class="room" onclick="alert('🎙️ دخول السهرة السورية')">
🎙️
<h3>سهرة سورية</h3>
<small>دردشة صوتية</small>
<span>● 64 متصل</span>
</button>

<button class="room" onclick="alert('⚡ دخول التحدي')">
⚡
<h3>التحدي</h3>
<small>مسابقات وجوائز</small>
<span>● 41 متصل</span>
</button>

</div>

<div class="title">
<h3>🎮 الألعاب</h3>
<small>المزيد</small>
</div>

<div class="games">

<button class="game" onclick="alert('⚽ اللعبة قيد التطوير')">
⚽
<h3>ركلات الترجيح</h3>
<small>تحدّى أصدقاءك</small>
</button>

<button class="game" onclick="alert('🧠 اللعبة قيد التطوير')">
🧠
<h3>مسابقة الروح</h3>
<small>أسئلة وجوائز</small>
</button>

<button class="game" onclick="alert('🎯 اللعبة قيد التطوير')">
🎯
<h3>التحدي السريع</h3>
<small>نقاط يومية</small>
</button>

</div>

<div class="title">
<h3>🏆 المتصدرون</h3>
<small>هذا الأسبوع</small>
</div>

<div class="card">
<div class="avatar">🥇</div>
<div>
<strong>Syrian King</strong>
<br>
<small>المستوى 48</small>
</div>
<div class="coins">💎 98K</div>
</div>

<div class="card">
<div class="avatar">🥈</div>
<div>
<strong>Queen Soul</strong>
<br>
<small>المستوى 42</small>
</div>
<div class="coins">💎 76K</div>
</div>

</div>

<nav>
<button><b>🏠</b>الرئيسية</button>
<button><b>🌐</b>اكتشف</button>
<button><b>💬</b>الرسائل</button>
<button><b>👤</b>حسابي</button>
</nav>

</body>
</html>
