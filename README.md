<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <style>
        body { background: #1a1a1a; color: white; text-align: center; font-family: sans-serif; overflow: hidden; }
        .coin { width: 200px; height: 200px; background: gold; border-radius: 50%; margin: 50px auto; 
                display: flex; align-items: center; justify-content: center; font-size: 80px;
                box-shadow: 0 0 20px orange; cursor: pointer; transition: transform 0.1s; }
        .coin:active { transform: scale(0.95); }
    </style>
</head>
<body>
    <h1>Клікай!</h1>
    <div class="coin" id="tapBtn">🐹</div>
    <p>Баланс: <span id="bal">0</span> P</p>

    <script>
        let tg = window.Telegram.WebApp;
        let balance = 0;
        tg.expand();

        document.getElementById('tapBtn').onclick = () => {
            balance += 1;
            document.getElementById('bal').innerText = (balance * 0.0001).toFixed(4);
            tg.sendData(JSON.stringify({action: 'click'}));
        };
    </script>
</body>
</html>
