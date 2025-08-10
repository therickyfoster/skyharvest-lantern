<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SkyHarvest Lantern™ - Revolutionary Solar-Bio Lighting</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #00ff88;
            --secondary: #ff6b35;
            --accent: #ffd23f;
            --dark: #0a0a0a;
            --card: #1a1a2e;
            --glass: rgba(26, 26, 46, 0.8);
            --gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --neon: 0 0 20px var(--primary), 0 0 40px var(--primary);
        }

        body {
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
            background: linear-gradient(45deg, #0a0a0a, #1a1a2e, #16213e);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            color: white;
            overflow-x: hidden;
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        /* Floating particles effect */
        .particles {
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
            width: 3px;
            height: 3px;
            background: var(--primary);
            border-radius: 50%;
            animation: float 6s infinite ease-in-out;
            opacity: 0.6;
        }

        @keyframes float {
            0%, 100% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
        }

        /* Header with glassmorphism */
        .header {
            position: fixed;
            top: 0;
            width: 100%;
            backdrop-filter: blur(15px);
            background: var(--glass);
            border-bottom: 1px solid rgba(0, 255, 136, 0.2);
            z-index: 1000;
            padding: 1rem 0;
            transition: all 0.3s ease;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--primary);
            text-shadow: var(--neon);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo::before {
            content: "💡";
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.2); }
        }

        .nav-menu {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-item {
            cursor: pointer;
            padding: 0.5rem 1rem;
            border-radius: 25px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .nav-item:hover {
            background: rgba(0, 255, 136, 0.1);
            box-shadow: var(--neon);
            transform: translateY(-2px);
        }

        /* Hero section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            padding: 2rem;
            margin-top: 80px;
        }

        .hero-content {
            max-width: 800px;
            animation: slideInUp 1s ease;
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-size: clamp(2.5rem, 8vw, 5rem);
            margin-bottom: 1rem;
            background: linear-gradient(45deg, var(--primary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: none;
        }

        .hero-subtitle {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .cta-button {
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            border: none;
            padding: 1rem 2rem;
            font-size: 1.1rem;
            border-radius: 50px;
            color: white;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            margin: 0.5rem;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 255, 136, 0.3);
        }

        .cta-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }

        .cta-button:hover::before {
            left: 100%;
        }

        /* Feature cards with 3D effect */
        .features-section {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 3rem;
            color: var(--primary);
            text-shadow: var(--neon);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .feature-card {
            background: var(--glass);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 2rem;
            border: 1px solid rgba(0, 255, 136, 0.2);
            transition: all 0.4s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .feature-card:hover {
            transform: translateY(-10px) rotateX(5deg);
            box-shadow: 0 20px 40px rgba(0, 255, 136, 0.3);
            border-color: var(--primary);
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            display: block;
            transition: all 0.3s ease;
        }

        .feature-card:hover .feature-icon {
            transform: scale(1.2) rotate(10deg);
        }

        .progress-section {
            background: var(--glass);
            backdrop-filter: blur(15px);
            margin: 3rem 0;
            padding: 3rem;
            border-radius: 25px;
            border: 1px solid rgba(0, 255, 136, 0.2);
        }

        /* Gamification elements */
        .achievement-badge {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: linear-gradient(45deg, var(--accent), var(--secondary));
            padding: 0.5rem 1rem;
            border-radius: 25px;
            font-size: 0.9rem;
            margin: 0.25rem;
            animation: badgeGlow 3s infinite alternate;
        }

        @keyframes badgeGlow {
            0% { box-shadow: 0 0 10px rgba(255, 210, 63, 0.5); }
            100% { box-shadow: 0 0 20px rgba(255, 210, 63, 0.8); }
        }

        .progress-bar {
            width: 100%;
            height: 10px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 5px;
            overflow: hidden;
            margin: 1rem 0;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            border-radius: 5px;
            animation: progressAnimation 2s ease;
            position: relative;
        }

        @keyframes progressAnimation {
            from { width: 0%; }
        }

        .progress-fill::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            height: 100%;
            width: 20px;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.6), transparent);
            animation: shimmer 2s infinite;
        }

        @keyframes shimmer {
            0% { transform: translateX(-20px); }
            100% { transform: translateX(200px); }
        }

        /* Interactive elements */
        .interactive-demo {
            background: var(--glass);
            backdrop-filter: blur(15px);
            border-radius: 25px;
            padding: 3rem;
            margin: 3rem 0;
            text-align: center;
            border: 1px solid rgba(0, 255, 136, 0.2);
        }

        .demo-lantern {
            width: 200px;
            height: 300px;
            margin: 2rem auto;
            background: linear-gradient(180deg, #333, #555);
            border-radius: 15px;
            position: relative;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .demo-lantern:hover {
            transform: scale(1.05);
            box-shadow: var(--neon);
        }

        .demo-lantern.active {
            animation: lanternGlow 2s infinite alternate;
        }

        @keyframes lanternGlow {
            0% { box-shadow: 0 0 20px var(--primary); }
            100% { box-shadow: 0 0 40px var(--primary), 0 0 60px var(--accent); }
        }

        .lantern-light {
            position: absolute;
            top: 30%;
            left: 50%;
            transform: translateX(-50%);
            width: 80%;
            height: 40%;
            background: radial-gradient(circle, var(--accent), transparent);
            border-radius: 50%;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .demo-lantern.active .lantern-light {
            opacity: 0.8;
        }

        /* Contact section with modern styling */
        .contact-section {
            background: var(--glass);
            backdrop-filter: blur(15px);
            padding: 3rem;
            margin: 3rem 0;
            border-radius: 25px;
            border: 1px solid rgba(0, 255, 136, 0.2);
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .contact-item {
            text-align: center;
            padding: 1.5rem;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .contact-item:hover {
            background: rgba(0, 255, 136, 0.1);
            transform: translateY(-5px);
        }

        /* Scroll indicators */
        .scroll-indicator {
            position: fixed;
            top: 0;
            left: 0;
            height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            z-index: 1001;
            transition: width 0.3s ease;
        }

        /* Mobile responsiveness */
        @media (max-width: 768px) {
            .nav-menu {
                flex-direction: column;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background: var(--glass);
                backdrop-filter: blur(15px);
                padding: 1rem 0;
                transform: translateY(-100%);
                opacity: 0;
                transition: all 0.3s ease;
            }

            .nav-menu.active {
                transform: translateY(0);
                opacity: 1;
            }

            .hero h1 {
                font-size: 2.5rem;
            }
            
            .features-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Additional fun animations */
        .bounce {
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-30px); }
            60% { transform: translateY(-15px); }
        }

        .rotate {
            animation: rotate 10s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        /* Easter egg - konami code effect */
        .konami-active {
            animation: rainbow 1s infinite;
        }

        @keyframes rainbow {
            0% { filter: hue-rotate(0deg); }
            100% { filter: hue-rotate(360deg); }
        }
    </style>
</head>
<body>
    <!-- Floating particles -->
    <div class="particles" id="particles"></div>
    
    <!-- Scroll progress indicator -->
    <div class="scroll-indicator" id="scrollIndicator"></div>

    <!-- Header -->
    <header class="header">
        <nav class="nav-container">
            <div class="logo">SkyHarvest Lantern™</div>
            <ul class="nav-menu">
                <li class="nav-item" onclick="scrollToSection('hero')">🏠 Home</li>
                <li class="nav-item" onclick="scrollToSection('features')">⭐ Features</li>
                <li class="nav-item" onclick="scrollToSection('demo')">🎮 Demo</li>
                <li class="nav-item" onclick="scrollToSection('roadmap')">🗺️ Roadmap</li>
                <li class="nav-item" onclick="scrollToSection('contact')">📞 Contact</li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="hero">
        <div class="hero-content">
            <h1 class="bounce">SkyHarvest Lantern™</h1>
            <p class="hero-subtitle">🌱 Solar-Powered • 🌿 Air-Purifying • ✨ Bioluminescent Backup</p>
            
            <div class="achievement-badge">
                <span>🏆</span> Patent Pending Innovation
            </div>
            <div class="achievement-badge">
                <span>🌍</span> Eco-Friendly Design
            </div>
            <div class="achievement-badge">
                <span>⚡</span> Zero-Waste Technology
            </div>
            
            <div style="margin-top: 2rem;">
                <button class="cta-button" onclick="activateDemo()">
                    🚀 Launch Interactive Demo
                </button>
                <button class="cta-button" onclick="showSpecs()">
                    📊 View Tech Specs
                </button>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features-section" id="features">
        <h2 class="section-title">🔥 Revolutionary Features</h2>
        
        <div class="features-grid">
            <div class="feature-card" onclick="animateCard(this)">
                <span class="feature-icon">☀️</span>
                <h3>Solar-Powered LED</h3>
                <p>High-efficiency solar charging provides 8-12 hours of brilliant illumination per charge</p>
                <div class="progress-bar">
                    <div class="progress-fill" style="width: 95%;"></div>
                </div>
                <small>95% Energy Efficiency</small>
            </div>

            <div class="feature-card" onclick="animateCard(this)">
                <span class="feature-icon">🌿</span>
                <h3>Air Purification Core</h3>
                <p>Mycelium-carbon filter removes VOCs, particulates, and CO₂ from your environment</p>
                <div class="progress-bar">
                    <div class="progress-fill" style="width: 87%;"></div>
                </div>
                <small>87% Pollutant Removal Rate</small>
            </div>

            <div class="feature-card" onclick="animateCard(this)">
                <span class="feature-icon">✨</span>
                <h3>Bio-Luminescent Backup</h3>
                <p>Natural glow that runs indefinitely without any battery or electricity needed</p>
                <div class="progress-bar">
                    <div class="progress-fill" style="width: 100%;"></div>
                </div>
                <small>∞ Infinite Runtime</small>
            </div>

            <div class="feature-card" onclick="animateCard(this)">
                <span class="feature-icon">🛡️</span>
                <h3>Ultra-Durable Design</h3>
                <p>Weather-resistant construction from recycled materials and sustainable bamboo</p>
                <div class="progress-bar">
                    <div class="progress-fill" style="width: 92%;"></div>
                </div>
                <small>92% Sustainability Score</small>
            </div>
        </div>

        <div class="progress-section">
            <h3>🎯 Development Progress</h3>
            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 2rem; margin-top: 2rem;">
                <div>
                    <p>🧪 R&D Phase</p>
                    <div class="progress-bar">
                        <div class="progress-fill" style="width: 85%;"></div>
                    </div>
                    <small>85% Complete</small>
                </div>
                <div>
                    <p>🏭 Manufacturing Setup</p>
                    <div class="progress-bar">
                        <div class="progress-fill" style="width: 60%;"></div>
                    </div>
                    <small>60% Complete</small>
                </div>
                <div>
                    <p>📱 Market Launch</p>
                    <div class="progress-bar">
                        <div class="progress-fill" style="width: 30%;"></div>
                    </div>
                    <small>30% Complete</small>
                </div>
            </div>
        </div>
    </section>

    <!-- Interactive Demo -->
    <section class="interactive-demo" id="demo">
        <h2 class="section-title">🎮 Interactive Demo</h2>
        <p>Click the lantern to experience different modes!</p>
        
        <div class="demo-lantern" id="demoLantern" onclick="cycleLanternMode()">
            <div class="lantern-light"></div>
            <div style="position: absolute; top: 10px; left: 50%; transform: translateX(-50%); font-size: 0.8rem;">
                <span id="modeDisplay">☀️ Solar Mode</span>
            </div>
        </div>
        
        <div style="margin-top: 2rem;">
            <div class="achievement-badge">
                <span>🏅</span> Demo Expert
            </div>
            <p id="demoCounter" style="margin-top: 1rem;">Interactions: 0 🎯</p>
        </div>
    </section>

    <!-- Roadmap Section -->
    <section class="features-section" id="roadmap">
        <h2 class="section-title">🗺️ Innovation Roadmap</h2>
        
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem;">
            <div class="feature-card">
                <span class="feature-icon rotate">⚗️</span>
                <h3>Phase 1 - Q3 2025</h3>
                <p>🧪 Complete bioluminescent testing<br>
                🏭 Begin pilot production<br>
                📊 Efficiency optimization</p>
                <div class="achievement-badge">
                    <span>🎯</span> 85% Complete
                </div>
            </div>

            <div class="feature-card">
                <span class="feature-icon">🚀</span>
                <h3>Phase 2 - Q4 2025</h3>
                <p>💰 Kickstarter launch<br>
                🏪 Retail partnerships<br>
                📦 Scale production</p>
                <div class="achievement-badge">
                    <span>⏳</span> Coming Soon
                </div>
            </div>

            <div class="feature-card">
                <span class="feature-icon">🌟</span>
                <h3>Phase 3 - 2026</h3>
                <p>🏙️ Large-scale air hubs<br>
                📱 IoT integration<br>
                🌐 Global expansion</p>
                <div class="achievement-badge">
                    <span>🔮</span> Future Vision
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact-section" id="contact">
        <h2 class="section-title">🤝 Connect & Contribute</h2>
        <p style="text-align: center; font-size: 1.2rem; margin-bottom: 2rem;">
            <em>"The truth is not what I say. It's what I've already done."</em> – Ricky Foster
        </p>
        
        <div class="contact-grid">
            <div class="contact-item" onclick="window.open('https://github.com/TheRickyFoster', '_blank')">
                <span style="font-size: 2rem;">💻</span>
                <h3>GitHub</h3>
                <p>TheRickyFoster</p>
            </div>
            
            <div class="contact-item" onclick="window.open('mailto:therickyfoster@outlook.com', '_blank')">
                <span style="font-size: 2rem;">📧</span>
                <h3>Email</h3>
                <p>therickyfoster@outlook.com</p>
            </div>
            
            <div class="contact-item">
                <span style="font-size: 2rem;">₿</span>
                <h3>Crypto Support</h3>
                <p>ETH • SOL • BTC</p>
                <small style="opacity: 0.7;">Click cards for addresses</small>
            </div>
            
            <div class="contact-item">
                <span style="font-size: 2rem;">📜</span>
                <h3>Legal</h3>
                <p>Patent Pending<br>LCGTL-1.0 Licensed</p>
            </div>
        </div>
        
        <div style="text-align: center; margin-top: 3rem;">
            <div class="achievement-badge">
                <span>🌱</span> Sustainable Innovation
            </div>
            <div class="achievement-badge">
                <span>🔬</span> Science-Backed
            </div>
            <div class="achievement-badge">
                <span>💚</span> Humanitarian Friendly
            </div>
        </div>
    </section>

    <script>
        // Particle system
        function createParticles() {
            const particleContainer = document.getElementById('particles');
            for (let i = 0; i < 50; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + 'vw';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (Math.random() * 3 + 3) + 's';
                particleContainer.appendChild(particle);
            }
        }

        // Scroll progress indicator
        function updateScrollIndicator() {
            const scrollTop = window.pageYOffset;
            const docHeight = document.body.offsetHeight - window.innerHeight;
            const scrollPercent = (scrollTop / docHeight) * 100;
            document.getElementById('scrollIndicator').style.width = scrollPercent + '%';
        }

        // Smooth scrolling to sections
        function scrollToSection(sectionId) {
            const element = document.getElementById(sectionId);
            element.scrollIntoView({ behavior: 'smooth' });
        }

        // Demo lantern functionality
        let lanternModes = [
            { mode: '☀️ Solar Mode', color: '#ffd23f' },
            { mode: '🌿 Air Purifier', color: '#00ff88' },
            { mode: '✨ Bio-Glow', color: '#ff6b35' },
            { mode: '🛡️ Emergency', color: '#ff4757' }
        ];
        let currentMode = 0;
        let demoClicks = 0;

        function cycleLanternMode() {
            const lantern = document.getElementById('demoLantern');
            const modeDisplay = document.getElementById('modeDisplay');
            const counter = document.getElementById('demoCounter');
            
            currentMode = (currentMode + 1) % lanternModes.length;
            demoClicks++;
            
            lantern.classList.add('active');
            modeDisplay.textContent = lanternModes[currentMode].mode;
            counter.textContent = `Interactions: ${demoClicks} 🎯`;
            
            // Add achievement for milestones
            if (demoClicks === 10) {
                showAchievement('🏆 Demo Master Unlocked!');
            } else if (demoClicks === 25) {
                showAchievement('🌟 Innovation Explorer!');
            }
            
            setTimeout(() => lantern.classList.remove('active'), 2000);
        }

        function activateDemo() {
            document.getElementById('demo').scrollIntoView({ behavior: 'smooth' });
            setTimeout(() => {
                cycleLanternMode();
                showAchievement('🚀 Demo Activated!');
            }, 1000);
        }

        function showSpecs() {
            const specs = `
🔋 Battery: 5000mAh Li-ion
☀️ Solar Panel: 10W monocrystalline
💡 LED Output: 800 lumens max
🌿 Filter Life: 6-12 months
⚡ Charge Time: 6-8 hours
🏃 Runtime: 8-12 hours
🌡️ Temperature: -20°C to 50°C
💧 Rating: IP65 weather resistant
📏 Dimensions: 15cm × 25cm
⚖️ Weight: 850g
            `;
            alert('📊 SkyHarvest Lantern™ Specifications:\n' + specs);
            showAchievement('🤓 Tech Specs Viewed!');
        }

        // Feature card animation
        function animateCard(card) {
            card.style.transform = 'scale(1.05) rotateY(10deg)';
            setTimeout(() => {
                card.style.transform = 'translateY(-10px) rotateX(5deg)';
            }, 200);
            showAchievement('⭐ Feature Explored!');
        }

        // Achievement system
        function showAchievement(text) {
            const achievement = document.createElement('div');
            achievement.style.cssText = `
                position: fixed;
                top: 20px;
                right: 20px;
                background: linear-gradient(45deg, #ffd23f, #ff6b35);
                color: white;
                padding: 1rem 1.5rem;
                border-radius: 10px;
                font-weight: bold;
                z-index: 2000;
                animation: slideInRight 0.5s ease, fadeOut 0.5s ease 2.5s forwards;
                box-shadow: 0 10px 25px rgba(255, 210, 63, 0.3);
            `;
            achievement.textContent = text;
            document.body.appendChild(achievement);
            
            setTimeout(() => achievement.remove(), 3000);
        }

        // Konami code easter egg
        let konamiCode = [];
        const konamiSequence = ['ArrowUp', 'ArrowUp', 'ArrowDown', 'ArrowDown', 'ArrowLeft', 'ArrowRight', 'ArrowLeft', 'ArrowRight', 'KeyB', 'KeyA'];

        function handleKonamiCode(event) {
            konamiCode.push(event.code);
            if (konamiCode.length > konamiSequence.length) {
                konamiCode.shift();
            }
            
            if (JSON.stringify(konamiCode) === JSON.stringify(konamiSequence)) {
                document.body.classList.add('konami-active');
                showAchievement('🎮 Konami Code Activated! Rainbow Mode!');
                setTimeout(() => document.body.classList.remove('konami-active'), 5000);
            }
        }

        // Advanced interactions
        function addClickEffects() {
            document.addEventListener('click', function(e) {
                // Create ripple effect
                const ripple = document.createElement('div');
                ripple.style.cssText = `
                    position: fixed;
                    border-radius: 50%;
                    background: radial-gradient(circle, var(--primary), transparent);
                    pointer-events: none;
                    z-index: 9999;
                    animation: rippleEffect 0.6s ease-out;
                    left: ${e.clientX - 25}px;
                    top: ${e.clientY - 25}px;
                    width: 50px;
                    height: 50px;
                `;
                document.body.appendChild(ripple);
                setTimeout(() => ripple.remove(), 600);
            });
        }

        // Add CSS for ripple effect
        const rippleCSS = `
            @keyframes rippleEffect {
                0% {
                    transform: scale(0);
                    opacity: 1;
                }
                100% {
                    transform: scale(4);
                    opacity: 0;
                }
            }
            
            @keyframes slideInRight {
                from {
                    transform: translateX(100%);
                    opacity: 0;
                }
                to {
                    transform: translateX(0);
                    opacity: 1;
                }
            }
            
            @keyframes fadeOut {
                to {
                    opacity: 0;
                    transform: translateX(100%);
                }
            }
        `;
        
        const style = document.createElement('style');
        style.textContent = rippleCSS;
        document.head.appendChild(style);

        // Crypto address display system
        function showCryptoAddress(type) {
            const addresses = {
                eth: '0xCeA929dee554652261fd6261F3034A2D71C7BDDb',
                sol: 'HfGCVthQ4Wp4CAYd4v7gJX53h6X3mdreUocjrhByPXQx',
                btc: 'bc1q6fyvqxm7jryy5edckk9nuu6mgyjlz4nnp8nksr'
            };
            
            const modal = document.createElement('div');
            modal.style.cssText = `
                position: fixed;
                top: 0;
                left: 0;
                width: 100%;
                height: 100%;
                background: rgba(0, 0, 0, 0.8);
                display: flex;
                align-items: center;
                justify-content: center;
                z-index: 3000;
                backdrop-filter: blur(5px);
            `;
            
            modal.innerHTML = `
                <div style="
                    background: var(--glass);
                    backdrop-filter: blur(15px);
                    padding: 2rem;
                    border-radius: 20px;
                    border: 1px solid var(--primary);
                    max-width: 500px;
                    text-align: center;
                    box-shadow: var(--neon);
                ">
                    <h3>💰 Crypto Addresses</h3>
                    <div style="margin: 1rem 0; font-family: monospace; font-size: 0.9rem;">
                        <p><strong>ETH:</strong><br>${addresses.eth}</p>
                        <p><strong>SOL:</strong><br>${addresses.sol}</p>
                        <p><strong>BTC:</strong><br>${addresses.btc}</p>
                    </div>
                    <button onclick="this.parentElement.parentElement.remove()" class="cta-button">
                        ✅ Got it!
                    </button>
                </div>
            `;
            
            document.body.appendChild(modal);
            showAchievement('💎 Crypto Support Info!');
        }

        // Performance monitoring and gamification
        let userStats = {
            timeSpent: 0,
            sectionsVisited: new Set(),
            interactionsCount: 0,
            achievements: []
        };

        function trackUserEngagement() {
            const startTime = Date.now();
            
            // Track sections in view
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        userStats.sectionsVisited.add(entry.target.id);
                        checkEngagementAchievements();
                    }
                });
            }, { threshold: 0.5 });

            document.querySelectorAll('section[id]').forEach(section => {
                observer.observe(section);
            });

            // Track time spent
            setInterval(() => {
                userStats.timeSpent = Date.now() - startTime;
                checkTimeAchievements();
            }, 1000);
        }

        function checkEngagementAchievements() {
            if (userStats.sectionsVisited.size >= 3 && !userStats.achievements.includes('explorer')) {
                userStats.achievements.push('explorer');
                showAchievement('🗺️ Section Explorer!');
            }
            
            if (userStats.sectionsVisited.size === document.querySelectorAll('section[id]').length && !userStats.achievements.includes('completionist')) {
                userStats.achievements.push('completionist');
                showAchievement('🏆 Completionist Unlocked!');
            }
        }

        function checkTimeAchievements() {
            const minutes = userStats.timeSpent / (1000 * 60);
            
            if (minutes >= 2 && !userStats.achievements.includes('engaged')) {
                userStats.achievements.push('engaged');
                showAchievement('⏰ Engaged Visitor!');
            }
            
            if (minutes >= 5 && !userStats.achievements.includes('dedicated')) {
                userStats.achievements.push('dedicated');
                showAchievement('💪 Dedicated Explorer!');
            }
        }

        // Enhanced mobile menu
        function createMobileMenu() {
            const menuToggle = document.createElement('div');
            menuToggle.style.cssText = `
                display: none;
                flex-direction: column;
                cursor: pointer;
                padding: 0.5rem;
                gap: 4px;
            `;
            
            for (let i = 0; i < 3; i++) {
                const line = document.createElement('div');
                line.style.cssText = `
                    width: 25px;
                    height: 3px;
                    background: var(--primary);
                    transition: all 0.3s ease;
                    border-radius: 2px;
                `;
                menuToggle.appendChild(line);
            }
            
            const nav = document.querySelector('.nav-container');
            nav.appendChild(menuToggle);
            
            // Mobile-specific CSS
            const mobileCSS = `
                @media (max-width: 768px) {
                    .nav-container div:last-child {
                        display: flex !important;
                    }
                    
                    .nav-menu {
                        display: none;
                    }
                    
                    .nav-menu.mobile-active {
                        display: flex;
                        flex-direction: column;
                        position: absolute;
                        top: 100%;
                        left: 0;
                        right: 0;
                        background: var(--glass);
                        backdrop-filter: blur(15px);
                        padding: 1rem;
                        border-top: 1px solid var(--primary);
                    }
                }
            `;
            
            const mobileStyle = document.createElement('style');
            mobileStyle.textContent = mobileCSS;
            document.head.appendChild(mobileStyle);
            
            menuToggle.addEventListener('click', () => {
                const menu = document.querySelector('.nav-menu');
                menu.classList.toggle('mobile-active');
            });
        }

        // Advanced visual effects
        function addParallaxEffect() {
            window.addEventListener('scroll', () => {
                const scrolled = window.pageYOffset;
                const parallaxElements = document.querySelectorAll('.feature-icon');
                
                parallaxElements.forEach((element, index) => {
                    const speed = 0.5 + (index * 0.1);
                    element.style.transform = `translateY(${scrolled * speed * 0.01}px) rotate(${scrolled * 0.05}deg)`;
                });
            });
        }

        // Matrix rain effect (easter egg)
        function createMatrixRain() {
            const canvas = document.createElement('canvas');
            canvas.style.cssText = `
                position: fixed;
                top: 0;
                left: 0;
                width: 100%;
                height: 100%;
                pointer-events: none;
                z-index: -1;
                opacity: 0.1;
            `;
            
            document.body.appendChild(canvas);
            
            const ctx = canvas.getContext('2d');
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
            
            const chars = '01⚡🌱💡✨🔋☀️';
            const charArray = chars.split('');
            const fontSize = 14;
            const columns = canvas.width / fontSize;
            const drops = [];
            
            for (let i = 0; i < columns; i++) {
                drops[i] = 1;
            }
            
            function drawMatrix() {
                ctx.fillStyle = 'rgba(0, 0, 0, 0.05)';
                ctx.fillRect(0, 0, canvas.width, canvas.height);
                
                ctx.fillStyle = '#00ff88';
                ctx.font = fontSize + 'px monospace';
                
                for (let i = 0; i < drops.length; i++) {
                    const text = charArray[Math.floor(Math.random() * charArray.length)];
                    ctx.fillText(text, i * fontSize, drops[i] * fontSize);
                    
                    if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                        drops[i] = 0;
                    }
                    drops[i]++;
                }
            }
            
            setInterval(drawMatrix, 100);
        }

        // Initialize everything
        document.addEventListener('DOMContentLoaded', function() {
            createParticles();
            addClickEffects();
            trackUserEngagement();
            createMobileMenu();
            addParallaxEffect();
            
            // Add scroll listener for progress indicator
            window.addEventListener('scroll', updateScrollIndicator);
            
            // Add konami code listener
            document.addEventListener('keydown', handleKonamiCode);
            
            // Add crypto address display to contact items
            document.querySelectorAll('.contact-item').forEach((item, index) => {
                if (index === 2) { // Crypto contact item
                    item.addEventListener('click', () => showCryptoAddress('all'));
                }
            });
            
            // Welcome achievement
            setTimeout(() => {
                showAchievement('🎉 Welcome to SkyHarvest!');
            }, 1000);
            
            // Activate matrix rain after 30 seconds for extra ambiance
            setTimeout(createMatrixRain, 30000);
        });

        // Voice of the creator easter egg
        function showCreatorMessage() {
            const messages = [
                "🚀 Innovation isn't just about the idea - it's about execution!",
                "🌱 Every breakthrough starts with believing the impossible is possible.",
                "⚡ The future belongs to those who solve tomorrow's problems today.",
                "🔬 Science fiction becomes science fact when you refuse to give up.",
                "🌍 Technology should heal the planet, not harm it."
            ];
            
            const randomMessage = messages[Math.floor(Math.random() * messages.length)];
            showAchievement(randomMessage);
        }

        // Add creator message trigger (triple click on logo)
        let logoClicks = 0;
        document.querySelector('.logo').addEventListener('click', () => {
            logoClicks++;
            if (logoClicks === 3) {
                showCreatorMessage();
                logoClicks = 0;
            }
            setTimeout(() => logoClicks = 0, 2000);
        });
    </script>
</body>
</html>
