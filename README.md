# student-market
index.html
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Student Market</title>

<style>
body{
  margin:0;
  font-family:Arial, sans-serif;
  background:#f2f4f5;
}

/* HEADER */
.header{
  background:#23a6d5;
  color:white;
  padding:15px;
  text-align:center;
  font-size:20px;
  font-weight:bold;
}

/* SEARCH */
.search-box{
  padding:10px;
  text-align:center;
}

.search-box input{
  width:90%;
  max-width:500px;
  padding:10px;
  border-radius:10px;
  border:1px solid #ccc;
  outline:none;
}

/* CATEGORIES */
.categories{
  display:flex;
  gap:10px;
  overflow-x:auto;
  padding:10px;
}

.cat{
  padding:8px 12px;
  background:white;
  border-radius:20px;
  white-space:nowrap;
  cursor:pointer;
  box-shadow:0 2px 5px rgba(0,0,0,0.1);
}

.cat.active{
  background:#23a6d5;
  color:white;
}

/* ADS */
.container{
  padding:10px;
}

.ad{
  display:flex;
  justify-content:space-between;
  align-items:center;
  background:white;
  margin:10px auto;
  border-radius:10px;
  padding:10px;
  max-width:700px;
  box-shadow:0 2px 10px rgba(0,0,0,0.1);
}

.ad-info{
  flex:1;
}

.price{
  color:green;
  font-weight:bold;
}

/* BUTTONS */
.btn{
  display:inline-block;
  margin-top:8px;
  padding:6px 10px;
  background:#25D366;
  color:white;
  text-decoration:none;
  border-radius:6px;
  font-size:13px;
  border:none;
  cursor:pointer;
}

.heart{
  font-size:20px;
  cursor:pointer;
  margin-left:10px;
}

/* CHAT */
.chat-box{
  position:fixed;
  bottom:10px;
  right:10px;
  width:280px;
  background:white;
  border-radius:10px;
  box-shadow:0 5px 20px rgba(0,0,0,0.2);
  display:none;
  flex-direction:column;
  overflow:hidden;
}

.chat-header{
  background:#23a6d5;
  color:white;
  padding:10px;
  display:flex;
  justify-content:space-between;
}

.chat-messages{
  height:180px;
  overflow-y:auto;
  padding:10px;
  font-size:14px;
}

.chat-input{
  display:flex;
  border-top:1px solid #ddd;
}

.chat-input input{
  flex:1;
  padding:8px;
  border:none;
  outline:none;
}

.chat-input button{
  background:#25D366;
  color:white;
  border:none;
  padding:8px;
}

.msg{
  background:#f1f1f1;
  padding:5px;
  margin:5px 0;
  border-radius:5px;
}
</style>
</head>

<body>

<div class="header">🛒 Student Market (OLX style)</div>

<!-- SEARCH -->
<div class="search-box">
  <input type="text" id="search" placeholder="Поиск товаров...">
</div>

<!-- CATEGORIES -->
<div class="categories">
  <div class="cat active" onclick="filterCat('all')">Все</div>
  <div class="cat" onclick="filterCat('tech')">Техника</div>
  <div class="cat" onclick="filterCat('study')">Учёба</div>
  <div class="cat" onclick="filterCat('other')">Другое</div>
</div>

<!-- ADS -->
<div class="container">

  <div class="ad tech" data-name="телефон">
    <div class="ad-info">
      <h3>Телефон</h3>
      <p class="price">1 200 000 сум</p>
      <button class="btn" onclick="openChat('Телефон')">Чат</button>
      <span class="heart" onclick="fav(this)">♡</span>
    </div>
  </div>

  <div class="ad study" data-name="ручка">
    <div class="ad-info">
      <h3>Ручка</h3>
      <p class="price">5 000 сум</p>
      <button class="btn" onclick="openChat('Ручка')">Чат</button>
      <span class="heart" onclick="fav(this)">♡</span>
    </div>
  </div>

  <div class="ad study" data-name="атлас">
    <div class="ad-info">
      <h3>Атлас</h3>
      <p class="price">25 000 сум</p>
      <button class="btn" onclick="openChat('Атлас')">Чат</button>
      <span class="heart" onclick="fav(this)">♡</span>
    </div>
  </div>

  <div class="ad other" data-name="мишка">
    <div class="ad-info">
      <h3>Мишка</h3>
      <p class="price">45 000 сум</p>
      <button class="btn" onclick="openChat('Мишка')">Чат</button>
      <span class="heart" onclick="fav(this)">♡</span>
    </div>
  </div>

</div>

<!-- CHAT -->
<div id="chatBox" class="chat-box">
  <div class="chat-header">
    <span id="chatTitle">Чат</span>
    <button onclick="closeChat()">✖️</button>
  </div>
  <div id="chatMessages" class="chat-messages"></div>

  <div class="chat-input">
    <input id="msgInput" placeholder="Сообщение...">
    <button onclick="sendMsg()">Отправить</button>
  </div>
</div>

<script>
let currentChat="";

// SEARCH
document.getElementById("search").addEventListener("input", function(){
  let val=this.value.toLowerCase();
  document.querySelectorAll(".ad").forEach(ad=>{
    ad.style.display = ad.innerText.toLowerCase().includes(val) ? "flex" : "none";
  });
});

// CATEGORY
function filterCat(cat){
  document.querySelectorAll(".ad").forEach(ad=>{
    ad.style.display = (cat==="all" || ad.classList.contains(cat)) ? "flex":"none";
  });
}

// FAVORITE
function fav(el){
  el.textContent = el.textContent==="♡"?"❤️":"♡";
}

// CHAT
function openChat(name){
  currentChat=name;
  document.getElementById("chatTitle").innerText="Чат: "+name;
  document.getElementById("chatBox").style.display="flex";
  loadMsg();
}

function closeChat(){
  document.getElementById("chatBox").style.display="none";
}

function sendMsg(){
  let input=document.getElementById("msgInput");
  if(input.value==="")return;

  let key="chat_"+currentChat;
  let arr=JSON.parse(localStorage.getItem(key)||"[]");

  arr.push(input.value);
  localStorage.setItem(key,JSON.stringify(arr));

  input.value="";
  loadMsg();
}

function loadMsg(){
  let key="chat_"+currentChat;
  let arr=JSON.parse(localStorage.getItem(key)||"[]");

  let box=document.getElementById("chatMessages");
  box.innerHTML="";

  arr.forEach(m=>{
    box.innerHTML+=<div class="msg">${m}</div>;
  });
}
</script>

</body>
</html>
