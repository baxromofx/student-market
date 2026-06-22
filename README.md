index.html
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
Students Market  powered by Baxromov Shohrux</title>
  
<style>
body{
    margin:0;
    font-family:Arial,sans-serif;
    min-height:100vh;
    background:linear-gradient(
        135deg,
        #00111f,
        #003366,
        #0055aa,
        #ffffff
    );
    background-size:400% 400%;
    animation:bgMove 12s ease infinite;
}

@keyframes bgMove{
    0%{background-position:0% 50%;}
    50%{background-position:100% 50%;}
    100%{background-position:0% 50%;}
}

/* HEADER */
.header{
    margin:15px;
    padding:18px;
    text-align:center;
    font-size:24px;
    font-weight:bold;
    color:white;

    background:rgba(255,255,255,0.12);
    backdrop-filter:blur(15px);

    border:1px solid rgba(255,255,255,0.2);
    border-radius:20px;

    box-shadow:
    0 0 20px rgba(0,170,255,0.4);
}

/* SEARCH */
.search-box{
    text-align:center;
    padding:10px;
}

.search-box input{
    width:90%;
    max-width:500px;

    padding:14px;

    border:none;
    outline:none;

    border-radius:15px;

    color:white;

    background:rgba(255,255,255,0.12);
    backdrop-filter:blur(15px);

    box-shadow:
    0 0 15px rgba(0,170,255,0.4);
}

.search-box input::placeholder{
    color:#ddd;
}

/* CATEGORY */
.cat{
    color:white;

    background:rgba(255,255,255,0.12);

    border-radius:20px;
    padding:10px 16px;

    transition:0.3s;

    border:1px solid rgba(255,255,255,0.2);
}

.cat:hover{
    transform:translateY(-2px);

    box-shadow:
    0 0 15px rgba(0,170,255,0.7);
}

.cat.active{
    background:#00cfff;
    color:black;
}

/* PRODUCT */
.ad{
    background:rgba(255,255,255,0.12);

    backdrop-filter:blur(15px);

    color:white;

    border-radius:20px;

    margin:15px auto;
    padding:15px;

    max-width:700px;

    border:1px solid rgba(255,255,255,0.15);

    box-shadow:
    0 0 20px rgba(0,170,255,0.25);

    transition:0.3s;
}

.ad:hover{
    transform:translateY(-5px);

    box-shadow:
    0 0 25px rgba(0,170,255,0.8);
}

.price{
    color:#00ffcc;
    font-size:18px;
    font-weight:bold;

    text-shadow:
    0 0 10px #00ffcc;
}

/* BUTTON */
.btn{
    display:inline-block;

    margin-top:10px;

    padding:10px 15px;

    text-decoration:none;

    color:white;

    border-radius:12px;

    background:linear-gradient(
    45deg,
    #00cfff,
    #0077ff
    );

    box-shadow:
    0 0 15px rgba(0,170,255,0.7);

    transition:0.3s;
}

.btn:hover{
    transform:scale(1.05);

    box-shadow:
    0 0 25px rgba(0,170,255,1);
}
  .ad{
    border-left:5px solid #00cfff;
}
</style>
</head>
<h3>📱 Телефон</h3>

<h3>🎧 Наушники</h3>

<h3>📖 Атлас</h3>

<h3>🧸 Мишка</h3>
<body>

<div class="header">🛒 </div>
Students Market  powered by Baxromov Shohrux
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
