<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CodeCaracal - Innovative IoT Solutions</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #FF6B35;
            --secondary: #004E89;
            --accent: #1A659E;
            --dark: #0A1128;
            --light: #F7F9FC;
            --gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --gradient-alt: linear-gradient(135deg, #ff6b35 0%, #f7931e 100%);
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--dark);
            overflow-x: hidden;
            background: var(--light);
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            opacity: 0.1;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Floating Particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: rgba(102, 126, 234, 0.6);
            border-radius: 50%;
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }

        /* Header Styles */
        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            padding: 2rem 0;
            text-align: center;
            position: relative;
            overflow: hidden;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
        }

        .logo {
            font-size: 3.5rem;
            font-weight: 900;
            background: var(--gradient-alt);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 0.5rem;
            animation: logoGlow 3s ease-in-out infinite alternate;
        }

        @keyframes logoGlow {
            from { filter: drop-shadow(0 0 20px rgba(255, 107, 53, 0.3)); }
            to { filter: drop-shadow(0 0 40px rgba(255, 107, 53, 0.6)); }
        }

        .tagline {
            font-size: 1.3rem;
            color: var(--secondary);
            font-weight: 300;
            margin-bottom: 2rem;
            opacity: 0;
            animation: slideUp 1s ease-out 0.5s forwards;
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Badge Container */
        .badges {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 1rem;
            margin: 2rem 0;
        }

        .badge {
            background: var(--gradient);
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 50px;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            transform: translateY(50px);
            opacity: 0;
            animation: badgeSlide 0.8s ease-out forwards;
        }

        .badge:nth-child(1) { animation-delay: 0.2s; }
        .badge:nth-child(2) { animation-delay: 0.4s; }
        .badge:nth-child(3) { animation-delay: 0.6s; }
        .badge:nth-child(4) { animation-delay: 0.8s; }
        .badge:nth-child(5) { animation-delay: 1s; }

        @keyframes badgeSlide {
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .badge:hover {
            transform: translateY(-8px) scale(1.05);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
        }

        .badge::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.5s;
        }

        .badge:hover::before {
            left: 100%;
        }

        /* Main Content */
        main {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 2rem;
        }

        .section {
            margin: 4rem 0;
            opacity: 0;
            transform: translateY(50px);
            animation: sectionReveal 1s ease-out forwards;
        }

        .section:nth-child(2) { animation-delay: 1.2s; }
        .section:nth-child(3) { animation-delay: 1.6s; }
        .section:nth-child(4) { animation-delay: 2s; }

        @keyframes sectionReveal {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .section h2 {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 2rem;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .mission-text {
            font-size: 1.2rem;
            text-align: center;
            max-width: 800px;
            margin: 0 auto 3rem;
            color: var(--secondary);
            line-height: 1.8;
        }

        /* Tech Stack Grid */
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .tech-category {
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(20px);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .tech-category:hover {
            transform: translateY(-10px);
            box-shadow: 0 30px 80px rgba(0, 0, 0, 0.15);
        }

        .tech-category h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--secondary);
            text-align: center;
        }

        .tech-list {
            list-style: none;
        }

        .tech-list li {
            padding: 0.5rem 0;
            font-size: 1.1rem;
            display: flex;
            align-items: center;
            transition: all 0.3s ease;
        }

        .tech-list li:hover {
            transform: translateX(10px);
            color: var(--primary);
        }

        .tech-list li::before {
            content: '⚡';
            margin-right: 0.5rem;
            font-size: 1.2rem;
        }

        /* Services Grid */
        .services {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .service-card {
            background: rgba(255, 255, 255, 0.95);
            padding: 2rem;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: var(--gradient);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .service-card:hover::before {
            transform: scaleX(1);
        }

        .service-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 40px 100px rgba(0, 0, 0, 0.2);
        }

        .service-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            display: block;
        }

        .service-title {
            font-size: 1.3rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: var(--secondary);
        }

        .service-desc {
            color: #666;
            line-height: 1.6;
        }

        /* Interactive Code Block */
        .code-showcase {
            background: #1a1a1a;
            border-radius: 15px;
            padding: 2rem;
            margin: 3rem 0;
            position: relative;
            overflow: hidden;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
        }

        .code-header {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
        }

        .code-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            margin-right: 8px;
        }

        .dot-red { background: #ff5f57; }
        .dot-yellow { background: #ffbd2e; }
        .dot-green { background: #28ca42; }

        .code-content {
            color: #e6e6e6;
            font-family: 'Courier New', monospace;
            font-size: 0.9rem;
            line-height: 1.6;
        }

        .code-line {
            opacity: 0;
            animation: typeLine 0.5s ease-out forwards;
        }

        .code-line:nth-child(1) { animation-delay: 0.2s; }
        .code-line:nth-child(2) { animation-delay: 0.6s; }
        .code-line:nth-child(3) { animation-delay: 1s; }
        .code-line:nth-child(4) { animation-delay: 1.4s; }

        @keyframes typeLine {
            to { opacity: 1; }
        }

        .syntax-keyword { color: #ff79c6; }
        .syntax-string { color: #f1fa8c; }
        .syntax-comment { color: #6272a4; }
        .syntax-function { color: #50fa7b; }

        /* Contact Section */
        .contact {
            background: var(--gradient);
            color: white;
            padding: 4rem 2rem;
            border-radius: 30px;
            text-align: center;
            margin: 4rem 0;
            position: relative;
            overflow: hidden;
        }

        .contact::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .contact-content {
            position: relative;
            z-index: 1;
        }

        .contact h2 {
            color: white;
            margin-bottom: 1rem;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
            flex-wrap: wrap;
        }

        .contact-link {
            color: white;
            text-decoration: none;
            font-size: 1.1rem;
            padding: 1rem 2rem;
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 50px;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .contact-link:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .logo { font-size: 2.5rem; }
            .tagline { font-size: 1.1rem; }
            .badges { flex-direction: column; align-items: center; }
            .tech-grid { grid-template-columns: 1fr; }
            .services { grid-template-columns: 1fr; }
            main { padding: 2rem 1rem; }
            .contact-links { flex-direction: column; align-items: center; }
        }

        /* Loading Animation */
        .loading-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--dark);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            animation: fadeOut 1s ease-out 2s forwards;
        }

        .loading-text {
            color: white;
            font-size: 2rem;
            font-weight: 700;
            animation: pulse 1.5s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.7; }
            50% { opacity: 1; }
        }

        @keyframes fadeOut {
            to {
                opacity: 0;
                visibility: hidden;
            }
        }
    </style>
</head>
<body>
    <!-- Loading Screen -->
    <div class="loading-overlay">
        <div class="loading-text">🦊 CodeCaracal</div>
    </div>

    <!-- Animated Background -->
    <div class="bg-animation"></div>
    
    <!-- Floating Particles -->
    <div class="particles" id="particles"></div>

    <header>
        <div class="logo">🦊 CodeCaracal</div>
        <div class="tagline">Innovative IoT Solutions | Full-Stack Development | Cross-Platform Apps</div>
        
        <div class="badges">
            <div class="badge">📱 Flutter Apps</div>
            <div class="badge">⚛️ React Interfaces</div>
            <div class="badge">🔧 Node.js APIs</div>
            <div class="badge">📡 ESP32 IoT</div>
            <div class="badge">☁️ AWS Cloud</div>
        </div>
    </header>

    <main>
        <section class="section">
            <h2>🚀 Building the Future of IoT</h2>
            <p class="mission-text">
                At CodeCaracal, we transform innovative ideas into reality through cutting-edge IoT solutions. 
                Our expertise spans from embedded hardware programming to cloud-scale applications, 
                delivering comprehensive end-to-end solutions that bridge the physical and digital worlds.
            </p>

            <div class="services">
                <div class="service-card">
                    <div class="service-icon">📱</div>
                    <div class="service-title">Cross-Platform Development</div>
                    <div class="service-desc">Flutter & React applications that work seamlessly across all platforms</div>
                </div>
                <div class="service-card">
                    <div class="service-icon">🔧</div>
                    <div class="service-title">Backend Architecture</div>
                    <div class="service-desc">Scalable Node.js APIs with real-time WebSocket communication</div>
                </div>
                <div class="service-card">
                    <div class="service-icon">📡</div>
                    <div class="service-title">IoT Hardware</div>
                    <div class="service-desc">ESP32/ESP8266 microcontroller solutions with sensor integration</div>
                </div>
                <div class="service-card">
                    <div class="service-icon">☁️</div>
                    <div class="service-title">Cloud Integration</div>
                    <div class="service-desc">AWS, Azure, and Google Cloud IoT platform implementation</div>
                </div>
            </div>
        </section>

        <section class="section">
            <h2>💻 Our Technical Expertise</h2>
            <div class="tech-grid">
                <div class="tech-category">
                    <h3>Frontend Development</h3>
                    <ul class="tech-list">
                        <li>Flutter (Dart)</li>
                        <li>React.js & Next.js</li>
                        <li>Tailwind CSS</li>
                        <li>TypeScript</li>
                    </ul>
                </div>
                <div class="tech-category">
                    <h3>Backend Systems</h3>
                    <ul class="tech-list">
                        <li>Node.js & Express</li>
                        <li>WebSocket APIs</li>
                        <li>Database Design</li>
                        <li>Microservices</li>
                    </ul>
                </div>
                <div class="tech-category">
                    <h3>IoT & Hardware</h3>
                    <ul class="tech-list">
                        <li>ESP32/ESP8266</li>
                        <li>Raspberry Pi</li>
                        <li>Embedded C/C++</li>
                        <li>Sensor Integration</li>
                    </ul>
                </div>
                <div class="tech-category">
                    <h3>Cloud Platforms</h3>
                    <ul class="tech-list">
                        <li>AWS IoT Core</li>
                        <li>Azure IoT Hub</li>
                        <li>Google Cloud IoT</li>
                        <li>Docker & Kubernetes</li>
                    </ul>
                </div>
            </div>
        </section>

        <section class="section">
            <h2>🔥 Code Excellence</h2>
            <div class="code-showcase">
                <div class="code-header">
                    <div class="code-dot dot-red"></div>
                    <div class="code-dot dot-yellow"></div>
                    <div class="code-dot dot-green"></div>
                </div>
                <div class="code-content">
                    <div class="code-line"><span class="syntax-comment">// IoT Device Controller - Real-time Data Stream</span></div>
                    <div class="code-line"><span class="syntax-keyword">const</span> <span class="syntax-function">iotController</span> = <span class="syntax-keyword">async</span> () => {</div>
                    <div class="code-line">  <span class="syntax-keyword">await</span> <span class="syntax-function">connectToCluster</span>(<span class="syntax-string">'aws-iot-endpoint'</span>);</div>
                    <div class="code-line">  <span class="syntax-function">streamSensorData</span>(<span class="syntax-string">'temperature-humidity'</span>);</div>
                    <div class="code-line">};</div>
                </div>
            </div>
        </section>
    </main>

    <div class="contact">
        <div class="contact-content">
            <h2>🌟 Let's Build Something Amazing</h2>
            <p>Ready to transform your IoT vision into reality? Let's connect and discuss your next innovative project.</p>
            <div class="contact-links">
                <a href="https://github.com/CodeCaracal" class="contact-link">🐙 GitHub</a>
                <a href="mailto:contact@codecaracal.dev" class="contact-link">📧 Email</a>
                <a href="#" class="contact-link">🌐 Portfolio</a>
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
                particle.style.animationDelay = Math.random() * 20 + 's';
                particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
                particlesContainer.appendChild(particle);
            }
        }

        // Smooth scrolling for internal links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animationPlayState = 'running';
                }
            });
        }, observerOptions);

        // Observe all animated elements
        document.querySelectorAll('.section, .service-card, .tech-category').forEach(el => {
            observer.observe(el);
        });

        // Interactive hover effects
        document.querySelectorAll('.service-card, .tech-category').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-15px) scale(1.02)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });

        // Initialize particles when page loads
        window.addEventListener('load', () => {
            createParticles();
            
            // Add subtle parallax effect
            window.addEventListener('scroll', () => {
                const scrolled = window.pageYOffset;
                const parallax = document.querySelector('.bg-animation');
                const speed = scrolled * 0.5;
                parallax.style.transform = `translateY(${speed}px)`;
            });
        });

        // Enhanced code typing animation
        const codeLines = document.querySelectorAll('.code-line');
        codeLines.forEach((line, index) => {
            const text = line.textContent;
            line.textContent = '';
            line.style.opacity = '1';
            
            setTimeout(() => {
                let i = 0;
                const typeWriter = () => {
                    if (i < text.length) {
                        line.innerHTML = text.slice(0, i + 1);
                        i++;
                        setTimeout(typeWriter, 50);
                    }
                };
                typeWriter();
            }, index * 800);
        });
    </script>
</body>
</html>
