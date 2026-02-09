<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <title>Проверка бдительности | День безопасного интернета</title>
    <style>
        body { 
            font-family: Arial, sans-serif; 
            text-align: center; 
            margin: 50px; 
            transition: 0.5s;
        }
        .bait { 
            background: linear-gradient(45deg, #FFD700, #FFA500);
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(255, 165, 0, 0.3);
        }
        .lesson { 
            background: #f0f8ff;
            padding: 40px;
            border-radius: 20px;
            border-left: 10px solid #ff4444;
            display: none;
            text-align: left;
            max-width: 800px;
            margin: 0 auto;
        }
        .btn {
            padding: 15px 40px;
            font-size: 20px;
            background: #4CAF50;
            color: white;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            margin: 20px;
            transition: 0.3s;
        }
        .btn:hover {
            background: #45a049;
            transform: scale(1.05);
        }
        .warning {
            color: #ff4444;
            font-size: 36px;
            font-weight: bold;
        }
        .counter {
            background: black;
            color: lime;
            font-family: monospace;
            padding: 10px;
            display: inline-block;
            margin: 10px;
        }
    </style>
</head>
<body>
    <div class="bait" id="bait">
        <h1>⚠️ ВНИМАНИЕ! ⚠️</h1>
        <h2>Ваше устройство заражено вирусом!</h2>
        <p>Обнаружена критическая угроза безопасности</p>
        <p>Немедленно выполните сканирование:</p>
        <button class="btn" onclick="showLesson()">▶️ НЕМЕДЛЕННО СКАНИРОВАТЬ</button>
        <p><small>Отсчёт времени: <span id="timer">10</span> сек.</small></p>
        <div class="counter">Угроз обнаружено: 127</div>
    </div>
    
    <div class="lesson" id="lesson">
        <h1 class="warning">🎯 Вы попались!</h1>
        <p>Именно так выглядят типичные мошеннические страницы!</p>
        
        <h2>🔍 Что было в этой приманке:</h2>
        <ul>
            <li>✅ Ложное ощущение срочности ("вирус", "угроза")</li>
            <li>✅ Счётчик обратного отсчёта для давления</li>
            <li>✅ Технический жаргон для запугивания</li>
            <li>✅ Яркая кнопка с требованием немедленного действия</li>
        </ul>
        
        <h2>🛡️ Как защитить себя:</h2>
        <ol>
            <li><strong>Не паникуйте</strong> — мошенники играют на эмоциях</li>
            <li><strong>Проверяйте URL</strong> — настоящие антивирусы не работают через браузер</li>
            <li><strong>Не нажимайте</strong> на кнопки в панике</li>
            <li><strong>Установите настоящий антивирус</strong> — Kaspersky, Avast, Windows Defender</li>
        </ol>
        
        <div style="background: #e8f5e9; padding: 20px; border-radius: 10px;">
            <h3>📅 Сегодня — Всемирный день безопасного интернета!</h3>
            <p>Поделитесь этой страницей с друзьями, чтобы повысить их бдительность!</p>
            <button class="btn" onclick="location.reload()">Показать приманку снова</button>
        </div>
    </div>

    <script>
        let timeLeft = 10;
        const timerEl = document.getElementById('timer');
        const timer = setInterval(() => {
            timeLeft--;
            timerEl.textContent = timeLeft;
            if (timeLeft <= 0) {
                clearInterval(timer);
                if (!lessonShown) showLesson();
            }
        }, 1000);
        
        let lessonShown = false;
        function showLesson() {
            lessonShown = true;
            clearInterval(timer);
            document.getElementById('bait').style.display = 'none';
            document.getElementById('lesson').style.display = 'block';
        }
    </script>
</body>
</html>
