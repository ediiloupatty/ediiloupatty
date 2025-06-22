<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Edii Lou Patty - Neural Network Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Monaco', 'Menlo', 'Ubuntu Mono', monospace;
            background: #0d1117;
            color: #c9d1d9;
            overflow-x: hidden;
            min-height: 100vh;
        }

        .container {
            position: relative;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .neural-network {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.3;
        }

        .profile-card {
            background: rgba(13, 17, 23, 0.9);
            border: 1px solid #30363d;
            border-radius: 12px;
            padding: 40px;
            max-width: 800px;
            width: 100%;
            backdrop-filter: blur(10px);
            box-shadow: 0 16px 32px rgba(0, 0, 0, 0.4);
            animation: slideUp 1s ease-out;
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
        }

        .name {
            font-size: 3rem;
            font-weight: bold;
            background: linear-gradient(45deg, #f78166, #58a6ff, #7c3aed);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradient 3s ease-in-out infinite;
            margin-bottom: 10px;
        }

        @keyframes gradient {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .title {
            font-size: 1.2rem;
            color: #7c3aed;
            margin-bottom: 20px;
        }

        .typing-container {
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .typing-text {
            color: #58a6ff;
            font-size: 1.1rem;
        }

        .cursor {
            display: inline-block;
            width: 2px;
            height: 20px;
            background: #58a6ff;
            margin-left: 2px;
            animation: blink 1s infinite;
        }

        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0; }
        }

        .info-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }

        .info-section {
            background: rgba(48, 54, 61, 0.3);
            border: 1px solid #30363d;
            border-radius: 8px;
            padding: 20px;
            transition: all 0.3s ease;
        }

        .info-section:hover {
            border-color: #58a6ff;
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(88, 166, 255, 0.1);
        }

        .section-title {
            color: #f78166;
            font-size: 1.1rem;
            font-weight: bold;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
        }

        .section-title::before {
            content: '';
            width: 4px;
            height: 20px;
            background: linear-gradient(45deg, #f78166, #58a6ff);
            margin-right: 10px;
            border-radius: 2px;
        }

        .tech-list {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .tech-item {
            background: rgba(88, 166, 255, 0.1);
            color: #58a6ff;
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 0.9rem;
            border: 1px solid rgba(88, 166, 255, 0.2);
            transition: all 0.3s ease;
        }

        .tech-item:hover {
            background: rgba(88, 166, 255, 0.2);
            transform: scale(1.05);
        }

        .stats-container {
            display: flex;
            justify-content: space-around;
            margin: 30px 0;
            flex-wrap: wrap;
            gap: 20px;
        }

        .stat-item {
            text-align: center;
            padding: 15px;
            background: rgba(48, 54, 61, 0.3);
            border-radius: 8px;
            border: 1px solid #30363d;
            min-width: 120px;
            transition: all 0.3s ease;
        }

        .stat-item:hover {
            border-color: #7c3aed;
            transform: scale(1.05);
        }

        .stat-number {
            font-size: 2rem;
            font-weight: bold;
            color: #7c3aed;
            margin-bottom: 5px;
        }

        .stat-label {
            color: #8b949e;
            font-size: 0.9rem;
        }

        .contact-section {
            text-align: center;
            margin-top: 40px;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0;
        }

        .contact-link {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 10px 20px;
            background: rgba(48, 54, 61, 0.5);
            border: 1px solid #30363d;
            border-radius: 8px;
            color: #c9d1d9;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .contact-link:hover {
            border-color: #58a6ff;
            background: rgba(88, 166, 255, 0.1);
            transform: translateY(-2px);
        }

        .quote {
            font-style: italic;
            color: #7c3aed;
            text-align: center;
            margin: 30px 0;
            padding: 20px;
            background: rgba(124, 58, 237, 0.1);
            border-left: 4px solid #7c3aed;
            border-radius: 4px;
        }

        .node {
            position: absolute;
            width: 4px;
            height: 4px;
            background: #58a6ff;
            border-radius: 50%;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.3; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.5); }
        }

        .connection {
            position: absolute;
            height: 1px;
            background: linear-gradient(90deg, transparent, #58a6ff, transparent);
            animation: flow 3s linear infinite;
        }

        @keyframes flow {
            0% { opacity: 0; }
            50% { opacity: 0.6; }
            100% { opacity: 0; }
        }

        @media (max-width: 768px) {
            .name { font-size: 2rem; }
            .profile-card { padding: 20px; margin: 10px; }
            .info-grid { grid-template-columns: 1fr; gap: 20px; }
            .contact-links { flex-direction: column; align-items: center; }
        }
    </style>
</head>
<body>
    <div class="neural-network" id="neuralNetwork"></div>
    
    <div class="container">
        <div class="profile-card">
            <div class="header">
                <h1 class="name">Edii Lou Patty</h1>
                <div class="title">👋 Neural Network Developer</div>
                <div class="typing-container">
                    <span class="typing-text" id="typingText"></span>
                    <span class="cursor"></span>
                </div>
            </div>

            <div class="info-grid">
                <div class="info-section">
                    <div class="section-title">Languages</div>
                    <div class="tech-list">
                        <span class="tech-item">JavaScript</span>
                        <span class="tech-item">Python</span>
                        <span class="tech-item">PHP</span>
                        <span class="tech-item">GDScript</span>
                        <span class="tech-item">HTML5</span>
                        <span class="tech-item">C++</span>
                    </div>
                </div>

                <div class="info-section">
                    <div class="section-title">Frameworks</div>
                    <div class="tech-list">
                        <span class="tech-item">React</span>
                        <span class="tech-item">Express.js</span>
                        <span class="tech-item">Prisma</span>
                        <span class="tech-item">OpenCV</span>
                    </div>
                </div>

                <div class="info-section">
                    <div class="section-title">Database</div>
                    <div class="tech-list">
                        <span class="tech-item">MySQL</span>
                        <span class="tech-item">MongoDB</span>
                    </div>
                </div>

                <div class="info-section">
                    <div class="section-title">Hardware & IoT</div>
                    <div class="tech-list">
                        <span class="tech-item">Arduino</span>
                        <span class="tech-item">NodeMCU</span>
                        <span class="tech-item">ESP32</span>
                    </div>
                </div>
            </div>

            <div class="stats-container">
                <div class="stat-item">
                    <div class="stat-number" id="projects">0</div>
                    <div class="stat-label">Projects</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number" id="commits">0</div>
                    <div class="stat-label">Commits</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number" id="experience">0</div>
                    <div class="stat-label">Years Experience</div>
                </div>
            </div>

            <div class="quote">
                "github cuma 1 ya gez ya" - Sometimes simple is better! 😄
            </div>

            <div class="contact-section">
                <div class="contact-links">
                    <a href="https://github.com/ediiloupatty" class="contact-link">
                        <span>🐙</span> GitHub
                    </a>
                    <a href="mailto:ediloupatty@gmail.com" class="contact-link">
                        <span>📧</span> Email
                    </a>
                </div>
                <p><strong>Thanks for visiting! Let's build something awesome together! 🚀</strong></p>
                <p><em>I may be slow to respond, but every great project takes time to perfect! ⏰</em></p>
            </div>
        </div>
    </div>

    <script>
        // Typing animation
        const texts = [
            'Full Stack Developer',
            'Game Developer', 
            'Hardware Enthusiast',
            'IoT Developer',
            'Always Learning New Things'
        ];
        
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typingText');

        function typeText() {
            const currentText = texts[textIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentText.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentText.substring(0, charIndex + 1);
                charIndex++;
            }

            if (!isDeleting && charIndex === currentText.length) {
                setTimeout(() => isDeleting = true, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % texts.length;
            }

            const speed = isDeleting ? 50 : 100;
            setTimeout(typeText, speed);
        }

        // Neural network animation
        function createNeuralNetwork() {
            const canvas = document.getElementById('neuralNetwork');
            const nodes = [];
            const connections = [];
            
            // Create nodes
            for (let i = 0; i < 50; i++) {
                const node = document.createElement('div');
                node.className = 'node';
                node.style.left = Math.random() * window.innerWidth + 'px';
                node.style.top = Math.random() * window.innerHeight + 'px';
                node.style.animationDelay = Math.random() * 2 + 's';
                canvas.appendChild(node);
                nodes.push({
                    element: node,
                    x: parseFloat(node.style.left),
                    y: parseFloat(node.style.top)
                });
            }

            // Create connections
            for (let i = 0; i < nodes.length; i++) {
                for (let j = i + 1; j < nodes.length; j++) {
                    const distance = Math.sqrt(
                        Math.pow(nodes[i].x - nodes[j].x, 2) + 
                        Math.pow(nodes[i].y - nodes[j].y, 2)
                    );
                    
                    if (distance < 150) {
                        const connection = document.createElement('div');
                        connection.className = 'connection';
                        
                        const angle = Math.atan2(nodes[j].y - nodes[i].y, nodes[j].x - nodes[i].x);
                        connection.style.width = distance + 'px';
                        connection.style.left = nodes[i].x + 'px';
                        connection.style.top = nodes[i].y + 'px';
                        connection.style.transform = `rotate(${angle}rad)`;
                        connection.style.animationDelay = Math.random() * 3 + 's';
                        
                        canvas.appendChild(connection);
                    }
                }
            }
        }

        // Animate numbers
        function animateNumber(element, target, duration = 2000) {
            let start = 0;
            const increment = target / (duration / 16);
            
            function updateNumber() {
                start += increment;
                if (start < target) {
                    element.textContent = Math.floor(start);
                    requestAnimationFrame(updateNumber);
                } else {
                    element.textContent = target;
                }
            }
            updateNumber();
        }

        // Initialize
        window.addEventListener('load', () => {
            typeText();
            createNeuralNetwork();
            
            setTimeout(() => {
                animateNumber(document.getElementById('projects'), 15);
                animateNumber(document.getElementById('commits'), 1250);
                animateNumber(document.getElementById('experience'), 3);
            }, 1000);
        });

        // Resize handler
        window.addEventListener('resize', () => {
            document.getElementById('neuralNetwork').innerHTML = '';
            createNeuralNetwork();
        });
    </script>
</body>
</html>
