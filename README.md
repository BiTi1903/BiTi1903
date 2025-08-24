<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BiTi1903 - Developer Portfolio</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0f0f23 0%, #1a1a2e 50%, #16213e 100%);
            color: #ffffff;
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* Animated Background */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(120, 119, 198, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(255, 119, 198, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 80%, rgba(120, 219, 255, 0.1) 0%, transparent 50%);
            animation: float 20s ease-in-out infinite;
            z-index: -1;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            33% { transform: translateY(-20px) rotate(1deg); }
            66% { transform: translateY(10px) rotate(-1deg); }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Header Section */
        .header {
            text-align: center;
            margin-bottom: 60px;
            padding: 40px 0;
        }

        .profile-section {
            margin-bottom: 40px;
        }

        .profile-avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
        }

        .profile-avatar::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }

        .profile-avatar i {
            font-size: 60px;
            color: white;
            z-index: 1;
        }

        .profile-name {
            font-size: 2.5rem;
            font-weight: 700;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
        }

        .profile-title {
            font-size: 1.2rem;
            color: #a0a0a0;
            margin-bottom: 20px;
        }

        /* Section Headers */
        .section-header {
            text-align: center;
            margin: 60px 0 40px;
            position: relative;
        }

        .section-header h2 {
            font-size: 2.2rem;
            font-weight: 700;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
        }

        .section-header::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 2px;
        }

        /* Technologies Section */
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }

        .tech-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .tech-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: left 0.5s;
        }

        .tech-card:hover::before {
            left: 100%;
        }

        .tech-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(102, 126, 234, 0.3);
            border-color: rgba(102, 126, 234, 0.5);
        }

        .tech-badges {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 10px;
        }

        .tech-badge {
            display: inline-block;
            transition: transform 0.3s ease;
        }

        .tech-badge:hover {
            transform: scale(1.1);
        }

        .tech-badge img {
            height: 35px;
            border-radius: 5px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        /* GitHub Stats Section */
        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            transition: all 0.3s ease;
            overflow: hidden;
            position: relative;
        }

        .stat-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, rgba(102, 126, 234, 0.1), transparent);
            animation: rotate 4s linear infinite;
            opacity: 0;
            transition: opacity 0.3s;
        }

        .stat-card:hover::before {
            opacity: 1;
        }

        @keyframes rotate {
            100% { transform: rotate(360deg); }
        }

        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(102, 126, 234, 0.2);
        }

        .stat-card img {
            width: 100%;
            border-radius: 10px;
            position: relative;
            z-index: 1;
        }

        /* Contact Section */
        .contact-section {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 40px;
            margin: 60px 0;
            text-align: center;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .contact-item {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 25px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .contact-item::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: radial-gradient(circle, rgba(102, 126, 234, 0.1) 0%, transparent 70%);
            transition: all 0.4s ease;
            transform: translate(-50%, -50%);
        }

        .contact-item:hover::before {
            width: 300px;
            height: 300px;
        }

        .contact-item:hover {
            transform: translateY(-5px);
            border-color: rgba(102, 126, 234, 0.5);
        }

        .contact-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .contact-item h3 {
            margin-bottom: 10px;
            font-size: 1.3rem;
        }

        .contact-item a {
            color: #a0a0a0;
            text-decoration: none;
            transition: color 0.3s ease;
            position: relative;
            z-index: 1;
        }

        .contact-item:hover a {
            color: #ffffff;
        }

        /* Floating Elements */
        .floating-shapes {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .shape {
            position: absolute;
            opacity: 0.1;
        }

        .shape-1 {
            top: 10%;
            left: 10%;
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 50%;
            animation: float-1 6s ease-in-out infinite;
        }

        .shape-2 {
            top: 60%;
            right: 10%;
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #f093fb, #f5576c);
            transform: rotate(45deg);
            animation: float-2 8s ease-in-out infinite;
        }

        .shape-3 {
            bottom: 20%;
            left: 15%;
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, #4facfe, #00f2fe);
            border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
            animation: float-3 7s ease-in-out infinite;
        }

        @keyframes float-1 {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        @keyframes float-2 {
            0%, 100% { transform: translateY(0px) rotate(45deg); }
            50% { transform: translateY(-30px) rotate(225deg); }
        }

        @keyframes float-3 {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-15px) rotate(90deg); }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .container {
                padding: 15px;
            }

            .profile-name {
                font-size: 2rem;
            }

            .section-header h2 {
                font-size: 1.8rem;
            }

            .stats-container {
                grid-template-columns: 1fr;
            }

            .tech-grid {
                grid-template-columns: 1fr;
            }

            .contact-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Smooth scrolling */
        html {
            scroll-behavior: smooth;
        }

        /* Glowing text effect */
        .glow-text {
            text-shadow: 0 0 10px rgba(102, 126, 234, 0.5);
        }
    </style>
</head>
<body>
    <!-- Floating Shapes -->
    <div class="floating-shapes">
        <div class="shape shape-1"></div>
        <div class="shape shape-2"></div>
        <div class="shape shape-3"></div>
    </div>

    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <div class="profile-section">
                <div class="profile-avatar">
                    <i class="fas fa-code"></i>
                </div>
                <h1 class="profile-name glow-text">BiTi1903</h1>
                <p class="profile-title">Full-Stack Developer & Mobile App Developer</p>
            </div>
        </header>

        <!-- Technologies Section -->
        <section class="tech-section">
            <div class="section-header">
                <h2>🛠 Technologies & Tools 🛠</h2>
            </div>
            
            <div class="tech-grid">
                <div class="tech-card">
                    <h3 style="margin-bottom: 20px; color: #667eea;">Development Tools</h3>
                    <div class="tech-badges">
                        <span class="tech-badge">
                            <img src="https://img.shields.io/badge/Visual%20Studio%20Code-282C34?logo=visual-studio-code&logoColor=007ACC" alt="VS Code" title="Visual Studio Code" />
                        </span>
                        <span class="tech-badge">
                            <img src="https://img.shields.io/badge/GitHub-282C34?logo=github&logoColor=FFFFFF" alt="GitHub" title="GitHub" />
                        </span>
                    </div>
                </div>

                <div class="tech-card">
                    <h3 style="margin-bottom: 20px; color: #667eea;">Backend & Web</h3>
                    <div class="tech-badges">
                        <span class="tech-badge">
                            <img src="https://img.shields.io/badge/ASP.NET%20Core-282C34?logo=dotnet&logoColor=5C2D91" alt="ASP.NET Core" title="ASP.NET Core" />
                        </span>
                        <span class="tech-badge">
                            <img src="https://img.shields.io/badge/C%23-282C34?logo=c-sharp&logoColor=9B4B96" alt="C#" title="C#" />
                        </span>
                    </div>
                </div>

                <div class="tech-card">
                    <h3 style="margin-bottom: 20px; color: #667eea;">Mobile Development</h3>
                    <div class="tech-badges">
                        <span class="tech-badge">
                            <img src="https://img.shields.io/badge/Flutter-282C34?logo=flutter&logoColor=02569B" alt="Flutter" title="Flutter" />
                        </span>
                        <span class="tech-badge">
                            <img src="https://img.shields.io/badge/Dart-282C34?logo=dart&logoColor=0175C2" alt="Dart" title="Dart" />
                        </span>
                    </div>
                </div>

                <div class="tech-card">
                    <h3 style="margin-bottom: 20px; color: #667eea;">Database & Cloud</h3>
                    <div class="tech-badges">
                        <span class="tech-badge">
                            <img src="https://img.shields.io/badge/Firebase-282C34?logo=firebase&logoColor=FFCA28" alt="Firebase" title="Firebase" />
                        </span>
                        <span class="tech-badge">
                            <img src="https://img.shields.io/badge/SQL-282C34?logo=postgresql&logoColor=00758F" alt="SQL" title="SQL" />
                        </span>
                    </div>
                </div>
            </div>
        </section>

        <!-- GitHub Stats Section -->
        <section class="stats-section">
            <div class="section-header">
                <h2>🔥 GitHub Statistics 🔥</h2>
            </div>
            
            <div class="stats-container">
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api?username=BiTi1903&show_icons=true&theme=tokyonight&hide_border=false&include_all_commits=true&count_private=true" 
                         alt="GitHub Stats" />
                </div>
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=BiTi1903&layout=compact&theme=tokyonight&hide_border=false" 
                         alt="Top Languages" />
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="contact-section">
            <div class="section-header">
                <h2>👽 Where to Find Me 👽</h2>
                <p style="color: #a0a0a0; margin-top: 10px;">🌟 Kết nối với tôi</p>
            </div>

            <div class="contact-grid">
                <div class="contact-item">
                    <div class="contact-icon">
                        <i class="fab fa-facebook"></i>
                    </div>
                    <h3>Facebook</h3>
                    <a href="https://www.facebook.com/dunghackfemnha/" target="_blank">Lê Bảo Thiện</a>
                </div>

                <div class="contact-item">
                    <div class="contact-icon">
                        <i class="fas fa-phone"></i>
                    </div>
                    <h3>Phone</h3>
                    <a href="tel:0865340630" target="_blank">0865340630</a>
                </div>
            </div>
        </section>
    </div>

    <script>
        // Add smooth reveal animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Apply animations to cards
        document.addEventListener('DOMContentLoaded', function() {
            const cards = document.querySelectorAll('.tech-card, .stat-card, .contact-item');
            cards.forEach((card, index) => {
                card.style.opacity = '0';
                card.style.transform = 'translateY(30px)';
                card.style.transition = `opacity 0.6s ease ${index * 0.1}s, transform 0.6s ease ${index * 0.1}s`;
                observer.observe(card);
            });
        });

        // Add interactive cursor effect
        document.addEventListener('mousemove', function(e) {
            const cursor = document.querySelector('.cursor');
            if (!cursor) {
                const newCursor = document.createElement('div');
                newCursor.className = 'cursor';
                newCursor.style.cssText = `
                    position: fixed;
                    width: 20px;
                    height: 20px;
                    background: radial-gradient(circle, rgba(102, 126, 234, 0.8), transparent);
                    border-radius: 50%;
                    pointer-events: none;
                    z-index: 9999;
                    transform: translate(-50%, -50%);
                    transition: all 0.1s ease;
                `;
                document.body.appendChild(newCursor);
            }
            
            const cursorElement = document.querySelector('.cursor');
            cursorElement.style.left = e.clientX + 'px';
            cursorElement.style.top = e.clientY + 'px';
        });
    </script>
</body>
</html>
