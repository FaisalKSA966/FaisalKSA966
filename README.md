<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Faisal - Developer Profile</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0d1421 0%, #1a2332 25%, #2d3748 50%, #1a2332 75%, #0d1421 100%);
            color: #ffffff;
            overflow-x: hidden;
            position: relative;
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
                radial-gradient(circle at 20% 80%, rgba(0, 194, 255, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(66, 165, 245, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 40%, rgba(0, 230, 118, 0.05) 0%, transparent 50%);
            animation: backgroundPulse 8s ease-in-out infinite alternate;
            z-index: -1;
        }

        @keyframes backgroundPulse {
            0% { opacity: 0.3; }
            100% { opacity: 0.7; }
        }

        /* Floating particles */
        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: rgba(0, 194, 255, 0.6);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 0; }
            50% { transform: translateY(-100px) rotate(180deg); opacity: 1; }
        }

        .container {
            min-height: 100vh;
            padding: 2rem;
            position: relative;
            z-index: 1;
        }

        /* Header Section */
        .header {
            text-align: center;
            margin-bottom: 4rem;
            position: relative;
        }

        .profile-container {
            position: relative;
            display: inline-block;
            margin-bottom: 2rem;
        }

        .profile-img {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            border: 4px solid transparent;
            background: linear-gradient(45deg, #00c2ff, #42a5f5, #00e676);
            padding: 4px;
            animation: profileGlow 3s ease-in-out infinite alternate;
            transition: transform 0.3s ease;
        }

        .profile-img:hover {
            transform: scale(1.1) rotate(5deg);
        }

        .profile-img img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
        }

        @keyframes profileGlow {
            0% { box-shadow: 0 0 20px rgba(0, 194, 255, 0.5); }
            100% { box-shadow: 0 0 40px rgba(0, 194, 255, 0.8), 0 0 80px rgba(66, 165, 245, 0.3); }
        }

        .name-title {
            font-size: 4rem;
            font-weight: 900;
            background: linear-gradient(45deg, #00c2ff, #42a5f5, #00e676, #ffeb3b);
            background-size: 400% 400%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 4s ease-in-out infinite;
            margin-bottom: 1rem;
            text-shadow: 0 0 30px rgba(0, 194, 255, 0.5);
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .subtitle {
            font-size: 1.2rem;
            color: #94a3b8;
            margin-bottom: 2rem;
            opacity: 0;
            animation: fadeInUp 1s ease 0.5s forwards;
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Info Cards */
        .info-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }

        .info-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 2rem;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
            animation: cardSlideIn 0.8s ease forwards;
            opacity: 0;
            transform: translateY(50px);
        }

        .info-card:nth-child(1) { animation-delay: 0.2s; }
        .info-card:nth-child(2) { animation-delay: 0.4s; }
        .info-card:nth-child(3) { animation-delay: 0.6s; }

        @keyframes cardSlideIn {
            to { opacity: 1; transform: translateY(0); }
        }

        .info-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: left 0.5s ease;
        }

        .info-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 194, 255, 0.2);
            border-color: rgba(0, 194, 255, 0.3);
        }

        .info-card:hover::before {
            left: 100%;
        }

        .card-icon {
            font-size: 3rem;
            color: #00c2ff;
            margin-bottom: 1rem;
            display: block;
        }

        .card-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: #ffffff;
        }

        .card-content {
            color: #cbd5e0;
            line-height: 1.6;
        }

        /* Skills Section */
        .skills-container {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 25px;
            padding: 3rem;
            margin-bottom: 4rem;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
        }

        .skills-container::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, rgba(0, 194, 255, 0.1), transparent);
            animation: rotate 10s linear infinite;
            z-index: -1;
        }

        @keyframes rotate {
            to { transform: rotate(360deg); }
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 800;
            text-align: center;
            margin-bottom: 2rem;
            background: linear-gradient(45deg, #00c2ff, #42a5f5);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .skill-item {
            background: rgba(255, 255, 255, 0.08);
            border-radius: 15px;
            padding: 1.5rem;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
        }

        .skill-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(45deg, #00c2ff, #42a5f5, #00e676);
            transform: translateX(-100%);
            transition: transform 0.3s ease;
        }

        .skill-item:hover {
            transform: translateY(-5px);
            background: rgba(0, 194, 255, 0.1);
            box-shadow: 0 10px 30px rgba(0, 194, 255, 0.2);
        }

        .skill-item:hover::before {
            transform: translateX(0);
        }

        .skill-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: #42a5f5;
        }

        .skill-name {
            font-weight: 600;
            color: #ffffff;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }

        .project-card {
            background: linear-gradient(135deg, rgba(0, 194, 255, 0.1) 0%, rgba(66, 165, 245, 0.1) 100%);
            border-radius: 20px;
            padding: 2.5rem;
            border: 1px solid rgba(0, 194, 255, 0.2);
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease;
            cursor: pointer;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.05), transparent);
            transform: translateX(-100%) skewX(-45deg);
            transition: transform 0.6s ease;
        }

        .project-card:hover {
            transform: translateY(-15px) scale(1.02);
            box-shadow: 0 25px 50px rgba(0, 194, 255, 0.3);
        }

        .project-card:hover::before {
            transform: translateX(100%) skewX(-45deg);
        }

        .project-title {
            font-size: 1.8rem;
            font-weight: 700;
            color: #00c2ff;
            margin-bottom: 1rem;
        }

        .project-description {
            color: #cbd5e0;
            line-height: 1.6;
            margin-bottom: 1.5rem;
        }

        .project-status {
            display: inline-block;
            padding: 0.5rem 1rem;
            background: rgba(0, 230, 118, 0.2);
            color: #00e676;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 600;
        }

        /* Contact Section */
        .contact-section {
            text-align: center;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 25px;
            padding: 3rem;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
        }

        .contact-btn {
            display: inline-flex;
            align-items: center;
            gap: 1rem;
            background: linear-gradient(45deg, #00c2ff, #42a5f5);
            color: white;
            padding: 1rem 2rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .contact-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.3s ease;
        }

        .contact-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(0, 194, 255, 0.4);
        }

        .contact-btn:hover::before {
            left: 100%;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .name-title {
                font-size: 2.5rem;
            }
            
            .info-grid,
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            }
            
            .container {
                padding: 1rem;
            }
        }

        /* Arabic RTL Support */
        .rtl-text {
            direction: rtl;
            text-align: right;
        }

        /* Stats Animation */
        .stat-number {
            font-size: 2rem;
            font-weight: 900;
            color: #00c2ff;
            animation: countUp 2s ease-out;
        }

        @keyframes countUp {
            from { opacity: 0; transform: scale(0.5); }
            to { opacity: 1; transform: scale(1); }
        }
    </style>
