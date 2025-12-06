<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Мой анимированный сайт</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            background-size: 400% 400%;
            animation: gradient 15s ease infinite;
            color: #333;
            line-height: 1.6;
            overflow-x: hidden;
            min-height: 100vh;
            padding: 20px;
        }

        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        header {
            text-align: center;
            padding: 40px 20px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            margin-bottom: 30px;
            animation: fadeInDown 1s ease-out;
            position: relative;
            overflow: hidden;
        }

        header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4, #feca57);
            background-size: 500% 100%;
            animation: headerLine 3s linear infinite;
        }

        @keyframes headerLine {
            0% { background-position: 0% 0%; }
            100% { background-position: 500% 0%; }
        }

        h1 {
            font-size: 3.5rem;
            margin-bottom: 10px;
            background: linear-gradient(90deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4, #feca57);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            background-size: 300% 100%;
            animation: gradientText 5s ease infinite;
        }

        @keyframes gradientText {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .tagline {
            font-size: 1.5rem;
            color: #666;
            margin-bottom: 20px;
        }

        .typing-text {
            font-size: 1.8rem;
            overflow: hidden;
            border-right: 3px solid #3498db;
            white-space: nowrap;
            margin: 0 auto;
            width: 0;
            animation: typing 4s steps(30, end) forwards, blink-caret 0.75s step-end infinite;
            color: #2c3e50;
            font-weight: bold;
        }

        @keyframes typing {
            from { width: 0; }
            to { width: 100%; }
        }

        @keyframes blink-caret {
            from, to { border-color: transparent; }
            50% { border-color: #3498db; }
        }

        .content-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 30px;
        }

        .card {
            background: rgba(255, 255, 255, 0.9);
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            animation: fadeInUp 0.8s ease-out;
            position: relative;
            overflow: hidden;
        }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, #ff6b6b, #4ecdc4);
        }

        .card h2 {
            color: #2c3e50;
            margin-bottom: 15px;
            font-size: 1.8rem;
            position: relative;
            display: inline-block;
        }

        .card h2::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 50px;
            height: 3px;
            background: #3498db;
            transition: width 0.3s ease;
        }

        .card:hover h2::after {
            width: 100%;
        }

        .animated-words {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin: 20px 0;
        }

        .word {
            padding: 8px 15px;
            background: #f1f1f1;
            border-radius: 30px;
            font-weight: bold;
            animation: float 3s ease-in-out infinite;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .word:hover {
            transform: scale(1.1);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .word:nth-child(1) { animation-delay: 0s; background: #ff9ff3; color: #2d3436; }
        .word:nth-child(2) { animation-delay: 0.5s; background: #feca57; color: #2d3436; }
        .word:nth-child(3) { animation-delay: 1s; background: #ff6b6b; color: white; }
        .word:nth-child(4) { animation-delay: 1.5s; background: #48dbfb; color: #2d3436; }
        .word:nth-child(5) { animation-delay: 2s; background: #1dd1a1; color: white; }
        .word:nth-child(6) { animation-delay: 2.5s; background: #f368e0; color: white; }
        .word:nth-child(7) { animation-delay: 3s; background: #ff9f43; color: white; }
        .word:nth-child(8) { animation-delay: 3.5s; background: #00d2d3; color: white; }

        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }

        .feature-list {
            list-style: none;
        }

        .feature-list li {
            padding: 12px 0;
            border-bottom: 1px dashed #ddd;
            position: relative;
            padding-left: 30px;
            animation: slideInRight 0.5s forwards;
            opacity: 0;
        }

        .feature-list li::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: #2ecc71;
            font-weight: bold;
            font-size: 1.2rem;
        }

        .feature-list li:nth-child(1) { animation-delay: 0.2s; }
        .feature-list li:nth-child(2) { animation-delay: 0.4s; }
        .feature-list li:nth-child(3) { animation-delay: 0.6s; }
        .feature-list li:nth-child(4) { animation-delay: 0.8s; }
        .feature-list li:nth-child(5) { animation-delay: 1s; }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(-20px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .button-group {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
            margin: 25px 0;
        }

        .button {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #3498db, #2980b9);
            color: white;
            padding: 12px 25px;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .button:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        .button:active {
            transform: translateY(-2px);
        }

        .button::after {
            content: "";
            position: absolute;
            top: 50%;
            left: 50%;
            width: 5px;
            height: 5px;
            background: rgba(255, 255, 255, 0.5);
            opacity: 0;
            border-radius: 100%;
            transform: scale(1, 1) translate(-50%);
            transform-origin: 50% 50%;
        }

        .button:focus:not(:active)::after {
            animation: ripple 1s ease-out;
        }

        .button.secondary {
            background: linear-gradient(135deg, #2ecc71, #27ae60);
        }

        .button.tertiary {
            background: linear-gradient(135deg, #e74c3c, #c0392b);
        }

        @keyframes ripple {
            0% {
                transform: scale(0, 0);
                opacity: 0.5;
            }
            100% {
                transform: scale(20, 20);
                opacity: 0;
            }
        }

        .animated-box {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 15px;
            margin: 25px 0;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
            font-weight: bold;
            animation: pulse 2s infinite, colorShift 5s infinite alternate;
            position: relative;
            overflow: hidden;
        }

        .animated-box::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1), transparent);
            transform: rotate(45deg);
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        @keyframes colorShift {
            0% { filter: hue-rotate(0deg); }
            100% { filter: hue-rotate(360deg); }
        }

        .floating-elements {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .floating-element {
            position: absolute;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.2);
            animation: floatAround 20s infinite linear;
        }

        .floating-element:nth-child(1) {
            width: 80px;
            height: 80px;
            top: 10%;
            left: 10%;
            animation-duration: 25s;
        }

        .floating-element:nth-child(2) {
            width: 120px;
            height: 120px;
            top: 70%;
            left: 80%;
            animation-duration: 30s;
        }

        .floating-element:nth-child(3) {
            width: 60px;
            height: 60px;
            top: 50%;
            left: 20%;
            animation-duration: 20s;
        }

        .floating-element:nth-child(4) {
            width: 100px;
            height: 100px;
            top: 20%;
            left: 70%;
            animation-duration: 35s;
        }

        @keyframes floatAround {
            0% {
                transform: translate(0, 0) rotate(0deg);
            }
            25% {
                transform: translate(100px, 100px) rotate(90deg);
            }
            50% {
                transform: translate(0, 200px) rotate(180deg);
            }
            75% {
                transform: translate(-100px, 100px) rotate(270deg);
            }
            100% {
                transform: translate(0, 0) rotate(360deg);
            }
        }

        footer {
            text-align: center;
            padding: 30px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 15px;
            margin-top: 40px;
            animation: fadeIn 1.5s ease-out;
        }

        .social-icons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0;
        }

        .social-icon {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: #3498db;
            color: white;
            font-size: 1.5rem;
            transition: all 0.3s ease;
            animation: bounce 2s infinite;
        }

        .social-icon:nth-child(1) { animation-delay: 0.1s; background: #3b5998; }
        .social-icon:nth-child(2) { animation-delay: 0.2s; background: #1da1f2; }
        .social-icon:nth-child(3) { animation-delay: 0.3s; background: #e1306c; }
        .social-icon:nth-child(4) { animation-delay: 0.4s; background: #0077b5; }

        .social-icon:hover {
            transform: scale(1.2) rotate(15deg);
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Адаптивность */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            .typing-text {
                font-size: 1.4rem;
            }
            
            .content-grid {
                grid-template-columns: 1fr;
            }
            
            .button-group {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <div class="floating-elements">
        <div class="floating-element"></div>
        <div class="floating-element"></div>
        <div class="floating-element"></div>
        <div class="floating-element"></div>
    </div>

    <div class="container">
        <header>
            <h1>Мой анимированный сайт</h1>
            <p class="tagline">Исследуйте мир анимаций и интерактивности</p>
            <p class="typing-text">Добро пожаловать в захватывающий мир веб-дизайна!</p>
        </header>

        <div class="content-grid">
            <div class="card">
                <h2>Анимированные слова</h2>
                <p>Наведите курсор на слова, чтобы увидеть эффекты:</p>
                <div class="animated-words">
                    <div class="word">Креативность</div>
                    <div class="word">Инновации</div>
                    <div class="word">Дизайн</div>
                    <div class="word">Анимация</div>
                    <div class="word">Интерактивность</div>
                    <div class="word">Вдохновение</div>
                    <div class="word">Технологии</div>
                    <div class="word">Будущее</div>
                </div>
            </div>

            <div class="card">
                <h2>Особенности сайта</h2>
                <ul class="feature-list">
                    <li>Потрясающие анимации при прокрутке</li>
                    <li>Интерактивные элементы с эффектами наведения</li>
                    <li>Плавные переходы и трансформации</li>
                    <li>Адаптивный дизайн для всех устройств</li>
                    <li>Современный градиентный фон</li>
                </ul>
            </div>

            <div class="card">
                <h2>Интерактивные кнопки</h2>
                <p>Нажмите на кнопки, чтобы увидеть эффекты:</p>
                <div class="button-group">
                    <a href="#" class="button">Исследовать</a>
                    <a href="#" class="button secondary">Узнать больше</a>
                    <a href="#" class="button tertiary">Связаться</a>
                </div>
                <p>Анимированный блок с пульсацией:</p>
                <div class="animated-box">
                    Динамический контент
                </div>
            </div>
        </div>

        <footer>
            <p>© .</p>
            <div class="social-icons">
                <div class="social-icon">f</div>
                <div class="social-icon">t</div>
                <div class="social-icon">i</div>
                <div class="social-icon">in</div>
            </div>
            <p>Следите за нами в социальных сетях!</p>
        </footer>
    </div>

    <script>
        // Добавляем эффект параллакса для фона
        document.addEventListener('mousemove', function(e) {
            const floatingElements = document.querySelectorAll('.floating-element');
            const x = e.clientX / window.innerWidth;
            const y = e.clientY / window.innerHeight;
            
            floatingElements.forEach((el, index) => {
                const speed = (index + 1) * 0.5;
                const xMove = x * speed * 100;
                const yMove = y * speed * 100;
                el.style.transform = `translate(${xMove}px, ${yMove}px)`;
            });
        });

        // Добавляем анимацию при скролле
        document.addEventListener('DOMContentLoaded', function() {
            const animatedElements = document.querySelectorAll('.card, .feature-list li');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.animationPlayState = 'running';
                    }
                });
            }, { threshold: 0.1 });
            
            animatedElements.forEach(el => {
                observer.observe(el);
            });

            // Добавляем эффект при клике на слова
            const words = document.querySelectorAll('.word');
            words.forEach(word => {
                word.addEventListener('click', function() {
                    this.style.animation = 'none';
                    this.offsetHeight; // Trigger reflow
                    this.style.animation = null;
                    this.style.transform = 'scale(1.3)';
                    setTimeout(() => {
                        this.style.transform = 'scale(1)';
                    }, 300);
                });
            });

            // Добавляем случайное движение для плавающих элементов
            const floatingElements = document.querySelectorAll('.floating-element');
            setInterval(() => {
                floatingElements.forEach(el => {
                    const randomX = Math.random() * 20 - 10;
                    const randomY = Math.random() * 20 - 10;
                    el.style.transform += ` translate(${randomX}px, ${randomY}px)`;
                });
            }, 3000);
        });
    </script>
    <li><a href="https://vms.drweb.ru/scan_file/" target="_blank">антивирус</a></li>
</body>
</html>
