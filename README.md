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
  background:white;
  margin:10px auto;
  border-radius:10px;
  overflow:hidden;
  max-width:700px;
  box-shadow:0 2px 10px rgba(0,0,0,0.1);
}

.ad img{
  width:120px;
  height:120px;
  object-fit:cover;
}

.ad-info{
  padding:10px;
  flex:1;
}

.price{
  color:green;
  font-weight:bold;
}

.btn{
  display:inline-block;
  margin-top:8px;
  padding:6px 10px;
  background:#25D366;
  color:white;
  text-decoration:none;
  border-radius:6px;
  font-size:13px;
}

/* HIDE */
.hide{
  display:none;
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

  <div class="ad tech">
    <img src="https://via.placeholder.com/150">
    <div class="ad-info">
      <h3>Наушники</h3>
      <p class="price">80 000 сум</p>
      <a class="btn" href="https://t.me/baxromofx">Написать</a>
    </div>
  </div>

  <div class="ad study">
    <img src="https://via.placeholder.com/150">
    <div class="ad-info">
      <h3>Книга</h3>
      <p class="price">30 000 сум</p>
      <a class="btn" href="https://t.me/baxromofx">Написать</a>
    </div>
  </div>

  <div class="ad tech">
    <img src="https://<img width="547" height="365" alt="image" src="https://github.com/user-attachments/assets/e5ff1863-1214-40e5-9c94-733c4d3caaa7" />
/150">
    <div class="ad-info">
      <h3>Клавиатура</h3>
      <p class="price">150 000 сум</p>
      <a class="btn" href="https://t.me/baxromofx">Написать</a>
    </div>
  </div>

</div>

<script>
// SEARCH
document.getElementById("search").addEventListener("input", function(){
  let value = this.value.toLowerCase();
  let ads = document.querySelectorAll(".ad");

  ads.forEach(ad=>{
    let text = ad.innerText.toLowerCase();
    ad.style.display = text.includes(value) ? "flex" : "none";
  });
});

// CATEGORY FILTER
function filterCat(cat){
  let ads = document.querySelectorAll(".ad");
  let buttons = document.querySelectorAll(".cat");

  buttons.forEach(b=>b.classList.remove("active"));
  event.target.classList.add("active");

  ads.forEach(ad=>{
    if(cat === "all"){
      ad.style.display="flex";
    } else {
      ad.style.display = ad.classList.contains(cat) ? "flex" : "none";
    }
  });
}
</script>

</body>
</html>
