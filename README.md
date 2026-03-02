<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&display=swap" rel="stylesheet">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        body {
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            background-color: #ffc0cb; /* Fallback pink */
        }

        /* The Full Background Forest */
        .forest-bg {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: url('https://images.unsplash.com/photo-1522383225653-ed111181a951?q=80&w=2070&auto=format&fit=crop') no-repeat center center;
            background-size: cover;
            z-index: -1;
            filter: brightness(0.9);
        }

        /* Glass Card */
        .card {
            width: 85%;
            max-width: 320px;
            padding: 40px 20px;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.4);
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
            animation: float 3s ease-in-out infinite;
        }

        h1 { font-family: 'Dancing Script', cursive; color: #fff; font-size: 2.5rem; text-shadow: 2px 2px 10px rgba(218, 30, 124, 0.5); }
        p { color: #fff; font-family: sans-serif; margin-top: 10px; font-weight: 300; letter-spacing: 1px; }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        /* Falling Flower Animation */
        .petal {
            position: absolute;
            background-color: #ffb7c5;
            border-radius: 150% 0 150% 0;
            opacity: 0.8;
            pointer-events: none;
            animation: fall linear infinite;
        }

        @keyframes fall {
            0% { transform: translateY(-10vh) rotate(0deg) translateX(0); }
            100% { transform: translateY(110vh) rotate(360deg) translateX(80px); }
        }
    </style>
</head>
<body>

    <div class="forest-bg"></div>

    <div class="card">
        <h1>Happy Birthday!</h1>
        <p>May your day be as beautiful as these blossoms.</p>
    </div>

    <script>
        function createPetal() {
            const petal = document.createElement('div');
            petal.classList.add('petal');
            const size = Math.random() * 10 + 5 + 'px';
            petal.style.width = size;
            petal.style.height = size;
            petal.style.left = Math.random() * 100 + 'vw';
            petal.style.animationDuration = Math.random() * 3 + 4 + 's';
            petal.style.opacity = Math.random();
            document.body.appendChild(petal);
            setTimeout(() => petal.remove(), 6000);
        }
        setInterval(createPetal, 150);
    </script>
</body>
</html>
