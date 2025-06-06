<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mahesh Savant - Developer Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .hero-section {
            text-align: center;
            padding: 60px 0;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            margin-bottom: 40px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            position: relative;
            overflow: hidden;
        }

        .hero-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        .profile-image {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 30px;
            animation: pulse 2s infinite;
            font-size: 60px;
            color: white;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .hero-title {
            font-size: 3rem;
            color: white;
            margin-bottom: 10px;
            animation: fadeInUp 1s ease-out;
        }

        .hero-subtitle {
            font-size: 1.2rem;
            color: rgba(255, 255, 255, 0.8);
            margin-bottom: 30px;
            animation: fadeInUp 1s ease-out 0.2s both;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            animation: fadeInUp 1s ease-out;
        }

        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: #ff6b6b;
            margin-bottom: 10px;
            animation: countUp 2s ease-out;
        }

        .stat-label {
            color: white;
            font-size: 1.1rem;
        }

        .skills-section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 40px;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .section-title {
            font-size: 2.5rem;
            color: white;
            text-align: center;
            margin-bottom: 40px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            border-radius: 2px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 20px;
        }

        .skill-item {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            transition: transform 0.3s ease;
            animation: fadeInUp 1s ease-out;
        }

        .skill-item:hover {
            transform: translateY(-5px) scale(1.05);
        }

        .skill-icon {
            width: 50px;
            height: 50px;
            margin: 0 auto 15px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            color: white;
        }

        .skill-name {
            color: white;
            font-weight: 600;
            margin-bottom: 10px;
        }

        .skill-level {
            height: 6px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 3px;
            overflow: hidden;
        }

        .skill-progress {
            height: 100%;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            border-radius: 3px;
            animation: progressFill 2s ease-out;
        }

        .contact-section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }

        .social-link {
            width: 60px;
            height: 60px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 24px;
            text-decoration: none;
            transition: transform 0.3s ease, background 0.3s ease;
            animation: bounce 2s infinite;
        }

        .social-link:hover {
            transform: scale(1.2);
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
        }

        .floating-particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: rgba(255, 255, 255, 0.6);
            border-radius: 50%;
            animation: float 6s infinite ease-in-out;
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

        @keyframes countUp {
            from { opacity: 0; transform: scale(0.5); }
            to { opacity: 1; transform: scale(1); }
        }

        @keyframes progressFill {
            from { width: 0%; }
            to { width: var(--progress); }
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .typing-text {
            overflow: hidden;
            border-right: 2px solid #ff6b6b;
            white-space: nowrap;
            animation: typing 3s steps(40, end), blink 0.75s step-end infinite;
        }

        @keyframes typing {
            from { width: 0; }
            to { width: 100%; }
        }

        @keyframes blink {
            from, to { border-color: transparent; }
            50% { border-color: #ff6b6b; }
        }

        .chart-container {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 40px;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .progress-ring {
            width: 120px;
            height: 120px;
            margin: 0 auto;
        }

        .progress-ring__circle {
            transition: stroke-dashoffset 0.35s;
            transform: rotate(-90deg);
            transform-origin: 50% 50%;
        }

        @media (max-width: 768px) {
            .hero-title { font-size: 2rem; }
            .stats-grid { grid-template-columns: 1fr; }
            .skills-grid { grid-template-columns: repeat(auto-fit, minmax(100px, 1fr)); }
        }
    </style>
</head>
<body>
    <div class="floating-particles" id="particles"></div>
    
    <div class="container">
        <!-- Hero Section -->
        <div class="hero-section">
            <div class="profile-image">👨‍💻</div>
            <h1 class="hero-title">Hi 👋, I'm Mahesh Savant</h1>
            <p class="hero-subtitle typing-text">Debugging the Future: Portrait of a Dedicated Software Engineer</p>
        </div>

        <!-- Stats Grid -->
        <div class="stats-grid">
            <div class="stat-card">
                <div class="stat-number">50+</div>
                <div class="stat-label">Projects Completed</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">3+</div>
                <div class="stat-label">Years Experience</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">15+</div>
                <div class="stat-label">Technologies Mastered</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">1000+</div>
                <div class="stat-label">Profile Views</div>
            </div>
        </div>

        <!-- Skills Section -->
        <div class="skills-section">
            <h2 class="section-title">Technical Skills</h2>
            <div class="skills-grid">
                <div class="skill-item">
                    <div class="skill-icon">⚛️</div>
                    <div class="skill-name">React</div>
                    <div class="skill-level">
                        <div class="skill-progress" style="--progress: 90%; width: 90%;"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">🟢</div>
                    <div class="skill-name">Node.js</div>
                    <div class="skill-level">
                        <div class="skill-progress" style="--progress: 85%; width: 85%;"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">🐍</div>
                    <div class="skill-name">Python</div>
                    <div class="skill-level">
                        <div class="skill-progress" style="--progress: 80%; width: 80%;"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">☕</div>
                    <div class="skill-name">Java</div>
                    <div class="skill-level">
                        <div class="skill-progress" style="--progress: 75%; width: 75%;"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">🍃</div>
                    <div class="skill-name">MongoDB</div>
                    <div class="skill-level">
                        <div class="skill-progress" style="--progress: 70%; width: 70%;"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">🎨</div>
                    <div class="skill-name">CSS/HTML</div>
                    <div class="skill-level">
                        <div class="skill-progress" style="--progress: 95%; width: 95%;"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">🤖</div>
                    <div class="skill-name">Machine Learning</div>
                    <div class="skill-level">
                        <div class="skill-progress" style="--progress: 65%; width: 65%;"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">🔥</div>
                    <div class="skill-name">Tailwind CSS</div>
                    <div class="skill-level">
                        <div class="skill-progress" style="--progress: 85%; width: 85%;"></div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Current Focus -->
        <div class="chart-container">
            <h2 class="section-title">Current Focus</h2>
            <div style="text-align: center; color: white;">
                <div style="display: flex; justify-content: space-around; flex-wrap: wrap; gap: 20px;">
                    <div style="flex: 1; min-width: 200px;">
                        <h3 style="margin-bottom: 15px;">🔭 Currently Working On</h3>
                        <p style="background: rgba(255,255,255,0.1); padding: 15px; border-radius: 10px;">
                            Machine Learning Projects & Advanced Algorithms
                        </p>
                    </div>
                    <div style="flex: 1; min-width: 200px;">
                        <h3 style="margin-bottom: 15px;">🌱 Currently Learning</h3>
                        <p style="background: rgba(255,255,255,0.1); padding: 15px; border-radius: 10px;">
                            Fullstack Development & Salesforce Development
                        </p>
                    </div>
                    <div style="flex: 1; min-width: 200px;">
                        <h3 style="margin-bottom: 15px;">💬 Ask Me About</h3>
                        <p style="background: rgba(255,255,255,0.1); padding: 15px; border-radius: 10px;">
                            MERN Stack & Machine Learning
                        </p>
                    </div>
                </div>
            </div>
        </div>

        <!-- Contact Section -->
        <div class="contact-section">
            <h2 class="section-title">Let's Connect</h2>
            <p style="color: white; font-size: 1.1rem; margin-bottom: 10px;">
                📫 Reach me at: <strong>smahesh7741@gmail.com</strong>
            </p>
            <p style="color: rgba(255,255,255,0.8); margin-bottom: 20px;">
                ⚡ Fun fact: I am funny 😄
            </p>
            
            <div class="social-links">
                <a href="https://linkedin.com/in/mahesh-savant-66699923b" class="social-link" target="_blank">
                    💼
                </a>
                <a href="https://github.com/Mahesh7741" class="social-link" target="_blank">
                    🐙
                </a>
                <a href="https://instagram.com/mr_mahesh_savant" class="social-link" target="_blank">
                    📸
                </a>
                <a href="https://leetcode.com/maheshsavant" class="social-link" target="_blank">
                    🧩
                </a>
                <a href="https://auth.geeksforgeeks.org/user/mahesh_savant" class="social-link" target="_blank">
                    🤓
                </a>
            </div>
        </div>
    </div>

    <script>
        // Create floating particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 50;

            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (Math.random() * 3 + 3) + 's';
                particlesContainer.appendChild(particle);
            }
        }

        // Animate numbers counting up
        function animateNumbers() {
            const numbers = document.querySelectorAll('.stat-number');
            numbers.forEach(number => {
                const target = parseInt(number.textContent.replace(/\D/g, ''));
                const suffix = number.textContent.replace(/\d/g, '');
                let current = 0;
                const increment = target / 50;
                const timer = setInterval(() => {
                    current += increment;
                    if (current >= target) {
                        current = target;
                        clearInterval(timer);
                    }
                    number.textContent = Math.floor(current) + suffix;
                }, 40);
            });
        }

        // Add hover effects to skill items
        function addHoverEffects() {
            const skillItems = document.querySelectorAll('.skill-item');
            skillItems.forEach(item => {
                item.addEventListener('mouseenter', () => {
                    const progress = item.querySelector('.skill-progress');
                    progress.style.animationPlayState = 'running';
                });
            });
        }

        // Initialize everything when page loads
        document.addEventListener('DOMContentLoaded', () => {
            createParticles();
            setTimeout(animateNumbers, 1000);
            addHoverEffects();
        });

        // Add parallax effect to hero section
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const hero = document.querySelector('.hero-section');
            hero.style.transform = `translateY(${scrolled * 0.5}px)`;
        });
    </script>
</body>
</html>
