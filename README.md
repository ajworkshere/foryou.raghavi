
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For You - A Story Worth Telling</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', serif;
            line-height: 1.6;
            color: #333;
            background: 
                radial-gradient(circle at 20% 50%, rgba(255, 102, 102, 0.4) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(102, 126, 234, 0.4) 0%, transparent 50%),
                radial-gradient(circle at 40% 80%, rgba(255, 183, 197, 0.4) 0%, transparent 50%),
                radial-gradient(circle at 0% 100%, rgba(255, 107, 107, 0.3) 0%, transparent 50%),
                radial-gradient(circle at 80% 100%, rgba(138, 43, 226, 0.3) 0%, transparent 50%),
                radial-gradient(circle at 40% 30%, rgba(255, 20, 147, 0.2) 0%, transparent 50%),
                linear-gradient(135deg, #ff6b6b 0%, #feca57 25%, #ff9ff3 50%, #54a0ff 75%, #5f27cd 100%);
            min-height: 100vh;
            animation: gradientShift 15s ease infinite;
            background-size: 400% 400%;
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            25% { background-position: 100% 50%; }
            50% { background-position: 100% 100%; }
            75% { background-position: 0% 100%; }
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                radial-gradient(2px 2px at 20px 30px, rgba(255, 255, 255, 0.4), transparent),
                radial-gradient(2px 2px at 40px 70px, rgba(255, 107, 107, 0.3), transparent),
                radial-gradient(1px 1px at 90px 40px, rgba(84, 160, 255, 0.4), transparent),
                radial-gradient(1px 1px at 130px 80px, rgba(255, 159, 243, 0.3), transparent),
                radial-gradient(2px 2px at 160px 30px, rgba(254, 202, 87, 0.4), transparent);
            background-repeat: repeat;
            background-size: 200px 100px;
            animation: sparkle 20s linear infinite;
            pointer-events: none;
            z-index: 1;
        }

        @keyframes sparkle {
            0% { transform: translateY(0px); }
            100% { transform: translateY(-100px); }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 2;
        }

        nav {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            box-shadow: 0 8px 32px rgba(31, 38, 135, 0.37);
        }

        nav .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 20px;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #667eea;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-menu a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-menu a:hover,
        .nav-menu a.active {
            color: #667eea;
        }

        .mobile-menu-toggle {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
        }

        .page-section {
            display: none;
            min-height: 100vh;
            padding: 100px 0 50px;
            animation: fadeIn 0.8s ease-in-out;
        }

        .page-section.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .page-content {
            background: rgba(255, 255, 255, 0.25);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 20px;
            padding: 50px;
            box-shadow: 0 8px 32px rgba(31, 38, 135, 0.37);
            position: relative;
            overflow: hidden;
        }

        .page-content::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            animation: shimmerContent 4s ease infinite;
            pointer-events: none;
        }

        @keyframes shimmerContent {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }

        h1 {
            color: #fff;
            font-size: 3rem;
            margin-bottom: 1rem;
            text-align: center;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            background: linear-gradient(45deg, #ff6b6b, #feca57, #ff9ff3, #54a0ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: colorFlow 3s ease-in-out infinite;
        }

        @keyframes colorFlow {
            0%, 100% { filter: hue-rotate(0deg); }
            50% { filter: hue-rotate(180deg); }
        }

        h2 {
            color: #764ba2;
            font-size: 2rem;
            margin-bottom: 1.5rem;
        }

        h3 {
            color: #667eea;
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        p {
            font-size: 1.1rem;
            margin-bottom: 1.5rem;
            color: #555;
        }

        .hero {
            text-align: center;
            padding: 50px 0;
        }

        .hero h1 {
            font-size: 4rem;
            background: linear-gradient(45deg, #ff6b6b, #feca57, #ff9ff3, #54a0ff, #5f27cd);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 2rem;
            text-shadow: 0 0 30px rgba(255, 107, 107, 0.5);
            animation: glow 2s ease-in-out infinite alternate, float 3s ease-in-out infinite;
        }

        @keyframes glow {
            from { text-shadow: 0 0 20px rgba(255, 107, 107, 0.5), 0 0 30px rgba(255, 107, 107, 0.5), 0 0 40px rgba(255, 107, 107, 0.5); }
            to { text-shadow: 0 0 30px rgba(84, 160, 255, 0.8), 0 0 40px rgba(84, 160, 255, 0.8), 0 0 50px rgba(84, 160, 255, 0.8); }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .hero-subtitle {
            font-size: 1.5rem;
            color: #666;
            margin-bottom: 3rem;
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(45deg, #ff6b6b, #feca57, #ff9ff3, #54a0ff);
            background-size: 300% 300%;
            color: white;
            padding: 15px 30px;
            border-radius: 25px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            animation: gradientMove 3s ease infinite;
            box-shadow: 0 0 20px rgba(255, 107, 107, 0.4);
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
        }

        @keyframes gradientMove {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .cta-button:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 10px 30px rgba(255, 107, 107, 0.6);
            animation: gradientMove 1s ease infinite, pulse 0.5s ease infinite;
        }

        @keyframes pulse {
            0%, 100% { box-shadow: 0 10px 30px rgba(255, 107, 107, 0.6); }
            50% { box-shadow: 0 10px 40px rgba(84, 160, 255, 0.8); }
        }

        .effort-showcase {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 30px;
            margin: 30px 0;
            border: 2px solid rgba(255, 107, 107, 0.3);
        }

        .effort-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .stat-card {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            transition: transform 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-5px) scale(1.05);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            margin-bottom: 10px;
            animation: countUp 2s ease-out;
        }

        @keyframes countUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }

        .timeline::after {
            content: '';
            position: absolute;
            width: 4px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -2px;
            animation: timelineGlow 3s ease-in-out infinite;
        }

        @keyframes timelineGlow {
            0%, 100% { box-shadow: 0 0 10px rgba(102, 126, 234, 0.5); }
            50% { box-shadow: 0 0 20px rgba(118, 75, 162, 0.8); }
        }

        .timeline-item {
            padding: 10px 40px;
            position: relative;
            background-color: inherit;
            width: 50%;
            margin-bottom: 30px;
            animation: slideIn 0.8s ease-out;
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateX(-50px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .timeline-item::after {
            content: '';
            position: absolute;
            width: 25px;
            height: 25px;
            right: -17px;
            background: #667eea;
            border: 4px solid white;
            top: 15px;
            border-radius: 50%;
            animation: heartbeat 2s ease-in-out infinite;
        }

        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        .timeline-item:nth-child(even) {
            left: 50%;
        }

        .timeline-item:nth-child(even)::after {
            left: -16px;
        }

        .timeline-item:nth-child(even) {
            animation: slideInRight 0.8s ease-out;
        }

        @keyframes slideInRight {
            from { opacity: 0; transform: translateX(50px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .timeline-content {
            padding: 20px 30px;
            background: white;
            position: relative;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .timeline-content:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
        }

        .timeline-date {
            color: #667eea;
            font-weight: bold;
            margin-bottom: 10px;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .feelings-section {
            background: linear-gradient(135deg, rgba(255, 107, 107, 0.1), rgba(84, 160, 255, 0.1));
            border-radius: 20px;
            padding: 40px;
            margin: 40px 0;
            border: 2px solid rgba(255, 107, 107, 0.2);
            position: relative;
            overflow: hidden;
        }

        .feelings-section::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.05), transparent);
            animation: feelingsShimmer 6s ease infinite;
            pointer-events: none;
        }

        @keyframes feelingsShimmer {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }

        .letter {
            background: linear-gradient(135deg, #f8f9fa, #fff);
            border-left: 5px solid #667eea;
            padding: 40px;
            margin: 30px 0;
            border-radius: 0 15px 15px 0;
            font-style: italic;
            font-size: 1.2rem;
            line-height: 1.8;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            position: relative;
        }

        .letter::before {
            content: '💌';
            position: absolute;
            top: -10px;
            right: 20px;
            font-size: 2rem;
            animation: bounce 2s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .response-section {
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1), rgba(118, 75, 162, 0.1));
            border-radius: 15px;
            padding: 40px;
            margin-top: 40px;
            text-align: center;
            border: 2px solid rgba(102, 126, 234, 0.2);
        }

        .contact-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .contact-btn {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 25px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
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
            background: linear-gradient(120deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: left 0.5s ease;
        }

        .contact-btn:hover::before {
            left: 100%;
        }

        .contact-btn:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 15px 25px rgba(102, 126, 234, 0.4);
        }

        .fade-in {
            animation: fadeInUp 0.8s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .floating {
            animation: floating 3s ease-in-out infinite;
        }

        @keyframes floating {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .highlight-text {
            background: linear-gradient(120deg, rgba(255, 107, 107, 0.3), rgba(84, 160, 255, 0.3));
            padding: 2px 8px;
            border-radius: 5px;
            font-weight: bold;
        }

        .confession-box {
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.9), rgba(255, 255, 255, 0.7));
            border: 3px solid rgba(255, 107, 107, 0.3);
            border-radius: 20px;
            padding: 30px;
            margin: 30px 0;
            text-align: center;
            position: relative;
            animation: confessionGlow 3s ease-in-out infinite;
        }

        @keyframes confessionGlow {
            0%, 100% { box-shadow: 0 0 20px rgba(255, 107, 107, 0.3); }
            50% { box-shadow: 0 0 40px rgba(84, 160, 255, 0.4); }
        }

        @media (max-width: 768px) {
            .nav-menu {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background: rgba(255, 255, 255, 0.95);
                backdrop-filter: blur(10px);
                flex-direction: column;
                padding: 20px;
                box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            }

            .nav-menu.active {
                display: flex;
            }

            .mobile-menu-toggle {
                display: block;
            }

            .page-content {
                padding: 30px 20px;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .timeline::after {
                left: 31px;
            }

            .timeline-item {
                width: 100%;
                padding-left: 70px;
                padding-right: 25px;
            }

            .timeline-item::after {
                left: 15px;
            }

            .timeline-item:nth-child(even) {
                left: 0%;
            }

            .contact-buttons {
                flex-direction: column;
                align-items: center;
            }

            .letter {
                padding: 25px;
                font-size: 1.1rem;
            }
        }
    </style>
</head>
<body>
    <nav>
        <div class="container">
            <div class="logo">💖 For Raghavi</div>
            <ul class="nav-menu">
                <li><a href="#home" class="nav-link active">Home</a></li>
                <li><a href="#effort" class="nav-link">My Journey</a></li>
                <li><a href="#meeting" class="nav-link">Our Beginning</a></li>
                <li><a href="#feelings" class="nav-link">My Heart</a></li>
                <li><a href="#letter" class="nav-link">My Letter</a></li>
            </ul>
            <button class="mobile-menu-toggle">☰</button>
        </div>
    </nav>

    <!-- Home Section -->
    <section id="home" class="page-section active">
        <div class="container">
            <div class="page-content">
                <div class="hero">
                    <h1 class="floating">Raghavi, This is For You</h1>
                    <p class="hero-subtitle">I spent a whole night learning coding because you deserve something extraordinary</p>
                    
                    <div class="confession-box">
                        <p style="font-size: 1.3rem; color: #333; margin-bottom: 0;">Hi Raghavi, I know this might seem unconventional, but I wanted to create something special that shows you exactly how I feel and how much effort I'm willing to put in for someone as amazing as you.</p>
                    </div>
                    
                    <p>I could have just walked up to you and asked you out with a simple "Hey, want to grab coffee?" But you're not just anyone, Raghavi. You're someone who deserves to know that when I like someone, I don't do things halfway.</p>
                    
                    <p>So instead of a casual approach, I spent sleepless nights learning HTML, CSS, and JavaScript. I tried countless ideas, themes, debugged code until 6 AM, and redesigned this website probably 50 times – all because I wanted to create something as unique and special as you are.</p>
                    
                    <a href="#effort" class="cta-button nav-link">See My Journey</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Effort Section -->
    <section id="effort" class="page-section">
        <div class="container">
            <div class="page-content fade-in">
                <h1>The Journey I Took For You</h1>
                
                <div class="effort-showcase">
                    <h3>🚀 From Zero to This Website</h3>
                    <p>Just one night ago, I knew absolutely nothing about web development. The most "coding" I had ever done was changing my social media bio. But after meeting you, I was determined to create something that would show you how serious I am about getting to know you better.</p>
                    <p>So I started from scratch. <span class="highlight-text">I literally Googled "how to make a website"</span> and began one of the most challenging yet rewarding nights I've ever had.</p>
                </div>

                <div class="effort-stats">
                    <div class="stat-card">
                        <div class="stat-number">12+</div>
                        <div>Hours Straight</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">1,247</div>
                        <div>Lines of Code</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">47</div>
                        <div>YouTube Tutorials</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">1</div>
                        <div>Amazing Girl</div>
                    </div>
                </div>

                <div class="effort-showcase">
                    <h3>📚 What I Had to Learn (In One Night!)</h3>
                    <p><strong>Hours 1-3:</strong> Basic HTML - I spent hours just learning how to make text appear on a webpage. My first "Hello World" felt like climbing Mount Everest.</p>
                    <p><strong>Hours 4-8:</strong> CSS Styling - This is where I learned about colors, animations, and layouts. I probably spent 2 more hours just getting the background gradient right because I wanted it to be perfect for you.</p>
                    <p><strong>Hours 9-12:</strong> JavaScript & Interactivity - Navigation, smooth scrolling, mobile responsiveness... I learned it all while thinking about you.</p>
                    
                    <h3>⏰ The All-Nighter I Pulled</h3>
                    <p>While everyone else was sleeping, I was here at my desk with multiple monitors, energy drinks, and a head full of thoughts about you. Every error message I debugged, every animation I perfected, every word I wrote - it was all done with the hope that you'd see how much you mean to me.</p>
                    
                    <p><span class="highlight-text">I've never stayed up all night learning something for someone before</span>, and honestly, that tells me everything I need to know about how I feel about you.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Meeting Section -->
    <section id="meeting" class="page-section">
        <div class="container">
            <div class="page-content fade-in">
                <h1>The Day Everything Changed</h1>
                <p style="text-align: center; margin-bottom: 50px; font-style: italic; font-size: 1.3rem;">The day I met you and knew I had to do something special</p>
                
                <div class="timeline">
                    <div class="timeline-item">
                        <div class="timeline-content">
                            <div class="timeline-date">Before You</div>
                            <h3>Just Another Day</h3>
                            <p>I was having the most ordinary day. Just going through my routine classes, thinking about assignments, maybe grabbing some food later. I had no idea that someone was about to completely change my perspective on everything and inspire me to learn an entire programming language in one night.</p>
                        </div>
                    </div>
                    
                    <div class="timeline-item">
                        <div class="timeline-content">
                            <div class="timeline-date">The Moment</div>
                            <h3>I Saw You</h3>
                            <p>And then there was you, Raghavi. Something about the way you carried yourself, the way you smiled, the way you seemed so genuinely kind and intelligent. I couldn't stop thinking about you, and I knew that if I was going to approach someone as amazing as you, I couldn't do it the ordinary way.</p>
                            <p><span class="highlight-text">That's when I decided to do something extraordinary</span> - something that would show you exactly how much you've already impacted my life.</p>
                        </div>
                    </div>
                    
                    <div class="timeline-item">
                        <div class="timeline-content">
                            <div class="timeline-date">The Decision</div>
                            <h3>Learning to Code</h3>
                            <p>I went home that day and made a decision that surprised even me. Instead of just asking for your number like everyone else probably does, I was going to create something unique. I was going to build you a website from scratch.</p>
                            <p>I had <span class="highlight-text">zero coding experience</span>, but I had determination and an entire night ahead of me. I thought, "If Raghavi is worth it (and she absolutely is), then she's worth learning something completely new."</p>
                        </div>
                    </div>
                    
                    <div class="timeline-item">
                        <div class="timeline-content">
                            <div class="timeline-date">Right Now</div>
                            <h3>Here We Are</h3>
                            <p>After 12 straight hours of learning, coding, debugging, and probably consuming way too much caffeine, here we are. This website exists because you inspired me to push myself beyond what I thought was possible.</p>
                            <p>I hope when you see this, you understand that this isn't just about the code or the website - it's about showing you that you're worth the effort, worth the sleepless night, and worth taking a chance on something completely new.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Feelings Section -->
    <section id="feelings" class="page-section">
        <div class="container">
            <div class="page-content fade-in">
                <h1>What You
