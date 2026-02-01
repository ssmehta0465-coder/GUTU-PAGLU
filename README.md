<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Beautiful Teasing Question</title>
    <style>
        body {
            font-family: 'Comic Sans MS', cursive, sans-serif; /* Fun, playful font */
            text-align: center;
            background: linear-gradient(45deg, #ff9a9e, #fecfef, #fecfef, #a8edea, #fed6e3, #d299c2); /* Rainbow gradient */
            background-size: 400% 400%;
            animation: gradientShift 10s ease infinite; /* Animated background */
            padding: 50px;
            overflow: hidden; /* For floating flowers */
            position: relative;
        }
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        .question {
            font-size: 28px;
            margin-bottom: 20px;
            color: #fff;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            position: relative;
        }
        .question::before, .question::after {
            content: "👸"; /* Doll emojis */
            font-size: 30px;
            position: absolute;
            top: -10px;
        }
        .question::before { left: -40px; }
        .question::after { right: -40px; }
        button {
            font-size: 20px;
            padding: 15px 30px;
            margin: 15px;
            cursor: pointer;
            border: none;
            border-radius: 50px; /* Rounded for cuteness */
            transition: all 0.3s ease;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }
        #yes {
            background: linear-gradient(45deg, #ff6b6b, #feca57); /* Warm gradient */
            color: white;
            animation: pulse 2s infinite; /* Pulsing animation */
        }
        #yes:hover {
            transform: scale(1.1);
            box-shadow: 0 6px 12px rgba(0,0,0,0.3);
        }
        #no {
            background: linear-gradient(45deg, #48cae4, #023e8a); /* Cool gradient */
            color: white;
            position: relative;
            animation: wiggle 1s infinite; /* Subtle wiggle */
        }
        #no:hover {
            transform: scale(1.05);
        }
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        @keyframes wiggle {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(-3deg); }
            75% { transform: rotate(3deg); }
        }
        #message {
            font-size: 24px;
            margin-top: 20px;
            display: none;
            color: #fff;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            animation: fadeIn 1s ease-in;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        /* Floating flowers animation */
        .flower {
            position: absolute;
            font-size: 24px;
            animation: float 15s linear infinite;
            pointer-events: none; /* So they don't interfere with clicks */
        }
        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-100px) rotate(360deg); opacity: 0; }
        }
        .flower:nth-child(1) { left: 10%; animation-delay: 0s; }
        .flower:nth-child(2) { left: 20%; animation-delay: 2s; }
        .flower:nth-child(3) { left: 30%; animation-delay: 4s; }
        .flower:nth-child(4) { left: 40%; animation-delay: 6s; }
        .flower:nth-child(5) { left: 50%; animation-delay: 8s; }
        .flower:nth-child(6) { left: 60%; animation-delay: 10s; }
        .flower:nth-child(7) { left: 70%; animation-delay: 12s; }
        .flower:nth-child(8) { left: 80%; animation-delay: 14s; }
    </style>
</head>
<body>
    <!-- Floating flowers -->
    <div class="flower">🌸</div>
    <div class="flower">🌺</div>
    <div class="flower">🌻</div>
    <div class="flower">🌷</div>
    <div class="flower">🌹</div>
    <div class="flower">🌼</div>
    <div class="flower">🌻</div>
    <div class="flower">🌸</div>

    <div class="question">Can you send me?</div>
    <button id="yes">Yes</button>
    <button id="no">No</button>
    <div id="message">Thank you mwahhh send me fast from every angle heheheh 💕</div>

    <script>
        const noButton = document.getElementById('no');
        const yesButton = document.getElementById('yes');
        const message = document.getElementById('message');

        // Function to move the "no" button randomly
        function moveNoButton() {
            const maxX = window.innerWidth - noButton.offsetWidth;
            const maxY = window.innerHeight - noButton.offsetHeight;
            const randomX = Math.random() * maxX;
            const randomY = Math.random() * maxY;
            noButton.style.left = randomX + 'px';
            noButton.style.top = randomY + 'px';
            noButton.style.position = 'absolute';
        }

        // On hover (desktop), move the button
        noButton.addEventListener('mouseover', moveNoButton);

        // On click/tap (mobile), move the button
        noButton.addEventListener('click', function(event) {
            event.preventDefault(); // Prevent default click
            moveNoButton();
        });

        // On "yes" click, show message
        yesButton.addEventListener('click', function() {
            message.style.display = 'block';
            // Hide buttons after yes is clicked
            yesButton.style.display = 'none';
            noButton.style.display = 'none';
        });
    </script>
</body>
</html>
