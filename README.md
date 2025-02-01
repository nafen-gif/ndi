# ndi
عندما تضغط ينتظرك مفاجأة
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Pages with Sounds and Sparkles</title>
    <style>
        body {
            background: linear-gradient(45deg, #ff7f50, #ff1493, #ff69b4, #f0e68c); 
            background-size: 400% 400%;
            animation: gradientAnimation 6s ease infinite;
            font-family: 'Arial', sans-serif;
        }

        @keyframes gradientAnimation {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        h1 {
            font-size: 3em;
            text-align: center;
            color: white;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
        }

        button {
            padding: 15px 30px;
            font-size: 1.5em;
            background-color: rgba(255, 255, 255, 0.8);
            border: none;
            cursor: pointer;
            margin-top: 20px;
            display: block;
            margin-left: auto;
            margin-right: auto;
            border-radius: 10px;
        }

        button:hover {
            background-color: rgba(255, 255, 255, 1);
            box-shadow: 0px 0px 15px rgba(255, 255, 255, 0.6);
        }

        .page {
            display: none;
        }

        .page.active {
            display: block;
        }

        /* إضافة تأثيرات براقة على الصفحة */
        .sparkle {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            z-index: -1;
            background: url('https://media.giphy.com/media/3o7TKoOVESv0tkxOue/giphy.gif') center center no-repeat;
            background-size: cover;
        }
    </style>
</head>
<body>

    <div class="sparkle"></div>

    <!-- الصفحة الأولى: النجمة -->
    <div id="starPage" class="page active">
        <h1>اضغط على النجمة ⭐</h1>
        <button onclick="goToCatPage()">اضغط على النجمة</button>
    </div>

    <!-- الصفحة الثانية: القطة -->
    <div id="catPage" class="page">
        <h1>اضغط على القطة 🐱</h1>
        <button onclick="goToWolfPage()">اضغط على القطة</button>
        <audio id="catSound" src="https://www.soundjay.com/button/beep-07.wav"></audio>
    </div>

    <!-- الصفحة الثالثة: الذئب -->
    <div id="wolfPage" class="page">
        <h1>اضغط على الذئب 🐺</h1>
        <button onclick="goToMonkeyPage()">اضغط على الذئب</button>
        <audio id="wolfSound" src="https://www.soundjay.com/animal/wolf-howling-01.mp3"></audio>
    </div>

    <!-- الصفحة الرابعة: القرد -->
    <div id="monkeyPage" class="page">
        <h1>اضغط على القرد 🐒</h1>
        <button onclick="goToFinalPage()">اضغط على القرد</button>
        <audio id="monkeySound" src="https://www.soundjay.com/animal/monkey-01.mp3"></audio>
    </div>

    <!-- الصفحة الأخيرة: النهاية -->
    <div id="finalPage" class="page">
        <h1>اضغط to someone 💦💦💦💦💦 مع صوت يقول تفو عليك</h1>
        <button onclick="goToStartPage()">اضغط هنا</button>
    </div>

    <script>
        function goToCatPage() {
            document.getElementById('starPage').classList.remove('active');
            document.getElementById('catPage').classList.add('active');
            document.getElementById('catSound').play();
        }

        function goToWolfPage() {
            document.getElementById('catPage').classList.remove('active');
            document.getElementById('wolfPage').classList.add('active');
            document.getElementById('wolfSound').play();
        }

        function goToMonkeyPage() {
            document.getElementById('wolfPage').classList.remove('active');
            document.getElementById('monkeyPage').classList.add('active');
            document.getElementById('monkeySound').play();
        }

        function goToFinalPage() {
            document.getElementById('monkeyPage').classList.remove('active');
            document.getElementById('finalPage').classList.add('active');
        }

        function goToStartPage() {
            document.getElementById('finalPage').classList.remove('active');
            document.getElementById('starPage').classList.add('active');
        }
    </script>
</body>
</html>
