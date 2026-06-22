index.html
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Student Market powered by Baxromov</title>

<style>
body{
  margin:0;
  font-family:Arial, sans-serif;
  background: linear-gradient(270deg, #0f2027, #2c5364, #ffffff);
  background-size: 600% 600%;
  animation: rgbMove 10s ease infinite;
}

/* RGB LED ANIMATION */
@keyframes rgbMove{
  0%{background-position:0% 50%;}
  50%{background-position:100% 50%;}
  100%{background-position:0% 50%;}
}

/* HEADER */
.header{
  background: rgba(0,0,0,0.5);
  color:white;
  padding:18px;
  text-align:center;
  font-size:22px;
  font-weight:bold;
  backdrop-filter: blur(10px);
  border-bottom:1px solid rgba(255,255,255,0.1);
}

/* SEARCH */
.search-box input{
  width:92%;
  max-width:500px;
  padding:12px;
  border-radius:12px;
  border:none;
  outline:none;
  background: rgba(255,255,255,0.15);
  color:white;
  backdrop-filter: blur(10px);
}

.search-box input::placeholder{
  color:#ddd;
}

/* CATEGORIES */
.categories{
  display:flex;
  gap:10px;
  overflow-x:auto;
  padding:10px;
}

.cat{
  padding:8px 14px;
  background: rgba(255,255,255,0.15);
  color:white;
  border-radius:20px;
  cursor:pointer;
  white-space:nowrap;
  backdrop-filter: blur(10px);
  transition:0.3s;
}

.cat.active{
  background:#00c6ff;
  color:black;
}

/* ADS */
.ad{
  display:flex;
  justify-content:space-between;
  align-items:center;
  background: rgba(0,0,0,0.5);
  margin:12px auto;
  border-radius:15px;
  padding:12px;
  max-width:700px;
  box-shadow:0 0 20px rgba(0,198,255,0.3);
  color:white;
  backdrop-filter: blur(10px);
  transition:0.3s;
}

.ad:hover{
  transform:scale(1.02);
  box-shadow:0 0 25px rgba(0,198,255,0.6);
}

.price{
  color:#00ffcc;
  font-weight:bold;
}

.btn{
  display:inline-block;
  margin-top:8px;
  padding:8px 12px;
  background:#00c6ff;
  color:black;
  text-decoration:none;
  border-radius:8px;
  font-size:13px;
  font-weight:bold;
  box-shadow:0 0 10px rgba(0,198,255,0.5);
}
</style>
</head>

<body>

<div class="header">🛒 Student Market</div>

<!-- SEARCH -->
<div class="search-box">
  <input type="text" id="search" placeholder="Поиск товаров...">
</div>

<!-- CATEGORIES -->
<div class="categories">
  <div class="cat active" onclick="filterCat('all', event)">Все</div>
  <div class="cat" onclick="filterCat('tech', event)">Техника</div>
  <div class="cat" onclick="filterCat('study', event)">Учёба</div>
  <div class="cat" onclick="filterCat('other', event)">Другое</div>
</div>

<!-- ADS -->
<div class="container">

  <div class="ad tech">
    <div class="ad-info">
      <h3>Телефон</h3>
      <p class="price">1 200 000 сум</p>
      <a class="btn" href="https://t.me/baxromofx" target="_blank">Написать в Telegram</a>
    </div>
  </div>

  <div class="ad tech">
    <div class="ad-info">
      <h3>Наушники</h3>
      <p class="price">80 000 сум</p>
      <a class="btn" href="https://t.me/baxromofx" target="_blank">Написать в Telegram</a>
    </div>
  </div>

  <div class="ad study">
    <div class="ad-info">
      <h3>Атлас</h3>
      <p class="price">25 000 сум</p>
      <a class="btn" href="https://t.me/baxromofx" target="_blank">Написать в Telegram</a>
    </div>
  </div>

  <div class="ad other">
    <div class="ad-info">
      <h3>Мишка</h3>
      <p class="price">45 000 сум</p>
      <a class="btn" href="https://t.me/baxromofx" target="_blank">Написать в Telegram</a>
    </div>
  </div>

</div>

<script>

// SEARCH
document.getElementById("search").addEventListener("input", function(){
  let val = this.value.toLowerCase();

  document.querySelectorAll(".ad").forEach(ad=>{
    ad.style.display = ad.innerText.toLowerCase().includes(val)
      ? "flex"
      : "none";
  });
});


// CATEGORY FILTER (FIXED)
function filterCat(cat, event){

  // buttons active
  document.querySelectorAll(".cat").forEach(c=>{
    c.classList.remove("active");
  });
  event.target.classList.add("active");

  // filter ads
  document.querySelectorAll(".ad").forEach(ad=>{
    if(cat === "all"){
      ad.style.display = "flex";
    } else {
      ad.style.display = ad.classList.contains(cat) ? "flex" : "none";
    }
  });
}

</script>

</body>
</html>
