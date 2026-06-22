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
  background:#eef2f5;
}

/* HEADER */
.header{
  background:linear-gradient(135deg,#2193b0,#6dd5ed);
  color:white;
  padding:18px;
  text-align:center;
  font-size:22px;
  font-weight:bold;
}

/* SEARCH */
.search-box{
  padding:10px;
  text-align:center;
}

.search-box input{
  width:92%;
  max-width:500px;
  padding:12px;
  border-radius:12px;
  border:1px solid #ccc;
  outline:none;
  font-size:14px;
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
  background:white;
  border-radius:20px;
  cursor:pointer;
  white-space:nowrap;
  box-shadow:0 2px 6px rgba(0,0,0,0.08);
  transition:0.2s;
}

.cat.active{
  background:#2193b0;
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
  margin:12px auto;
  border-radius:12px;
  padding:12px;
  max-width:700px;
  box-shadow:0 3px 12px rgba(0,0,0,0.08);
  transition:0.2s;
}

.ad:hover{
  transform:scale(1.01);
}

.ad-info{
  flex:1;
}

h3{
  margin:0;
  font-size:16px;
}

.price{
  color:green;
  font-weight:bold;
  margin-top:5px;
}

/* BUTTON */
.btn{
  display:inline-block;
  margin-top:8px;
  padding:8px 12px;
  background:#25D366;
  color:white;
  text-decoration:none;
  border-radius:8px;
  font-size:13px;
  font-weight:bold;
}

/* HIDE */
.hide{
  display:none;
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
