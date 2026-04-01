
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>M Naveen Sai | AI&DS Portfolio</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;500;700&family=Plus+Jakarta+Sans:wght@300;400;600;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"/>
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">

    <style>
        :root {
            --bg: #020617;
            --card: rgba(30, 41, 59, 0.5);
            --accent: #22d3ee;
            --accent-cyan: #22d3ee;
            --purple: #a855f7;
            --text: #f8fafc;
            --dim: #94a3b8;
        }

        * {
            margin: 0; padding: 0; box-sizing: border-box;
            font-family: 'Plus Jakarta Sans', sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg);
            color: var(--text);
            overflow-x: hidden;
        }

        /* --- Animated Canvas Background --- */
        #bg-canvas {
            position: fixed;
            top: 0; left: 0;
            z-index: -1;
            filter: blur(80px);
            opacity: 0.4;
        }

        /* --- Navigation --- */
        nav {
            position: fixed;
            top: 20px; left: 50%;
            transform: translateX(-50%);
            width: 90%; max-width: 1000px;
            background: rgba(15, 23, 42, 0.7);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: 100px;
            padding: 12px 25px;
            display: flex; justify-content: space-between; align-items: center;
            z-index: 1000;
        }

        nav .logo {
            font-family: 'Space Grotesk', sans-serif;
            font-weight: 800; color: var(--accent);
            letter-spacing: 1px;
        }

        nav a {
            color: var(--dim); text-decoration: none;
            margin-left: 20px; font-size: 0.85rem;
            font-weight: 600; transition: 0.3s;
        }

        nav a:hover { color: var(--accent); }

        /* --- Hero Section --- */
        header {
            height: 100vh;
            display: flex; flex-direction: column;
            justify-content: center; align-items: center;
            text-align: center; padding: 20px;
        }

        .profile-ring {
            position: relative; padding: 10px; margin-bottom: 30px;
        }

        .profile-ring::before {
            content: ''; position: absolute; inset: 0;
            border-radius: 50%; padding: 3px;
            background: linear-gradient(45deg, var(--accent), var(--purple));
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            mask-composite: exclude;
            animation: rotate 5s linear infinite;
        }

        header img.profile {
            width: 170px; height: 170px;
            border-radius: 50%; object-fit: cover;
        }

        header h1 {
            font-size: 5rem; font-weight: 800;
            font-family: 'Space Grotesk', sans-serif;
            background: linear-gradient(to bottom, #fff, #475569);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .badge {
            background: rgba(34, 211, 238, 0.1);
            color: var(--accent); padding: 5px 15px;
            border-radius: 50px; font-size: 0.8rem;
            font-weight: 700; border: 1px solid rgba(34, 211, 238, 0.3);
            margin-bottom: 20px;
        }

        /* --- Grid & Cards --- */
        section {
            max-width: 1100px; margin: 150px auto; padding: 0 25px;
        }

        .section-title {
            font-family: 'Space Grotesk', sans-serif;
            font-size: 3rem; margin-bottom: 50px;
        }

        .section-title span { color: var(--accent); }

        .glass-card {
            background: var(--card);
            border: 1px solid rgba(255,255,255,0.05);
            backdrop-filter: blur(10px);
            border-radius: 24px; padding: 40px;
            transition: 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .glass-card:hover {
            transform: translateY(-10px);
            border-color: var(--accent);
            background: rgba(30, 41, 59, 0.8);
        }

        .skills-grid {
            display: grid; grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); gap: 20px;
        }

        .skill-box {
            background: rgba(255,255,255,0.03);
            border: 1px solid rgba(255,255,255,0.1);
            padding: 25px; border-radius: 20px; text-align: center;
            transition: 0.3s;
        }

        .skill-box:hover { background: var(--accent); color: var(--bg); font-weight: bold; }
        .skill-box i { font-size: 2rem; margin-bottom: 15px; display: block; }

        /* --- Certificates --- */
        .achievements-grid {
            display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 25px;
        }

        .achievement-card {
            background: rgba(30, 41, 59, 0.4);
            border: 1px solid rgba(255, 255, 255, 0.05);
            border-radius: 20px; padding: 30px;
            display: flex; gap: 20px; transition: 0.4s;
            backdrop-filter: blur(10px);
        }

        .achievement-card:hover {
            background: rgba(34, 211, 238, 0.05);
            border-color: var(--accent); transform: scale(1.03);
        }

        .achievement-icon {
            width: 60px; height: 60px;
            background: rgba(34, 211, 238, 0.1);
            border-radius: 15px; display: flex; align-items: center;
            justify-content: center; color: var(--accent);
            font-size: 1.5rem; flex-shrink: 0;
        }

        .category-tag {
            font-size: 0.7rem; text-transform: uppercase;
            letter-spacing: 1.5px; color: var(--accent);
            font-weight: 800; margin-bottom: 8px; display: block;
        }
         /* --- Education Timeline --- */
        .edu-item {
            border-left: 2px solid var(--accent-cyan);
            padding-left: 30px;
            position: relative;
            margin-bottom: 40px;
        }

        .edu-item::before {
            content: "";
            width: 15px;
            height: 15px;
            background: var(--accent-cyan);
            position: absolute;
            left: -9px;
            top: 5px;
            border-radius: 50%;
        }
            .btn-contact {
            padding: 15px 40px;
            background: var(--accent-cyan);
            color: #000;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 700;
            display: inline-block;
            margin-top: 20px;
        }



        /* --- Contact --- */
        .contact-grid {
            display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 20px;
        }

        .contact-card {
            background: var(--card); padding: 30px; border-radius: 20px;
            text-decoration: none; color: var(--text); text-align: center;
            border: 1px solid rgba(255,255,255,0.05); transition: 0.3s;
        }

        .contact-card:hover {
            border-color: var(--accent); transform: translateY(-10px);
            background: rgba(34, 211, 238, 0.1);
        }

        .contact-card i { font-size: 2rem; color: var(--accent); margin-bottom: 15px; }

        @keyframes rotate { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }

        @media (max-width: 768px) {
            header h1 { font-size: 3rem; }
            nav { width: 95%; }
            .contact-grid { grid-template-columns: 1fr 1fr; }
        }
        .project-tag {
            font-size: 0.65rem;
            background: rgba(34, 211, 238, 0.1);
            color: var(--accent);
            padding: 3px 10px;
            border-radius: 4px;
            margin-right: 5px;
            font-weight: 800;
            border: 1px solid rgba(34, 211, 238, 0.2);
        }
    </style>
</head>
<body>

    <canvas id="bg-canvas"></canvas>

    <nav>
        <div class="logo">PORTFOLIO</div>
        <div>
            <a href="#about">About</a>
            <a href="#skills">Tech</a>
            <a href="#projects">Work</a>
            <a href="#contact">Contact</a>
        </div>
    </nav>

    <header>
        <div class="badge" data-aos="fade-down">Artificial Intelligence & Data Science Student</div>
        <div class="profile-ring" data-aos="zoom-in">
            <img class="profile" src="https://i.pinimg.com/736x/5d/40/52/5d4052ddc3545176db7564932269a0db.jpg" alt="M Naveen Sai">
        </div>
        <h1 data-aos="fade-up">M Naveen Sai</h1>
        <p style="color: var(--dim); font-size: 1.2rem; margin-top: 20px;">
            B.Tech Student @ MTIET | Building the future with code.
        </p>
    </header>

    <section id="about">
        <h2 class="section-title" data-aos="fade-right">About <span>Me</span></h2>
        <div class="glass-card" data-aos="fade-up">
            <p style="font-size: 1.3rem; line-height: 1.8; color: var(--dim);">
                I’m a 2nd-year engineering student passionate about <span style="color: #fff;">Arificial Intelligence</span> and <span style="color: #fff;">Modern Web Architectures</span>. 
                I focus on creating high-performance applications that solve real-world problems using the latest AI frameworks.
            </p>
        </div>
    </section>
      <section id="education">
        <h2 class="section-title" data-aos="fade-right">Education</h2>
        <div class="edu-item" data-aos="fade-up">
            <h3>B.Tech (AI & DS)</h3>
            <p style="color: var(--accent-cyan);">Mother Theresa Institute of Engineering and Technology</p>
            <p>2024–2028 | <b>CGPA: 8.5</b></p>
        </div>
        <div class="edu-item" data-aos="fade-up" data-aos-delay="100">
            <h3>Intermediate (+2)</h3>
            <p style="color: var(--accent-cyan);">Mother Theresa Junior College</p>
            <p> 2022–2024 — <b>91%</b></p>
        </div>
        <div class="edu-item" data-aos="fade-up" data-aos-delay="200">
            <h3>SSC (10th Grade)</h3>
            <p style="color: var(--accent-cyan);">Sri Sarada English Medium High School </p>
            <p> 2022 — <b>89%</b></p>
        </div>
    </section>

    <section id="skills">
        <h2 class="section-title">My <span>Arsenal</span></h2>
        <div class="skills-grid">
            <div class="skill-box" data-aos="flip-up" data-aos-delay="200"><i class="fas fa-code" style="color:#a8b9cc"></i>C Language</div>
             <div class="skill-box" data-aos="flip-up" data-aos-delay="300"><i class="fab fa-html5" style="color:#e34c26"></i>HTML/CSS</div>
             <div class="skill-box" data-aos="flip-up" data-aos-delay="500"><i class="fab fa-php" style="color:#777bb4"></i>PHP</div>
            

            <div class="skill-box" data-aos="flip-up" data-aos-delay="100"><i class="fab fa-java" style="color:#f89820"></i>Java</div>
            
            <div class="skill-box" data-aos="flip-up" data-aos-delay="400"><i class="fab fa-js" style="color:#f7df1e"></i>JavaScript</div>
          <div class="skill-box" data-aos="flip-up"><i class="fab fa-python" style="color:#3776ab"></i>Python</div>
        </div>
    </section>

    <section id="projects">
        <h2 class="section-title">Featured <span>Work</span></h2>
        <div class="achievements-grid">
            <div class="glass-card" data-aos="zoom-in-up">
                <span style="color: var(--accent); font-weight: 800;">01</span>
                <h3 style="margin: 15px 0;">College Result Portal</h3>
                <p style="color: var(--dim);">Dynamic HTML/JS Result portal with real-time analytics and secure student access.</p>
                <a href="https://youtu.be/15k027vWLOc?si=WnENkxLVIHS9c6jF" class="btn-contact">Visit My Project</a>
            </div>
            <div class="glass-card" data-aos="zoom-in-up" data-aos-delay="100">
                <span style="color: var(--accent); font-weight: 800;">02</span>
                <h3 style="margin: 15px 0;">Canteen Management</h3>
                <p style="color: var(--dim);">Full-stack web application for automating order tracking and inventory within a college canteen environment using PHP and XAMP database..</p>
                 <a href="https://youtu.be/fxZd3JlfTio?si=pLZrpNFFYej4xFZk" class="btn-contact">View My Project</a>
            </div>
            <div class="glass-card" data-aos="zoom-in-up" data-aos-delay="100">
                <span style="color: var(--accent); font-weight: 800;">03</span>
                <h3 style="margin: 15px 0;">EEG Analysis Project</h3>
                <p style="color: var(--dim);">A linear logical tool designed with Python to Analysis of Depression Detector of Patients</p>
                <a href="https://youtu.be/15k027vWLOc?si=WnENkxLVIHS9c6jF" class="btn-contact">View My Project</a>
            </div>
            <div class="glass-card" data-aos="zoom-in-up" data-aos-delay="100">
                <span style="color: var(--accent); font-weight: 800;">02</span>
                <h3 style="margin: 15px 0;"> Java Calculator</h3>
                <p style="color: var(--dim);">A responsive personal brand showcase using modern CSS and AOS animation libraries.</p>
            </div>
              <div class="glass-card" data-aos="zoom-in-up" data-aos-delay="100">
                <span style="color: var(--accent); font-weight: 800;">03</span>
                <h3 style="margin: 15px 0;">EEG Analysis Project</h3>
                <p style="color: var(--dim);">A logical tool designed for complex mathematical operations using Java backend logic.</p>
            
            </div>
        </div>
    </section>

    <section id="certificates">
        <h2 class="section-title" data-aos="fade-right">Recognition & <span>Certifications</span></h2>
        <div class="achievements-grid">
            <div class="achievement-card" data-aos="fade-up" data-aos-delay="100">
                <div class="achievement-icon"><i class="fas fa-laptop-code"></i></div>
                <div class="achievement-content">
                    <span class="category-tag">Internship</span>
                    <h3>Hands-on-Project</h3>
                    <p>Certificate of IIITK in Completing a Smart Humidity and Temperature Sensor Project </p>
                </div>
            </div>
            <div class="achievement-card" data-aos="fade-up">
                <div class="achievement-icon"><i class="fas fa-trophy"></i></div>
                <div class="achievement-content">
                    <span class="category-tag">Hackathon</span>
                    <h3>ProjectExpo 1st Prize Winner</h3>
                    <p>Kuppam Engineering College — Innovative technical project presentation.</p>
                </div>
            </div>
            <div class="achievement-card" data-aos="fade-up" data-aos-delay="100">
                <div class="achievement-icon"><i class="fas fa-trophy"></i></div>
                <div class="achievement-content">
                    <span class="category-tag">Hackathon</span>
                    <h3>24H Web Dev 2nd Prize Champion</h3>
                    <p>M.T.I.E.T — Achievement in intensive 24-hour application development.</p>
                </div>
            </div>
            
            <div class="achievement-card" data-aos="fade-up" data-aos-delay="200">
                <div class="achievement-icon"><i class="fas fa-cloud"></i></div>
                <div class="achievement-content">
                    <span class="category-tag">Virtual</span>
                    <h3>Cloud Gen AI</h3>
                    <p>Specialized training in Generative AI and Cloud infrastructure.</p>
                </div>
            </div>
        </div>
    </section>

    <footer id="contact">
        <h2 class="section-title" style="text-align: center;">Get In <span>Touch</span></h2>
        <div class="contact-grid">
            <a href="mailto:naveenmuthu2028@gmail.com" class="contact-card">
                <i class="fas fa-envelope"></i>
                <p>Email Me</p>
            </a>
            <a href="https://linkedin.com/in/naveen-sai-m" target="_blank" class="contact-card">
                <i class="fab fa-linkedin-in"></i>
                <p>LinkedIn</p>
            </a>
            <a href="https://github.com/NaveenSai2028" target="_blank" class="contact-card">
                <i class="fab fa-github"></i>
                <p>GitHub</p>
            </a>
            <a href="tel:+919505482092" class="contact-card">
                <i class="fas fa-phone"></i>
                <p>Call Now</p>
            </a>
        </div>
        <p style="text-align: center; margin-top: 80px; color: #444; font-size: 0.8rem;">
            © 2026 M Naveen Sai | Engineering Excellence
        </p>
    </footer>

    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        AOS.init({ duration: 1000, once: true });

        const canvas = document.getElementById('bg-canvas');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        function drawCircles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            const time = Date.now() * 0.001;
            for(let i = 0; i < 3; i++) {
                ctx.beginPath();
                const x = canvas.width/2 + Math.sin(time + i) * 200;
                const y = canvas.height/2 + Math.cos(time * 0.5 + i) * 200;
                ctx.arc(x, y, 300, 0, Math.PI * 2);
                ctx.fillStyle = i === 0 ? '#22d3ee' : (i === 1 ? '#a855f7' : '#1e293b');
                ctx.fill();
            }
            requestAnimationFrame(drawCircles);
        }
        drawCircles();

        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });
    </script>
</body>
</html>
