<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pixel Forge · Sakib Hasan</title>
    <!-- Google Fonts + Pixelated vibe -->
    <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            image-rendering: pixelated;
            image-rendering: crisp-edges;
        }
        body {
            background: #0c0b1a; /* deep night */
            font-family: 'Space Mono', monospace;
            color: #a0f0e0;
            display: flex;
            justify-content: center;
            padding: 16px 12px;
            line-height: 1.5;
            text-shadow: 0 0 5px #00ccaa80;
        }
        .pixel-container {
            max-width: 1100px;
            width: 100%;
            border: 4px solid #4af0c0;
            box-shadow: 0 0 0 2px #0f3f3a, 0 0 0 6px #1e2a3a, 0 0 20px #00ffc3;
            background: #0f121c;
            padding: 24px 20px;
            position: relative;
            animation: flicker 8s infinite;
        }
        /* scanlines & crt effect */
        .pixel-container::before {
            content: "";
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: repeating-linear-gradient(0deg, rgba(0,255,200,0.03) 0px, rgba(0,0,0,0.2) 2px, transparent 3px);
            pointer-events: none;
            z-index: 2;
        }
        .pixel-container::after {
            content: "";
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle at 50% 50%, #00ffe050 0%, transparent 80%);
            opacity: 0.1;
            pointer-events: none;
        }
        @keyframes flicker {
            0% { opacity: 0.98; }
            2% { opacity: 1; }
            4% { opacity: 0.97; }
            96% { opacity: 1; }
            98% { opacity: 0.95; }
            100% { opacity: 0.99; }
        }
        h1, h2, h3 {
            font-family: 'Press Start 2P', cursive;
            color: #f0f4a0;
            text-shadow: 3px 3px 0 #2d5a5a, 5px 5px 0 #0f3f3a;
            letter-spacing: 1px;
            word-break: break-word;
        }
        h2 {
            font-size: 1.2rem;
            margin: 32px 0 16px 0;
            border-bottom: 4px solid #3bc0b0;
            display: inline-block;
            padding-bottom: 6px;
        }
        .badge-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 8px 12px;
            justify-content: center;
            margin: 20px 0 10px;
        }
        .badge-pixel {
            background: #1a2a32;
            border: 2px solid #5af0d0;
            color: #c0ffee;
            padding: 8px 12px;
            font-size: 0.75rem;
            font-family: 'Press Start 2P', cursive;
            text-transform: uppercase;
            text-decoration: none;
            box-shadow: inset -2px -2px 0 #0a1f1f, inset 2px 2px 0 #9fffe0;
            transition: 0.1s linear;
            display: inline-flex;
            align-items: center;
            gap: 6px;
        }
        .badge-pixel:hover {
            background: #2f4f4f;
            border-color: #f0ffb0;
            transform: translate(2px, 2px);
            box-shadow: inset -1px -1px 0 #0a1f1f;
        }
        .badge-pixel img, .badge-pixel svg {
            width: 18px;
            height: 18px;
            image-rendering: pixelated;
            filter: drop-shadow(0 0 4px #aaffdd);
        }
        /* terminal-style typing header */
        .crt-header {
            background: #0a141c;
            border: 3px solid #3caa9a;
            padding: 16px;
            margin-bottom: 24px;
            box-shadow: inset 0 0 20px #1f4a4a;
            font-family: 'Space Mono', monospace;
        }
        .typewriter {
            font-size: 1.3rem;
            color: #b4ffe0;
            text-shadow: 0 0 8px #00e6b0;
            overflow: hidden;
            white-space: nowrap;
            border-right: 3px solid #a0ffc0;
            animation: typing 5s steps(40, end), blink-caret 0.75s step-end infinite;
            width: fit-content;
            max-width: 100%;
        }
        @keyframes typing {
            from { width: 0; }
            to { width: 100%; }
        }
        @keyframes blink-caret {
            from, to { border-color: transparent; }
            50% { border-color: #a0ffc0; }
        }
        .skill-icon-row {
            display: flex;
            flex-wrap: wrap;
            gap: 16px;
            align-items: center;
            justify-content: center;
            margin: 15px 0;
        }
        .pixel-icon {
            background: #1d2d2d;
            border: 2px solid #2f9f9f;
            width: 64px;
            height: 64px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            image-rendering: pixelated;
            box-shadow: 3px 3px 0 #062020;
        }
        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 20px;
            margin: 20px 0;
        }
        .project-card {
            background: #142026;
            border: 3px solid #2dbbaa;
            padding: 18px 12px;
            box-shadow: 5px 5px 0 #0b3535;
            transition: 0.1s;
        }
        .project-card:hover {
            border-color: #fdffb0;
            box-shadow: 2px 2px 0 #aaffdd, 0 0 18px #6fffd0;
        }
        .project-card h3 {
            font-size: 0.9rem;
            margin-bottom: 12px;
            color: #fcf9b0;
        }
        .pixel-tag {
            background: #1e3a3a;
            border: 1px solid #2ac0aa;
            font-size: 0.6rem;
            padding: 4px 8px;
            margin: 2px 4px 2px 0;
            display: inline-block;
            font-family: 'Press Start 2P', cursive;
        }
        .stats-panel {
            background: #0e1b24;
            border: 4px solid #3dc0b0;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            padding: 20px 10px;
            margin: 30px 0;
        }
        .stat-cell {
            font-family: 'Press Start 2P', cursive;
            font-size: 0.8rem;
            color: #f0ffc0;
            background: #1b2d30;
            padding: 15px;
            border: 2px solid #00c0a0;
            min-width: 150px;
            text-align: center;
        }
        hr {
            border: none;
            height: 4px;
            background: linear-gradient(90deg, #2fbbaa, #f0f0a0, #2fbbaa);
            margin: 28px 0;
        }
        footer {
            text-align: center;
            margin-top: 20px;
            font-size: 0.7rem;
            color: #50b0a0;
        }
        .glitch-link {
            color: #8cf0e0;
            text-decoration: none;
            border-bottom: 2px dotted #6fffd0;
        }
        .glitch-link:hover {
            color: #faffa0;
            border-bottom: 2px solid #f0ffa0;
        }
        /* pixel octocat / icons */
        .pixel-octo {
            background: #2f4f4f;
            mask: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="white"><path d="M12 2C6.477 2 2 6.477 2 12c0 4.42 2.865 8.166 6.839 9.489.5.092.682-.217.682-.482 0-.237-.008-.866-.013-1.7-2.782.603-3.369-1.34-3.369-1.34-.454-1.156-1.11-1.462-1.11-1.462-.908-.62.069-.608.069-.608 1.003.07 1.531 1.03 1.531 1.03.892 1.529 2.341 1.087 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.11-4.555-4.943 0-1.091.39-1.984 1.03-2.682-.103-.253-.447-1.27.098-2.646 0 0 .84-.269 2.75 1.025.8-.223 1.65-.334 2.5-.334.85 0 1.7.111 2.5.334 1.91-1.294 2.75-1.025 2.75-1.025.545 1.376.201 2.393.099 2.646.64.698 1.03 1.591 1.03 2.682 0 3.841-2.337 4.687-4.565 4.935.359.309.678.919.678 1.852 0 1.336-.012 2.415-.012 2.743 0 .267.18.578.688.48C19.138 20.161 22 16.418 22 12c0-5.523-4.477-10-10-10z"/></svg>') no-repeat center;
            background-color: #8cf0d0;
        }
    </style>
</head>
<body>
    <div class="pixel-container">
        <!-- HEADER: pixel typing animation -->
        <div class="crt-header">
            <div class="typewriter">> AI/ML ENGINEER // CV RESEARCHER // PIXEL_FUTURE</div>
            <div style="display: flex; gap: 10px; flex-wrap: wrap; justify-content: space-between; margin-top: 15px;">
                <span class="badge-pixel">📍 DHAKA, BANGLADESH</span>
                <span class="badge-pixel">📧 SAKIBMUNSHI013@GMAIL.COM</span>
                <span class="badge-pixel">🔗 @HASAN-SAKIB</span>
            </div>
            <div class="badge-grid">
                <a href="#" class="badge-pixel"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='%2388ffdd'%3E%3Cpath d='M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zM8 12H6v-2h2v2zm3 0H9v-2h2v2zm3 0h-2v-2h2v2zm6-4H4V8h16z'/%3E%3C/svg%3E"> MAIL</a>
                <a href="#" class="badge-pixel"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='%2388ffdd'%3E%3Cpath d='M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z'/%3E%3C/svg%3E"> LINKEDIN</a>
                <a href="#" class="badge-pixel"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='%2388ffdd'%3E%3Cpath d='M12 2C6.477 2 2 6.477 2 12c0 4.42 2.865 8.166 6.839 9.489.5.092.682-.217.682-.482 0-.237-.008-.866-.013-1.7-2.782.603-3.369-1.34-3.369-1.34-.454-1.156-1.11-1.462-1.11-1.462-.908-.62.069-.608.069-.608 1.003.07 1.531 1.03 1.531 1.03.892 1.529 2.341 1.087 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.11-4.555-4.943 0-1.091.39-1.984 1.03-2.682-.103-.253-.447-1.27.098-2.646 0 0 .84-.269 2.75 1.025.8-.223 1.65-.334 2.5-.334.85 0 1.7.111 2.5.334 1.91-1.294 2.75-1.025 2.75-1.025.545 1.376.201 2.393.099 2.646.64.698 1.03 1.591 1.03 2.682 0 3.841-2.337 4.687-4.565 4.935.359.309.678.919.678 1.852 0 1.336-.012 2.415-.012 2.743 0 .267.18.578.688.48C19.138 20.161 22 16.418 22 12c0-5.523-4.477-10-10-10z'/%3E%3C/svg%3E"> GITHUB</a>
                <span class="badge-pixel">👁️ 1337 views</span>
            </div>
        </div>

        <!-- About Me Pixel block -->
        <h2>⏣ ABOUT_ME</h2>
        <div style="background: #0a1620; padding: 20px; border: 2px solid #4ac0b0; font-size: 0.9rem;">
            <p><span style="color:#f0ffa0;">></span> entry-level AI engineer · building intelligent systems with computer vision & self-supervised learning.</p>
            <p><span style="color:#f0ffa0;">></span> seeking 2025 roles in AI/ML, CV, or data science.</p>
            <p><span style="color:#f0ffa0;">></span> fun fact: I convert malware into images to detect them (final year project).</p>
            <p><span style="color:#f0ffa0;">></span> ICCIT 2025 publication · freshwater fish classification via SSL.</p>
        </div>

        <!-- Skills pixelated icons + badges -->
        <h2>⚙️ TECH_STACK</h2>
        <div class="skill-icon-row">
            <div class="pixel-icon">🐍</div>
            <div class="pixel-icon">☕</div>
            <div class="pixel-icon">C</div>
            <div class="pixel-icon">🧠</div>
            <div class="pixel-icon">🔥</div>
            <div class="pixel-icon">📦</div>
        </div>
        <div style="display: flex; flex-wrap: wrap; gap: 6px; justify-content: center;">
            <span class="badge-pixel">PYTORCH</span>
            <span class="badge-pixel">TENSORFLOW</span>
            <span class="badge-pixel">OPENCV</span>
            <span class="badge-pixel">HUGGINGFACE</span>
            <span class="badge-pixel">SCI-KIT</span>
            <span class="badge-pixel">PANDAS</span>
            <span class="badge-pixel">NUMPY</span>
            <span class="badge-pixel">FASTAPI</span>
            <span class="badge-pixel">DOCKER</span>
            <span class="badge-pixel">GIT</span>
            <span class="badge-pixel">JUPYTER</span>
            <span class="badge-pixel">COLAB</span>
        </div>

        <!-- Research / publications -->
        <h2>📄 RESEARCH</h2>
        <div style="border: 3px solid #3bc0b0; padding: 16px; background: #0a2028;">
            <div style="display: flex; align-items: center; gap: 16px; flex-wrap: wrap;">
                <span class="badge-pixel" style="font-size:1rem;">📑 ICCIT 2025</span>
                <span><em>Freshwater Fish Species Classification Using Self-Supervised Learning</em></span>
            </div>
            <p style="margin-top:12px;">+ proposed SSL framework outperforms supervised baselines with limited labels · unlabeled image data · robust visual representations</p>
        </div>

        <!-- Featured projects with pixel cards -->
        <h2>🚀 PROJECTS</h2>
        <div class="project-grid">
            <div class="project-card">
                <h3>MALWARE DETECTION (SSL)</h3>
                <p>Convert EXEs → images · self-supervised learning · Flask webapp + real-time inference</p>
                <div>
                    <span class="pixel-tag">PYTORCH</span>
                    <span class="pixel-tag">FLASK</span>
                    <span class="pixel-tag">OPENCV</span>
                </div>
                <div style="margin-top:12px;"><a href="#" class="glitch-link">[ REPO ]</a> <a href="#" class="glitch-link">[ DEMO ]</a></div>
            </div>
            <div class="project-card">
                <h3>FISH CLASSIFICATION (SSL)</h3>
                <p>Self-supervised learning for 12 freshwater species · fine-tuned representations</p>
                <div>
                    <span class="pixel-tag">PYTORCH</span>
                    <span class="pixel-tag">RESNET</span>
                    <span class="pixel-tag">SIMCLR</span>
                </div>
                <div style="margin-top:12px;"><a href="#" class="glitch-link">[ REPO ]</a></div>
            </div>
            <div class="project-card">
                <h3>END-TO-END AI PIPELINE</h3>
                <p>Template with preprocessing, training, FastAPI, Docker · ready to deploy</p>
                <div>
                    <span class="pixel-tag">FASTAPI</span>
                    <span class="pixel-tag">SKLEARN</span>
                    <span class="pixel-tag">DOCKER</span>
                </div>
                <div style="margin-top:12px;"><a href="#" class="glitch-link">[ REPO ]</a></div>
            </div>
        </div>

        <!-- Education pixel grid -->
        <h2>🎓 EDUCATION</h2>
        <div style="display: flex; flex-direction: column; gap: 12px;">
            <div style="display: flex; gap: 10px; background:#14242c; border:2px solid #2faf9f; padding:10px;">
                <span style="min-width:100px;">2022–2025</span> <span><strong>B.Sc. CSE (Data Science)</strong> — East West University, Dhaka</span>
            </div>
            <div style="display: flex; gap: 10px; background:#14242c; border:2px solid #2faf9f; padding:10px;">
                <span style="min-width:100px;">2018–2020</span> <span><strong>HSC (Science)</strong> — Bangladesh Navy College</span>
            </div>
            <div class="badge-grid" style="justify-content:flex-start;">
                <span class="badge-pixel">AI</span>
                <span class="badge-pixel">ML</span>
                <span class="badge-pixel">IMAGE PROCESSING</span>
                <span class="badge-pixel">DATA MINING</span>
                <span class="badge-pixel">ALGORITHMS</span>
            </div>
        </div>

        <!-- GitHub stats but with pixel style / fake retro stats (you can replace with actual iframe later) -->
        <h2>📊 PIXEL_STATS</h2>
        <div class="stats-panel">
            <div class="stat-cell">COMMITS: 1.2k<br/> <span style="color:#80ffc0;">▲ +327</span></div>
            <div class="stat-cell">REPOS: 24<br/> <span style="color:#f0ffa0;">⭐ 42</span></div>
            <div class="stat-cell">STREAK: 147d<br/> <span style="color:#ffb56b;">⚡active</span></div>
            <div class="stat-cell">LANG: PYTHON<br/> 78%</div>
        </div>
        <!-- activity graph (pure pixel placeholder) -->
        <div style="background:#0a1a1a; width:100%; height:70px; border:3px solid #2fbbaa; display:flex; align-items:center; justify-content:center; color:#a0f0d0; font-family:'Press Start 2P'; font-size:0.6rem;">
            ███ ██ ████ █ ███   ████ ██  ██   ███  █████  ████  (activity grid)
        </div>

        <!-- Core Strengths / interests -->
        <h2>💡 CORE_STRENGTHS</h2>
        <div style="display: flex; flex-wrap: wrap; gap:10px; justify-content:center;">
            <span class="badge-pixel">COMPUTER VISION</span>
            <span class="badge-pixel">SELF-SUPERVISED</span>
            <span class="badge-pixel">LLM (BASIC)</span>
            <span class="badge-pixel">RESEARCH WRITING</span>
            <span class="badge-pixel">PROBLEM SOLVING</span>
        </div>
        <hr/>
        <!-- connect & retro footer -->
        <div style="display: flex; flex-wrap: wrap; justify-content: space-between; align-items:center;">
            <span style="font-family:'Press Start 2P'; font-size:0.8rem;">>_ CONNECT</span>
            <div style="display:flex; gap: 10px;">
                <a href="#" class="badge-pixel">🐦 TWITTER</a>
                <a href="#" class="badge-pixel">📧 EMAIL</a>
                <a href="#" class="badge-pixel">💼 PORTFOLIO</a>
            </div>
        </div>
        <footer>
            <span style="display:block; margin: 24px 0 8px;">⚡ "Building intelligent systems, one pixel at a time." ⚡</span>
            <span>© 2025 HASAN-SAKIB // RETRO PIXEL EDITION</span>
        </footer>
    </div>
</body>
</html>
