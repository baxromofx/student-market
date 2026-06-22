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
    .tg-btn{
  display:block;
  margin:15px auto;
  padding:10px;
  background:#25D366;
  color:white;
  text-align:center;
  border-radius:10px;
  text-decoration:none;
  width:80%;
  font-weight:bold;
}
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background: #f2f4f8;
    }

    .header {
      background: #2196F3;
      color: white;
      padding: 15px;
      text-align: center;
      font-size: 22px;
      font-weight: bold;
    }

    .container {
      padding: 15px;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
      gap: 15px;
    }

    .card {
      background: white;
      border-radius: 12px;
      padding: 10px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      text-align: center;
    }

    .card h3 {
      margin: 10px 0 5px;
    }

    .price {
      color: green;
      font-weight: bold;
    }

    .btn {
      margin-top: 10px;
      padding: 8px;
      background: #2196F3;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      width: 100%;
    }

    .btn:hover {
      background: #1976D2;
    }

    @media (max-width: 600px) {
      .header {
        font-size: 18px;
      }
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
