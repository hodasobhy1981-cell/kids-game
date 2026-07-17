# kids-game<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<title>لعبة الأطفال</title>
<style>
body{
  font-family: Arial;
  text-align:center;
  background:#fef3c7;
  padding:30px;
}
.box{
  background:white;
  border-radius:20px;
  padding:25px;
  max-width:500px;
  margin:auto;
  box-shadow:0 0 10px #ccc;
}
button{
  display:block;
  width:90%;
  margin:10px auto;
  padding:15px;
  border:none;
  border-radius:15px;
  background:#60a5fa;
  color:white;
  font-size:18px;
  cursor:pointer;
}
button:hover{
  background:#2563eb;
}
#result{
  font-size:25px;
  color:green;
}
</style>
</head>

<body>

<div class="box">
<h1>🎮 لعبة الأصدقاء الصغار</h1>

<h2 id="question"></h2>

<div id="answers"></div>

<p id="score"></p>

<div id="result"></div>
</div>

<script>

let questions=[
{
q:"ما هو لون الشمس؟ ☀️",
a:["أزرق","أصفر","أخضر","أسود"],
c:"أصفر"
},
{
q:"كم عدد أصابع اليد؟ ✋",
a:["3","5","8","10"],
c:"5"
},
{
q:"أي حيوان يقول موو؟ 🐄",
a:["قطة","بقرة","سمكة","طائر"],
c:"بقرة"
}
];

let index=0;
let score=0;

function showQuestion(){
if(index < questions.length){

document.getElementById("question").innerHTML =
questions[index].q;

let box=document.getElementById("answers");
box.innerHTML="";

questions[index].a.forEach(x=>{
let btn=document.createElement("button");
btn.innerHTML=x;
btn.onclick=()=>check(x);
box.appendChild(btn);
});

document.getElementById("score").innerHTML=
"⭐ النقاط: "+score;

}else{
document.getElementById("question").innerHTML="";
document.getElementById("answers").innerHTML="";
document.getElementById("result").innerHTML=
"🎉 أحسنت! نتيجتك "+score+" من "+questions.length;
}
}

function check(answer){
if(answer==questions[index].c){
score++;
alert("👏 إجابة صحيحة");
}else{
alert("😊 حاول مرة أخرى");
}
index++;
showQuestion();
}

showQuestion();

</script>

</body>
</html>
