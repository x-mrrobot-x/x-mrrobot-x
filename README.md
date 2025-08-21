<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>x-mrrobot-x Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #000000;
            color: #00FF00;
            font-family: 'Courier New', monospace;
            overflow-x: hidden;
            line-height: 1.6;
        }

        .matrix-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.3;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
            padding: 20px;
            border: 2px solid #00FF00;
            border-radius: 10px;
            background: rgba(0, 0, 0, 0.8);
        }

        .ascii-art {
            font-size: 10px;
            line-height: 1;
            color: #00FF00;
            white-space: pre;
            overflow-x: auto;
            margin-bottom: 20px;
            text-shadow: 0 0 5px #00FF00;
        }

        .typing-text {
            font-size: 18px;
            margin: 20px 0;
            color: #00F5A0;
            text-shadow: 0 0 10px #00F5A0;
        }

        .badges {
            display: flex;
            justify-content: center;
            gap: 10px;
            flex-wrap: wrap;
            margin: 20px 0;
        }

        .badge {
            background: #000;
            border: 1px solid #00FF00;
            padding: 5px 10px;
            border-radius: 5px;
            text-decoration: none;
            color: #00FF00;
            transition: all 0.3s ease;
            font-size: 12px;
        }

        .badge:hover {
            background: #00FF00;
            color: #000;
            box-shadow: 0 0 15px #00FF00;
        }

        .section {
            margin: 40px 0;
            padding: 20px;
            border: 1px solid #00FF00;
            border-radius: 10px;
            background: rgba(0, 20, 0, 0.3);
        }

        .section h2 {
            color: #00FF00;
            margin-bottom: 20px;
            text-align: center;
            font-size: 24px;
            text-shadow: 0 0 10px #00FF00;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            gap: 10px;
            margin: 20px 0;
        }

        .tech-item {
            background: #000;
            border: 1px solid #00FF00;
            padding: 10px;
            text-align: center;
            border-radius: 5px;
            font-size: 12px;
            transition: all 0.3s ease;
        }

        .tech-item:hover {
            background: #00FF00;
            color: #000;
            transform: scale(1.05);
        }

        .code-block {
            background: #001100;
            border: 1px solid #00FF00;
            padding: 20px;
            border-radius: 10px;
            margin: 20px 0;
            overflow-x: auto;
            font-family: 'Courier New', monospace;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 20px 0;
        }

        .project-card {
            background: rgba(0, 20, 0, 0.5);
            border: 1px solid #00FF00;
            padding: 20px;
            border-radius: 10px;
            transition: all 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 255, 0, 0.2);
        }

        .terminal {
            background: #000;
            border: 2px solid #00FF00;
            padding: 20px;
            border-radius: 10px;
            margin: 20px 0;
            font-family: 'Courier New', monospace;
        }

        .terminal-line {
            margin: 5px 0;
        }

        .prompt {
            color: #00FF00;
        }

        .output {
            color: #00F5A0;
            margin-left: 20px;
        }

        .footer {
            text-align: center;
            margin: 40px 0;
            padding: 20px;
            border-top: 2px solid #00FF00;
        }

        .glow {
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { text-shadow: 0 0 5px #00FF00; }
            to { text-shadow: 0 0 20px #00FF00, 0 0 30px #00FF00; }
        }

        .fade-in {
            animation: fadeIn 2s ease-in;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @media (max-width: 768px) {
            .ascii-art {
                font-size: 8px;
            }
            
            .tech-grid {
                grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <canvas class="matrix-canvas" id="matrixCanvas"></canvas>
    
    <div class="container">
        <div class="header fade-in">
            <div class="ascii-art glow">┌─────────────────────────────────────────────────────────────────┐
│  ██╗  ██╗      ███╗   ███╗██████╗ ██████╗  ██████╗ ██████╗  ██████╗ ████████╗   │
│  ╚██╗██╔╝      ████╗ ████║██╔══██╗██╔══██╗██╔═══██╗██╔══██╗██╔═══██╗╚══██╔══╝   │  
│   ╚███╔╝ █████╗██╔████╔██║██████╔╝██████╔╝██║   ██║██████╔╝██║   ██║   ██║      │
│   ██╔██╗ ╚════╝██║╚██╔╝██║██╔══██╗██╔══██╗██║   ██║██╔══██╗██║   ██║   ██║      │
│  ██╔╝ ██╗      ██║ ╚═╝ ██║██║  ██║██║  ██║╚██████╔╝██████╔╝╚██████╔╝   ██║      │
│  ╚═╝  ╚═╝      ╚═╝     ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝ ╚═════╝  ╚═════╝    ╚═╝      │
└─────────────────────────────────────────────────────────────────┘</div>
            
            <div class="typing-text glow">
                > Full Stack Developer<br>
                > Tasker Automation Specialist<br>
                > Knowledge Sharing Enthusiast
            </div>
            
            <div class="badges">
                <span class="badge">MATRIX</span>
                <span class="badge">ANDROID</span>
                <span class="badge">AUTOMATION</span>
            </div>
        </div>

        <div class="section fade-in">
            <div class="terminal">
                <div class="terminal-line">
                    <span class="prompt">$</span> whoami
                </div>
                <div class="output">
                    > Full Stack Developer | Tasker Automation Expert<br>
                    > Instructor @ Tasker Super Brasil Community<br>
                    > Code Architect | Knowledge Distributor
                </div>
            </div>
        </div>

        <div class="section fade-in">
            <h2 class="glow">[ TECH.STACK ]</h2>
            <div class="tech-grid">
                <div class="tech-item">JavaScript</div>
                <div class="tech-item">HTML5</div>
                <div class="tech-item">CSS3</div>
                <div class="tech-item">Vue.js</div>
                <div class="tech-item">React</div>
                <div class="tech-item">Node.js</div>
                <div class="tech-item">SQL</div>
                <div class="tech-item">Tasker</div>
                <div class="tech-item">Android</div>
            </div>
        </div>

        <div class="section fade-in">
            <h2 class="glow">[ PROJECTS.DEPLOY ]</h2>
            <div class="code-block">
<span style="color: #FF6B6B;">const</span> <span style="color: #4FC08D;">featuredProjects</span> = {
  <span style="color: #E2C08D;">automation</span>: {
    <span style="color: #82AAFF;">"file-picker"</span>: {
      <span style="color: #C3E88D;">description</span>: <span style="color: #C3E88D;">"🗂️ Advanced folder browser and file picker"</span>,
      <span style="color: #C3E88D;">tech</span>: [<span style="color: #C3E88D;">"JavaScript"</span>, <span style="color: #C3E88D;">"Android Integration"</span>],
      <span style="color: #C3E88D;">status</span>: <span style="color: #C3E88D;">"⭐ Active Development"</span>
    },
    <span style="color: #82AAFF;">"routine-flow"</span>: {
      <span style="color: #C3E88D;">description</span>: <span style="color: #C3E88D;">"⚡ Intelligent routine management system"</span>,
      <span style="color: #C3E88D;">tech</span>: [<span style="color: #C3E88D;">"JavaScript"</span>, <span style="color: #C3E88D;">"Workflow Automation"</span>],
      <span style="color: #C3E88D;">status</span>: <span style="color: #C3E88D;">"🔥 Production Ready"</span>
    }
  }
}
            </div>
            
            <div class="stats-grid">
                <div class="project-card">
                    <h3 style="color: #00FF00;">📁 file-picker</h3>
                    <p>Advanced folder browser and file picker for Android automation</p>
                </div>
                <div class="project-card">
                    <h3 style="color: #00FF00;">⚡ routine-flow</h3>
                    <p>Intelligent routine management system with workflow automation</p>
                </div>
            </div>
        </div>

        <div class="section fade-in">
            <h2 class="glow">[ MISSION.STATEMENT ]</h2>
            <div class="terminal">
                <div class="terminal-line">
                    <span class="prompt">></span> INITIALIZING CORE OBJECTIVES...
                </div>
                <div class="terminal-line">
                    <span class="prompt">></span> 
                </div>
                <div class="output">
                    [✓] Share knowledge freely within the community<br>
                    [✓] Develop innovative automation solutions<br>
                    [✓] Build tools that simplify complex workflows<br>
                    [✓] Foster learning in Tasker Super Brasil<br>
                    [✓] Create efficient, scalable code architectures
                </div>
                <div class="terminal-line">
                    <span class="prompt">></span>
                </div>
                <div class="output">
                    MISSION STATUS: ACTIVE | IMPACT: MAXIMIZING
                </div>
            </div>
        </div>

        <div class="section fade-in">
            <h2 class="glow">[ NETWORK.CONNECT ]</h2>
            <div class="terminal">
                <div class="terminal-line">
                    <span class="prompt">$</span> echo "Building the future, one automation at a time"
                </div>
                <div class="output">
                    > "Code is poetry, automation is art" - x-mrrobot-x
                </div>
            </div>
        </div>

        <div class="footer fade-in">
            <div class="ascii-art glow">┌─────────────────────────────────────────────────────────────────┐
│                     ~ END OF TRANSMISSION ~                     │
│                    [CONNECTION TERMINATED]                      │
└─────────────────────────────────────────────────────────────────┘</div>
        </div>
    </div>

    <script>
        // Matrix falling text effect
        const canvas = document.getElementById('matrixCanvas');
        const ctx = canvas.getContext('2d');

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        const text = 'x-mrrobot-x';
        const fontSize = 16;
        const columns = canvas.width / fontSize;

        const drops = [];
        for (let x = 0; x < columns; x++) {
            drops[x] = 1;
        }

        function drawMatrix() {
            ctx.fillStyle = 'rgba(0, 0, 0, 0.05)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            ctx.fillStyle = '#00FF00';
            ctx.font = fontSize + 'px monospace';

            for (let i = 0; i < drops.length; i++) {
                const char = text[Math.floor(Math.random() * text.length)];
                ctx.fillText(char, i * fontSize, drops[i] * fontSize);

                if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                    drops[i] = 0;
                }
                drops[i]++;
            }
        }

        setInterval(drawMatrix, 35);

        // Resize canvas on window resize
        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });

        // Animate elements on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            el.style.transition = 'all 0.8s ease';
            observer.observe(el);
        });
    </script>
</body>
</html>