</head>
<body>
    <!-- Floating Particles -->
    <div class="particle" style="top: 10%; left: 10%; animation-delay: 0s;"></div>
    <div class="particle" style="top: 20%; left: 80%; animation-delay: 1s;"></div>
    <div class="particle" style="top: 60%; left: 20%; animation-delay: 2s;"></div>
    <div class="particle" style="top: 80%; left: 70%; animation-delay: 3s;"></div>
    <div class="particle" style="top: 40%; left: 90%; animation-delay: 4s;"></div>

    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <div class="profile-container">
                <div class="profile-img">
                    <img src="https://avatars.githubusercontent.com/u/200758656?v=4" alt="Faisal Avatar">
                </div>
            </div>
            <h1 class="name-title">فيصل</h1>
            <p class="subtitle">13 سنة | السعودية | المنطقة الشرقية</p>
        </header>

        <!-- Info Cards -->
        <section class="info-grid">
            <div class="info-card">
                <i class="fas fa-user-graduate card-icon"></i>
                <h3 class="card-title">عني</h3>
                <div class="card-content rtl-text">
                    مطور سعودي عمري 13 سنة أركز على <strong>JavaScript</strong> والتقنيات الخلفية.
                    أتخصص في <strong>تطوير بوتات Discord</strong>، وأتعمق في التطوير الشامل وإنشاء الألعاب باستخدام <strong>Unreal Engine</strong> و<strong>الأمن السيبراني</strong>.
                    هدفي هو بناء أدوات <em>فعالة</em> و<em>مؤثرة</em>، خاصة في الذكاء الاصطناعي والأتمتة.
                </div>
            </div>

            <div class="info-card">
                <i class="fas fa-graduation-cap card-icon"></i>
                <h3 class="card-title">التعليم</h3>
                <div class="card-content rtl-text">
                    • طالب متفوق أكاديمياً<br>
                    • عضو في برنامج <strong>موهبة</strong>، السعودية<br>
                    • متخصص في العلوم والتكنولوجيا<br>
                    • شغوف بالبرمجة والابتكار
                </div>
            </div>

            <div class="info-card">
                <i class="fas fa-globe card-icon"></i>
                <h3 class="card-title">اللغات</h3>
                <div class="card-content rtl-text">
                    • العربية: اللغة الأم (اللهجة السعودية)<br>
                    • الإنجليزية: طلاقة تامة (اللكنة الاسكتلندية والأمريكية)<br>
                    • أتعلم الروسية والإسبانية<br>
                    • شغوف بتعلم اللغات الجديدة
                </div>
            </div>
        </section>

        <!-- Skills Section -->
        <section class="skills-container">
            <h2 class="section-title">المهارات التقنية</h2>
            <div class="skills-grid">
                <div class="skill-item">
                    <i class="fab fa-js-square skill-icon"></i>
                    <div class="skill-name">JavaScript</div>
                </div>
                <div class="skill-item">
                    <i class="fab fa-node-js skill-icon"></i>
                    <div class="skill-name">Node.js</div>
                </div>
                <div class="skill-item">
                    <i class="fas fa-server skill-icon"></i>
                    <div class="skill-name">Express</div>
                </div>
                <div class="skill-item">
                    <i class="fab fa-discord skill-icon"></i>
                    <div class="skill-name">Discord Bots</div>
                </div>
                <div class="skill-item">
                    <i class="fab fa-html5 skill-icon"></i>
                    <div class="skill-name">HTML5</div>
                </div>
                <div class="skill-item">
                    <i class="fab fa-css3-alt skill-icon"></i>
                    <div class="skill-name">CSS3</div>
                </div>
                <div class="skill-item">
                    <i class="fab fa-git-alt skill-icon"></i>
                    <div class="skill-name">Git</div>
                </div>
                <div class="skill-item">
                    <i class="fab fa-linux skill-icon"></i>
                    <div class="skill-name">Linux</div>
                </div>
                <div class="skill-item">
                    <i class="fas fa-gamepad skill-icon"></i>
                    <div class="skill-name">Unreal Engine</div>
                </div>
                <div class="skill-item">
                    <i class="fas fa-shield-alt skill-icon"></i>
                    <div class="skill-name">Cybersecurity</div>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section>
            <h2 class="section-title">المشاريع والأدوار</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3 class="project-title">OpticAI</h3>
                    <p class="project-description rtl-text">
                        مؤسس ومطور رئيسي لمشروع OpticAI - منصة ذكاء اصطناعي متقدمة تهدف إلى تحسين تجربة المستخدم وتوفير حلول ذكية ومبتكرة.
                    </p>
                    <span class="project-status">قيد التطوير</span>
                </div>

                <div class="project-card">
                    <h3 class="project-title">Flowline</h3>
                    <p class="project-description rtl-text">
                        مالك شركة Flowline الناشئة - نعمل على تطوير أدوات وحلول تقنية مبتكرة لتحسين سير العمل والإنتاجية.
                    </p>
                    <span class="project-status">مرحلة مبكرة</span>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="contact-section">
            <h2 class="section-title">تواصل معي</h2>
            <p style="margin-bottom: 2rem; color: #cbd5e0;">دعنا نتعاون ونبني شيئاً رائعاً معاً!</p>
            <a href="#" class="contact-btn" onclick="navigator.clipboard.writeText('6j.'); alert('تم نسخ اسم المستخدم!')">
                <i class="fab fa-discord"></i>
                Discord: 6j.
            </a>
        </section>
    </div>

    <script>
        // Add some interactive animations
        document.addEventListener('DOMContentLoaded', function() {
            // Animate skill items on scroll
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };

            const observer = new IntersectionObserver(function(entries) {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.animationDelay = Math.random() * 0.5 + 's';
                        entry.target.style.animation = 'fadeInUp 0.6s ease forwards';
                    }
                });
            }, observerOptions);

            // Observe all skill items
            document.querySelectorAll('.skill-item').forEach(item => {
                observer.observe(item);
            });

            // Add floating animation to profile image
            const profileImg = document.querySelector('.profile-img');
            let mouseX = 0, mouseY = 0;
            let imgX = 0, imgY = 0;

            document.addEventListener('mousemove', function(e) {
                mouseX = (e.clientX - window.innerWidth / 2) * 0.01;
                mouseY = (e.clientY - window.innerHeight / 2) * 0.01;
            });

            function animate() {
                imgX += (mouseX - imgX) * 0.1;
                imgY += (mouseY - imgY) * 0.1;
                
                profileImg.style.transform = `translate(${imgX}px, ${imgY}px) scale(1)`;
                requestAnimationFrame(animate);
            }
            animate();

            // Add dynamic particles
            function createParticle() {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = '100%';
                particle.style.animationDuration = (Math.random() * 3 + 4) + 's';
                particle.style.opacity = Math.random() * 0.8 + 0.2;
                document.body.appendChild(particle);

                setTimeout(() => {
                    particle.remove();
                }, 6000);
            }

            setInterval(createParticle, 2000);
        });
    </script>
</body>
</html>
