<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Deb Sunny · Premium Portfolio Card</title>
  <!-- Google Fonts: Premium Sans & Mono for elegance -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
  <!-- Font Awesome 6 (free icons) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: radial-gradient(circle at 10% 30%, #0a0f1e, #03050b);
      font-family: 'Inter', sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      padding: 2rem;
      position: relative;
      overflow-x: hidden;
    }

    /* animated background grain + floating orbs */
    body::before {
      content: "";
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: radial-gradient(circle at 20% 40%, rgba(66, 153, 225, 0.08) 0%, rgba(0,0,0,0) 70%);
      pointer-events: none;
      z-index: 0;
    }

    /* main container – glassmorphic card with premium animation */
    .portfolio-card {
      max-width: 1300px;
      width: 100%;
      background: rgba(12, 18, 28, 0.75);
      backdrop-filter: blur(14px);
      border-radius: 2.5rem;
      border: 1px solid rgba(66, 153, 225, 0.25);
      box-shadow: 0 25px 45px -12px rgba(0, 0, 0, 0.6), 0 0 0 1px rgba(76, 175, 230, 0.1) inset;
      overflow: hidden;
      transition: transform 0.4s ease, box-shadow 0.5s ease;
      animation: cardGlow 3s infinite alternate ease-in-out;
      z-index: 2;
    }

    @keyframes cardGlow {
      0% {
        box-shadow: 0 25px 45px -12px rgba(0, 0, 0, 0.6), 0 0 0 1px rgba(66, 153, 225, 0.2) inset;
        border-color: rgba(66, 153, 225, 0.2);
      }
      100% {
        box-shadow: 0 30px 55px -10px rgba(0, 180, 255, 0.25), 0 0 0 2px rgba(0, 212, 255, 0.4) inset;
        border-color: rgba(0, 212, 255, 0.5);
      }
    }

    /* inner content */
    .card-inner {
      padding: 2.2rem 2.4rem;
    }

    /* header / intro section with waving animation */
    .intro-section {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 2.5rem;
      border-bottom: 1px solid rgba(100, 150, 220, 0.3);
      padding-bottom: 1.8rem;
    }

    .title-badge h1 {
      font-size: 2.6rem;
      font-weight: 700;
      background: linear-gradient(135deg, #FFFFFF, #90e0ff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      letter-spacing: -0.02em;
    }

    .wave {
      display: inline-block;
      animation: waveAnim 1.2s infinite ease-in-out;
      transform-origin: 70% 70%;
      font-size: 2.5rem;
    }

    @keyframes waveAnim {
      0% { transform: rotate(0deg); }
      20% { transform: rotate(14deg); }
      40% { transform: rotate(-8deg); }
      60% { transform: rotate(10deg); }
      80% { transform: rotate(-2deg); }
      100% { transform: rotate(0deg); }
    }

    .role-tag {
      font-size: 1.2rem;
      font-weight: 500;
      background: rgba(0, 212, 255, 0.12);
      display: inline-block;
      padding: 0.3rem 1rem;
      border-radius: 40px;
      backdrop-filter: blur(4px);
      margin-top: 0.5rem;
      color: #b9f2ff;
      border: 0.5px solid #2c7da0;
    }

    .contact-actions {
      text-align: right;
    }

    .email-chip {
      background: #1e2a3e80;
      padding: 0.6rem 1.2rem;
      border-radius: 60px;
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.85rem;
      color: #9ad7f5;
      transition: all 0.25s;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      border: 1px solid #2c7da0;
      backdrop-filter: blur(5px);
    }

    .email-chip i {
      color: #3bc9ff;
    }

    .email-chip:hover {
      background: #2c3e55;
      transform: scale(1.02);
      border-color: #5ee0ff;
    }

    /* badge & socials row */
    .info-strip {
      display: flex;
      flex-wrap: wrap;
      gap: 1.8rem;
      justify-content: space-between;
      margin-bottom: 2rem;
    }

    .ask-me, .fun-fact {
      background: rgba(15, 25, 40, 0.6);
      border-radius: 1.2rem;
      padding: 0.7rem 1.3rem;
      font-size: 0.9rem;
      font-weight: 500;
      backdrop-filter: blur(4px);
    }

    .ask-me i, .fun-fact i {
      margin-right: 8px;
      color: #4cc9f0;
    }

    .social-links a {
      color: #cbd5e6;
      background: #0f172a;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 42px;
      height: 42px;
      border-radius: 40px;
      transition: all 0.3s cubic-bezier(0.2, 0.9, 0.4, 1.1);
      margin-left: 10px;
      font-size: 1.4rem;
      border: 1px solid #2c6690;
    }

    .social-links a:hover {
      background: #1e3a5f;
      color: white;
      transform: translateY(-3px);
      border-color: #5ee0ff;
      box-shadow: 0 8px 18px rgba(0,160,255,0.2);
    }

    /* tech stack containers */
    .section-title {
      font-size: 1.5rem;
      font-weight: 600;
      margin: 2rem 0 1rem 0;
      letter-spacing: -0.3px;
      background: linear-gradient(120deg, #dfeef8, #a0d0ff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      border-left: 4px solid #2c9cd4;
      padding-left: 16px;
    }

    .tech-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 0.9rem;
      margin-top: 1rem;
      margin-bottom: 1.4rem;
    }

    .tech-badge {
      background: rgba(20, 30, 45, 0.7);
      backdrop-filter: blur(5px);
      padding: 0.5rem 1rem;
      border-radius: 40px;
      font-size: 0.85rem;
      font-weight: 500;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      transition: all 0.2s;
      border: 0.5px solid #317f9e;
      color: #e2f0ff;
    }

    .tech-badge i, .tech-badge svg {
      font-size: 1.1rem;
    }

    .tech-badge:hover {
      background: #1f3b4f;
      transform: translateY(-2px);
      border-color: #4ad4ff;
    }

    /* stats & trophy section */
    .stats-wrapper {
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      justify-content: space-between;
      margin: 2rem 0 2rem;
    }

    .github-stats-card {
      flex: 2;
      min-width: 240px;
      background: rgba(8, 14, 22, 0.65);
      border-radius: 1.5rem;
      padding: 1.2rem;
      backdrop-filter: blur(5px);
    }

    .stats-img {
      width: 100%;
      border-radius: 12px;
      transition: filter 0.3s;
    }

    .trophy-grid {
      flex: 1.2;
      background: rgba(0, 0, 0, 0.35);
      border-radius: 1.5rem;
      padding: 1rem;
      text-align: center;
    }

    .trophy-img {
      max-width: 100%;
      border-radius: 12px;
    }

    .contrib-repo {
      background: linear-gradient(145deg, #0b1422, #03070f);
      border-radius: 1.5rem;
      padding: 1.2rem;
      margin-top: 1rem;
      border: 1px solid #2a577b;
    }

    .visitor-badge {
      display: flex;
      justify-content: flex-end;
      margin-top: 1.2rem;
      font-size: 0.8rem;
    }

    /* donation button */
    .donation-area {
      margin-top: 2rem;
      display: flex;
      justify-content: center;
    }

    .bmc-button {
      background: #ffdd00;
      color: #1f1a00;
      padding: 0.85rem 2rem;
      border-radius: 60px;
      font-weight: 700;
      display: inline-flex;
      align-items: center;
      gap: 12px;
      transition: all 0.3s;
      text-decoration: none;
      font-size: 1.1rem;
      border: none;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    }

    .bmc-button i {
      font-size: 1.5rem;
      color: #333;
    }

    .bmc-button:hover {
      transform: scale(1.03);
      background: #ffe55e;
      box-shadow: 0 10px 20px rgba(0,0,0,0.3);
    }

    /* footer / snake animation added as SVG */
    .snake-container {
      margin-top: 2rem;
      text-align: center;
      border-top: 1px solid rgba(66,153,225,0.25);
      padding-top: 1.8rem;
    }

    .snake-svg svg {
      max-width: 100%;
      height: auto;
      opacity: 0.85;
      transition: all 0.4s;
    }

    /* responsive */
    @media (max-width: 780px) {
      .card-inner {
        padding: 1.5rem;
      }
      .title-badge h1 {
        font-size: 1.9rem;
      }
      .intro-section {
        flex-direction: column;
        align-items: flex-start;
        gap: 1rem;
      }
      .contact-actions {
        text-align: left;
      }
      .stats-wrapper {
        flex-direction: column;
      }
    }

    /* subtle scroll */
    ::-webkit-scrollbar {
      width: 6px;
    }
    ::-webkit-scrollbar-track {
      background: #0a0f1e;
    }
    ::-webkit-scrollbar-thumb {
      background: #2c7da0;
      border-radius: 8px;
    }

    /* animate all tech-badge entrance */
    .tech-badge {
      animation: fadeSlideUp 0.5s ease backwards;
      animation-delay: calc(var(--order, 0) * 0.03s);
    }
    @keyframes fadeSlideUp {
      from {
        opacity: 0;
        transform: translateY(12px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
  </style>
</head>
<body>
<div class="portfolio-card">
  <div class="card-inner">

    <!-- Header section with waving animation -->
    <div class="intro-section">
      <div class="title-badge">
        <h1>
          <span class="wave">💫</span> Hi 👋, I'm Deb Brotho Sunny
          <div style="font-size: 0.9rem; font-weight: normal; color: #bdd4ff;">( Deb Sunny )</div>
        </h1>
        <div class="role-tag">
          <i class="fas fa-code"></i> passionate Software Engineer || DevOps Learner
        </div>
      </div>
      <div class="contact-actions">
        <div class="email-chip">
          <i class="fas fa-envelope"></i> debnathsunny7852@gmail.com
          <span style="font-size: 0.7rem;">✉️ For Collab/Project</span>
        </div>
      </div>
    </div>

    <!-- Info badges + Fun fact & socials -->
    <div class="info-strip">
      <div class="ask-me">
        <i class="fas fa-comments"></i> 💬 Ask me about: Collaboration, Tech Support
      </div>
      <div class="fun-fact">
        <i class="fas fa-microchip"></i> ⚡ Fun fact: I Love Tech and Tech Love Me
      </div>
      <div class="social-links">
        <a href="https://linkedin.com/in/deb-brotho-6b7b59308" target="_blank" aria-label="LinkedIn"><i class="fab fa-linkedin-in"></i></a>
        <a href="mailto:debnathsunny7852@gmail.com" target="_blank" aria-label="Email"><i class="fas fa-envelope"></i></a>
      </div>
    </div>

    <!-- Current work & learning -->
    <div style="display: flex; flex-wrap: wrap; gap: 1rem; background: rgba(31, 51, 75, 0.3); border-radius: 1.2rem; padding: 0.8rem 1.2rem; margin-bottom: 0.8rem;">
      <span><i class="fas fa-briefcase" style="color: #4cc9f0;"></i> 🔭 currently working at: <strong>Smith IT</strong> (May 2025 - Now)</span>
      <span><i class="fas fa-graduation-cap" style="color: #4cc9f0;"></i> 🌱 currently learning: <strong>DevOps · AWS · CI/CD</strong></span>
      <span><i class="fas fa-user-astronaut"></i> 😄 Pronouns: <strong>Deb Sunny</strong></span>
    </div>

    <!-- === Tech Stack with premium style (Frontend / Backend / Infra) === -->
    <div class="section-title">⚙️ Frontend Craft</div>
    <div class="tech-grid">
      <div class="tech-badge" style="--order:1"><i class="fab fa-html5"></i> HTML5</div>
      <div class="tech-badge" style="--order:2"><i class="fab fa-css3-alt"></i> CSS3</div>
      <div class="tech-badge" style="--order:3"><i class="fab fa-js"></i> JavaScript</div>
      <div class="tech-badge" style="--order:4"><i class="fab fa-react"></i> React</div>
      <div class="tech-badge" style="--order:5"><i class="fab fa-vuejs"></i> Vue.js</div>
      <div class="tech-badge" style="--order:6"><i class="fab fa-js"></i> jQuery</div>
      <div class="tech-badge" style="--order:7"><i class="fab fa-bootstrap"></i> Bootstrap</div>
      <div class="tech-badge" style="--order:8"><i class="fas fa-chart-line"></i> Chart.js</div>
      <div class="tech-badge" style="--order:9"><i class="fab fa-tailwind"></i> TailwindCSS</div>
    </div>

    <div class="section-title">🧠 Backend & Database</div>
    <div class="tech-grid">
      <div class="tech-badge"><i class="fab fa-php"></i> PHP</div>
      <div class="tech-badge"><i class="fab fa-laravel"></i> Laravel</div>
      <div class="tech-badge"><i class="fas fa-key"></i> JWT</div>
      <div class="tech-badge"><i class="fas fa-database"></i> MySQL</div>
      <div class="tech-badge"><i class="fas fa-database"></i> SQLite</div>
    </div>

    <div class="section-title">☁️ Infrastructure & Tools</div>
    <div class="tech-grid">
      <div class="tech-badge"><i class="fab fa-aws"></i> AWS</div>
      <div class="tech-badge"><i class="fas fa-cloud-upload-alt"></i> Netlify</div>
      <div class="tech-badge"><i class="fab fa-npm"></i> NPM</div>
      <div class="tech-badge"><i class="fas fa-flask"></i> Postman</div>
      <div class="tech-badge"><i class="fab fa-figma"></i> Figma</div>
    </div>

    <!-- GitHub Stats + Trophies (embeds live stats via shields API? but we use actual images from github-readme-stats) 
         but to show real stats we will use the official vercel images corresponding to the username: debbrothosunny -->
    <div class="stats-wrapper">
      <div class="github-stats-card">
        <div style="font-weight: 600; margin-bottom: 8px;"><i class="fab fa-github"></i> 📊 GitHub Analytics</div>
        <img class="stats-img" src="https://github-readme-stats.vercel.app/api?username=debbrothosunny&theme=dark&hide_border=false&include_all_commits=true&count_private=true" alt="GitHub Stats" loading="lazy">
        <img class="stats-img" src="https://nirzak-streak-stats.vercel.app/?user=debbrothosunny&theme=dark&hide_border=false" alt="Streak Stats" style="margin-top: 12px;" loading="lazy">
        <img class="stats-img" src="https://github-readme-stats.vercel.app/api/top-langs/?username=debbrothosunny&theme=dark&hide_border=false&include_all_commits=true&count_private=true&layout=compact" alt="Top Langs" style="margin-top: 12px;" loading="lazy">
      </div>
      <div class="trophy-grid">
        <div style="font-weight: 600;"><i class="fas fa-trophy"></i> 🏆 GitHub Trophies</div>
        <img class="trophy-img" src="https://github-profile-trophy.vercel.app/?username=debbrothosunny&theme=radical&no-frame=false&no-bg=true&margin-w=4" alt="Trophies" loading="lazy">
      </div>
    </div>

    <!-- Top Contributed Repo -->
    <div class="contrib-repo">
      <i class="fas fa-rocket"></i> 🔝 Top Contributed Repo
      <div style="margin-top: 10px;">
        <img src="https://github-contributor-stats.vercel.app/api?username=debbrothosunny&limit=5&theme=dark&combine_all_yearly_contributions=true" alt="contributor stats" style="width:100%; border-radius: 12px;">
      </div>
    </div>

    <!-- Visitor count & Donate -->
    <div class="visitor-badge">
      <img src="https://visitcount.itsvg.in/api?id=debbrothosunny&icon=0&color=0" alt="visitor counter" style="border-radius: 20px;">
    </div>

    <div class="donation-area">
      <a href="https://buymeacoffee.com/debnathsunny7852@gmail.com" target="_blank" class="bmc-button">
        <i class="fas fa-mug-hot"></i> Buy Me a Coffee
      </a>
    </div>

    <!-- Snake Game Animation (SVG from profile-readme-generator style) - we embed dynamic svg animation to match premium feel -->
    <div class="snake-container">
      <div class="snake-svg">
        <!-- Animated SVG snake grid (premium style) generated via inline, giving "Snake Game" effect but without external API risk. Pure vector animation -->
        <svg width="100%" height="80" viewBox="0 0 900 80" xmlns="http://www.w3.org/2000/svg" style="border-radius: 30px;">
          <rect width="100%" height="80" fill="#0c1622" rx="14" ry="14" />
          <g fill="none" stroke="#2c9cd4" stroke-width="1.5" opacity="0.5">
            <line x1="20" y1="20" x2="880" y2="20" stroke="#2c7da0" stroke-dasharray="4 4"/>
            <line x1="20" y1="60" x2="880" y2="60" stroke="#2c7da0" stroke-dasharray="4 4"/>
          </g>
          <g>
            <!-- animated snake path -->
            <circle cx="50" cy="40" r="6" fill="#5ee0ff" filter="url(#glow)">
              <animate attributeName="cx" values="50;200;350;500;650;800;800;650;500;350;200;50" dur="6s" repeatCount="indefinite" />
              <animate attributeName="cy" values="40;30;40;50;40;40;40;30;45;35;40;40" dur="6s" repeatCount="indefinite" />
            </circle>
            <circle cx="0" cy="40" r="5" fill="#9bdeff" opacity="0.8">
              <animate attributeName="cx" values="0;150;300;450;600;750;750;600;450;300;150;0" dur="6s" repeatCount="indefinite" />
            </circle>
            <circle cx="0" cy="40" r="4" fill="#ffd966">
              <animate attributeName="cx" values="0;90;240;390;540;690;690;540;390;240;90;0" dur="6s" repeatCount="indefinite" />
            </circle>
          </g>
          <defs>
            <filter id="glow" x="-30%" y="-30%" width="160%" height="160%">
              <feGaussianBlur in="SourceAlpha" stdDeviation="3" />
              <feMerge>
                <feMergeNode in="offsetblur" />
                <feMergeNode in="SourceGraphic" />
              </feMerge>
            </filter>
          </defs>
          <text x="20" y="70" fill="#70c8ff" font-size="9" font-family="monospace">🐍 dev-snake | tech love cycle</text>
        </svg>
      </div>
      <div style="font-size: 0.7rem; text-align: center; margin-top: 8px; color:#6b9bc0;">⚡ interactive snake animation — code never sleeps</div>
    </div>

    <!-- micro footer note -->
    <div style="text-align: center; margin-top: 1.4rem; font-size: 0.7rem; opacity: 0.6; letter-spacing: 0.5px;">
      <i class="fas fa-heart" style="color:#ff6699;"></i> Proudly crafted with premium style & animated glow • Deb Sunny
    </div>
  </div>
</div>
</body>
</html>
