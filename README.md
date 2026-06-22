# student-market
index.html
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Student Market</title>
<a href="https://t.me/baxromofx" class="tg-btn">💬 Написать в Telegram</a>
  <style>
  .tg-button{
    display:inline-block;
    margin-top:20px;
    padding:12px 20px;
    background:#0088cc;
    color:white;
    text-decoration:none;
    border-radius:10px;
    font-weight:bold;
    transition:0.3s;
} 
body{
  margin:0;
  font-family: Arial, sans-serif;
  background: linear-gradient(135deg,#74ebd5,#ACB6E5);
}.tg-button{
    display:inline-block;
    margin-top:20px;
    padding:12px 20px;
    background:#0088cc;
    color:white;
    text-decoration:none;
    border-radius:10px;
    font-weight:bold;
    transition:0.3s;
}
.tg-button:hover{
    background:#0077b5;
    transform:scale(1.05);
}
/* шапка */
.header{
  background: rgba(255,255,255,0.2);
  backdrop-filter: blur(10px);
  padding:20px;
  text-align:center;
  font-size:24px;
  font-weight:bold;
  color:#fff;
}
/* кнопка Telegram */
.tg-btn{
  display:block;
  margin:15px auto;
  padding:12px;
  background:#0088cc;
  color:white;
  text-align:center;
  border-radius:12px;
  text-decoration:none;
  width:80%;
  font-weight:bold;
  box-shadow:0 5px 15px rgba(0,0,0,0.2);
}
/* контейнер товаров */
.container{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(160px,1fr));
  gap:15px;
  padding:15px;
}
/* карточка товара */
.card{
  background:white;
  border-radius:15px;
  padding:10px;
  text-align:center;
  box-shadow:0 5px 15px rgba(0,0,0,0.15);
  transition:0.3s;
}
.card:hover{
  transform:translateY(-5px);
}
.card img{
  width:100%;
  border-radius:10px;
}
.price{
  color:green;
  font-weight:bold;
}
.btn{
  margin-top:10px;
  padding:8px;
  background:#2196F3;
  color:white;
  border:none;
  border-radius:10px;
  width:100%;
}
  </style>
</head>

<body>
  <div class="header">
    🛒 Student Market
  </div>
  <div class="container">
    <div class="card">
      <h3>Рюкзак</h3>
      <p class="price">120 000 сум</p>
      <button class="btn">Купить</button>
    </div>
    <div class="card">
      <h3>Наушники</h3>
      <p class="price">80 000 сум</p>
      <button class="btn">Купить</button>
    </div>
    <div class="card">
      <h3>Книга</h3>
      <p class="price">30 000 сум</p>
      <button class="btn">Купить</button>
    </div>
    <div class="card">
      <h3>Клавиатура</h3>
      <p class="price">150 000 сум</p>
      <button class="btn">Купить</button>
    </div>
  </div>
</body>
</html>
