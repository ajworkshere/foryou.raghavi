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
            line-height: 1.5;
            color: #333;
            background: 
                radial-gradient(circle at 20% 50%, rgba(255, 102, 102, 0.4) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(102, 126, 234, 0.4) 0%, transparent 50%),
                radial-gradient(circle at 40% 80%, rgba(255, 183, 197, 0.4) 0%, transparent 50%),
                linear-gradient(135deg, #ff6b6b 0%, #feca57 25%, #ff9ff3 50%, #54a0ff 75%, #5f27cd 100%);
            min-height: 100vh;
            animation: gradientShift 15s ease infinite;
            background-size: 400% 400%;
            overflow-x: hidden;
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
                radial-gradient(1px 1px at 40px 70px, rgba(255, 107, 107, 0.3), transparent),
                radial-gradient(1px 1px at 90px 40px, rgba(84, 160, 255, 0.4), transparent);
            background-repeat: repeat;
            background-size: 150px 80px;
            animation: sparkle 20s linear infinite;
            pointer-events: none;
            z-index: 1;
        }

        @keyframes sparkle {
            0% { transform: translateY(0px); }
            100% { transform: translateY(-80px); }
        }

        .container {
            max-width: 100%;
            margin: 0 auto;
            padding: 0 15px;
            position: relative;
            z-index: 2;
        }

        .page-content {
            background: rgba(255, 255, 255, 0.25);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 15px;
            padding: 25px 20px;
            box-shadow: 0 8px 32px rgba(31, 38, 135, 0.37);
            position: relative;
            overflow: hidden;
            margin: 20px 10px;
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
            font-size: 2.2rem;
            margin-bottom: 1rem;
            text-align: center;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            background: linear-gradient(45deg, #ff6b6b, #feca57, #ff9ff3, #54a0ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: colorFlow 3s ease-in-out infinite;
            line-height: 1.2;
        }

        @keyframes colorFlow {
            0%, 100% { filter: hue-rotate(0deg); }
            50% { filter: hue-rotate(180deg); }
        }

        p {
            font-size: 1rem;
            margin-bottom: 1.2rem;
            color: #555;
            text-align: left;
        }

        .hero {
            text-align: center;
            padding: 40px 0;
        }

        .hero h1 {
            font-size: 2.5rem;
            background: linear-gradient(45deg, #ff6b6b, #feca57, #ff9ff3, #54a0ff, #5f27cd);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 1.5rem;
            text-shadow: 0 0 30px rgba(255, 107, 107, 0.5);
            animation: glow 2s ease-in-out infinite alternate, float 3s ease-in-out infinite;
        }

        @keyframes glow {
            from { text-shadow: 0 0 20px rgba(255, 107, 107, 0.5); }
            to { text-shadow: 0 0 30px rgba(84, 160, 255, 0.8); }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-8px); }
        }

        .hero-subtitle {
            font-size: 1.1rem;
            color: #666;
            margin-bottom: 2rem;
            padding: 0 10px;
        }

        .floating {
            animation: floating 3s ease-in-out infinite;
        }

        @keyframes floating {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-8px); }
        }

        .highlight-text {
            background: linear-gradient(120deg, rgba(255, 107, 107, 0.3), rgba(84, 160, 255, 0.3));
            padding: 2px 6px;
            border-radius: 4px;
            font-weight: bold;
        }

        .confession-box {
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.9), rgba(255, 255, 255, 0.7));
            border: 2px solid rgba(255, 107, 107, 0.3);
            border-radius: 15px;
            padding: 20px;
            margin: 20px 0;
            text-align: center;
            position: relative;
            animation: confessionGlow 3s ease-in-out infinite;
        }

        @keyframes confessionGlow {
            0%, 100% { box-shadow: 0 0 15px rgba(255, 107, 107, 0.3); }
            50% { box-shadow: 0 0 25px rgba(84, 160, 255, 0.4); }
        }

        .confession-box p {
            font-size: 1.1rem;
            color: #333;
            margin-bottom: 0;
        }

        /* Mobile optimizations */
        @media (max-width: 480px) {
            .hero h1 {
                font-size: 2rem;
            }

            h1 {
                font-size: 1.8rem;
            }

            .page-content {
                margin: 10px 5px;
                padding: 20px 15px;
            }

            .confession-box p {
                font-size: 1rem;
            }

            .hero {
                padding: 20px 0;
            }
        }

        /* Ultra-small screens */
        @media (max-width: 360px) {
            .hero h1 {
                font-size: 1.8rem;
            }

            h1 {
                font-size: 1.6rem;
            }

            .page-content {
                padding: 15px 12px;
            }
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(45deg, #ff6b6b, #feca57, #ff9ff3, #54a0ff);
            background-size: 300% 300%;
            color: white;
            padding: 12px 25px;
            border-radius: 25px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            animation: gradientMove 3s ease infinite;
            box-shadow: 0 0 20px rgba(255, 107, 107, 0.4);
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
            font-size: 0.9rem;
            cursor: pointer;
            border: none;
            margin: 8px;
            min-width: 200px;
        }

        @keyframes gradientMove {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .cta-button:hover {
            transform: translateY(-2px) scale(1.05);
            box-shadow: 0 8px 25px rgba(255, 107, 107, 0.6);
        }

        .contact-section {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
            margin-top: 30px;
        }

        @media (max-width: 480px) {
            .cta-button {
                font-size: 0.85rem;
                padding: 10px 20px;
                min-width: 180px;
            }
        }

        /* Prevent horizontal scroll */
        html, body {
            overflow-x: hidden;
            width: 100%;
        }

        * {
            max-width: 100%;
        }
    </style>
</head>
<body>
    <!-- Home Section -->
    <section id="home">
        <div class="container">
            <div class="page-content">
                <div class="hero">
                    <h1 class="floating">Raghavi, This is For You</h1>
                    <p class="hero-subtitle">I spent a whole night learning coding because you deserve something extraordinary</p>
                    
                    <div class="confession-box">
                        <p>Hi Raghavi, I know this might seem unconventional, but I wanted to create something special that shows you exactly how I feel and how much effort I'm willing to put in for someone as amazing as you.</p>
                    </div>
                    
                    <p>I could have just walked up to you and asked you out with a simple "Hey, want to grab coffee?" But you're not just anyone, Raghavi. You're someone who deserves to know that when I like someone, I don't do things halfway.</p>
                    
                    <p>So instead of a casual approach, I spent sleepless nights learning HTML, CSS, and JavaScript. I tried countless ideas, themes, debugged code until 6 AM, and redesigned this website probably 50 times – all because I wanted to create something as unique and special as you are.</p>
                    
                    <p>This website represents more than just code - it represents dedication, genuine interest, and the belief that extraordinary people deserve extraordinary gestures. <span class="highlight-text">You inspired me to learn something completely new in one night</span>, and that says everything about how I feel about you.</p>
                    
                    <p>I hope this shows you that I'm serious about getting to know you better, and that you're worth every hour I spent learning to create this for you.</p>
                    
                    <p>I hope you'll accept my invitation to meet for coffee. I'd love to get to know you better.</p>
                    
                    <div class="contact-section">
                        <a href="tel:+919006291057" class="cta-button">📱 Call Me: 79006291057</a>
                        <a href="sms:+919006291057" class="cta-button">💬 Text Me: 79006291057</a>
                    </div>
                </div>
            </div>
        </div>
    </section>
</body>
</html>
