<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>YOUR NAME — Dev Profile</title>

<!-- Clean Google font -->
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">

<style>
  :root{
    --bg1: #0f172a;
    --bg2: #0b1221;
    --glass: rgba(255,255,255,0.06);
    --accent-a: #7c3aed;
    --accent-b: #06b6d4;
    --muted: rgba(255,255,255,0.65);
    --card-radius: 18px;
    --glass-border: rgba(255,255,255,0.06);
  }
  *{box-sizing:border-box}
  body{
    margin:0;
    min-height:100vh;
    font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial;
    background: radial-gradient(1200px 600px at 10% 10%, rgba(124,58,237,0.12), transparent),
                radial-gradient(800px 400px at 90% 90%, rgba(6,182,212,0.08), transparent),
                linear-gradient(180deg,var(--bg1),var(--bg2));
    color:#e6eef8;
    -webkit-font-smoothing:antialiased;
    -moz-osx-font-smoothing:grayscale;
    padding:48px;
    display:flex;
    align-items:center;
    justify-content:center;
  }

  /* container */
  .wrap{
    width:100%;
    max-width:1100px;
    display:grid;
    grid-template-columns: 360px 1fr;
    gap:28px;
    align-items:start;
  }

  /* left card */
  .card{
    background: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.015));
    border-radius: var(--card-radius);
    padding:22px;
    box-shadow: 0 6px 30px rgba(2,6,23,0.6);
    border: 1px solid var(--glass-border);
    backdrop-filter: blur(8px) saturate(1.2);
  }

  .avatar{
    width:100%;
    border-radius: 14px;
    overflow:hidden;
    border:1px solid rgba(255,255,255,0.04);
  }
  .avatar img{ display:block; width:100%; height:240px; object-fit:cover; }

  h1{
    margin:14px 0 6px 0;
    font-size:22px;
    letter-spacing:0.2px;
  }
  .subtitle{ color:var(--muted); font-size:13px; margin:0 0 14px 0; }

  .badges{ display:flex; flex-wrap:wrap; gap:8px; margin-bottom:14px; }
  .badge{
    background: linear-gradient(90deg,var(--accent-a),var(--accent-b));
    padding:6px 10px;
    font-size:12px;
    border-radius:999px;
    box-shadow:0 4px 18px rgba(12,16,30,0.35);
    font-weight:600;
  }

  /* contact row */
  .contact{ display:flex; gap:8px; flex-wrap:wrap; margin-top:10px; }
  .contact a{
    text-decoration:none;
    color:var(--muted);
    font-size:13px;
    padding:8px 10px;
    border-radius:10px;
    background:linear-gradient(180deg, rgba(255,255,255,0.01), transparent);
    border:1px solid rgba(255,255,255,0.02);
  }

  /* right column */
  .panel{
    background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    border-radius: var(--card-radius);
    padding:20px;
    border:1px solid rgba(255,255,255,0.03);
    box-shadow: 0 6px 40px rgba(2,6,23,0.5);
  }

  .about{ color:var(--muted); line-height:1.55; margin-bottom:16px; }
  .section-title{
    display:flex;
    align-items:center;
    gap:12px;
    margin-bottom:10px;
  }
  .section-title h3{ margin:0; font-size:16px; }

  /* skill bars */
  .skills{ display:grid; gap:12px; }
  .skill{
    background:rgba(255,255,255,0.02);
    padding:10px;
    border-radius:10px;
    border:1px solid rgba(255,255,255,0.02);
  }
  .skill .row{ display:flex; justify-content:space-between; font-size:13px; margin-bottom:8px; color:var(--muted); }
  .bar{
    height:10px;
    background:rgba(255,255,255,0.03);
    border-radius:999px;
    overflow:hidden;
  }
  .bar > i{
    display:block;
    height:100%;
    border-radius:999px;
    background:linear-gradient(90deg,var(--accent-a),var(--accent-b));
    width:0%;
    transition:width 1.2s cubic-bezier(.2,.85,.25,1);
  }

  /* project cards */
  .projects{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:12px;
    margin-top:12px;
  }
  .proj{
    padding:10px;
    border-radius:12px;
    border:1px solid rgba(255,255,255,0.03);
    background: linear-gradient(180deg, rgba(255,255,255,0.015), transparent);
  }
  .proj h4{ margin:6px 0 4px 0; font-size:14px; }
  .proj p{ margin:0; color:var(--muted); font-size:13px; }

  /* footer row */
  .footer{
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:12px;
    margin-top:18px;
  }

  .ctas{ display:flex; gap:10px; }
  .btn{
    padding:8px 12px;
    border-radius:10px;
    text-decoration:none;
    color:white;
    font-weight:600;
    font-size:13px;
    background: linear-gradient(90deg,var(--accent-b),var(--accent-a));
    box-shadow: 0 8px 30px rgba(12,16,30,0.45);
  }

  /* small responsive */
  @media (max-width:900px){
    .wrap{ grid-template-columns: 1fr; padding:0; }
    .avatar img{ height:200px; }
    .projects{ grid-template-columns: 1fr; }
  }

  /* subtle load animations */
  .animate-delay-1 .bar > i{ width:85%; }
  .animate-delay-2 .bar > i{ width:75%; }
  .animate-delay-3 .bar > i{ width:70%; }
  .animate-delay-4 .bar > i{ width:60%; }

  /* little glint shimmer on name */
  .shine{
    position:relative;
    display:inline-block;
    overflow:hidden;
  }
  .shine::after{
    content:"";
    position:absolute;
    left:-60%;
    top:0;
    width:60%;
    height:100%;
    background: linear-gradient(90deg, rgba(255,255,255,0.0), rgba(255,255,255,0.18), rgba(255,255,255,0.0));
    transform:skewX(-20deg);
    animation:shimmer 3s linear infinite;
  }
  @keyframes shimmer{ 0%{left:-60%} 100%{left:160%} }
</style>
</head>
<body>

<div class="wrap">
  <!-- LEFT -->
  <div class="card">
    <div class="avatar">
      <!-- Replace with your header GIF or image (upload to repo and link here) -->
      <img src="https://images.unsplash.com/photo-1545239351-1141bd82e8a6?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=fb7b3b1fbd1d1e0a4b6b9ce8e3f5a0c8" alt="Header image">
    </div>

    <h1><span class="shine">YOUR NAME</span></h1>
    <p class="subtitle">Full-Stack Developer • Open-Source Enthusiast • Web & API builder</p>

    <div class="badges">
      <div class="badge">React</div>
      <div class="badge">Node.js</div>
      <div class="badge">Python</div>
      <div class="badge">Django</div>
    </div>

    <div class="contact">
      <a href="https://github.com/YOUR-USERNAME" target="_blank">GitHub</a>
      <a href="https://linkedin.com/in/YOUR-LINKEDIN" target="_blank">LinkedIn</a>
      <a href="mailto:hello@you.com">Email</a>
    </div>

    <div style="margin-top:14px; font-size:13px; color:var(--muted)">
      <strong>Location:</strong> Dhaka, Bangladesh<br>
      <strong>Open to:</strong> Freelance, Collaboration, Full-time
    </div>
  </div>

  <!-- RIGHT -->
  <div class="panel">
    <div class="about">
      I build high-quality web applications and APIs with attention to performance and user experience.
      I love contributing to open-source and learning new tools & patterns.
    </div>

    <div class="section-title">
      <h3>Skills</h3>
    </div>
    <div class="skills">
      <div class="skill animate-delay-1">
        <div class="row"><span>JavaScript / TypeScript</span><strong>85%</strong></div>
        <div class="bar"><i></i></div>
      </div>
      <div class="skill animate-delay-2">
        <div class="row"><span>React / Next.js</span><strong>75%</strong></div>
        <div class="bar"><i></i></div>
      </div>
      <div class="skill animate-delay-3">
        <div class="row"><span>Python / Django / FastAPI</span><strong>70%</strong></div>
        <div class="bar"><i></i></div>
      </div>
      <div class="skill animate-delay-4">
        <div class="row"><span>DevOps / Docker / CI</span><strong>60%</strong></div>
        <div class="bar"><i></i></div>
      </div>
    </div>

    <div style="margin-top:16px" class="section-title"><h3>Featured Projects</h3></div>
    <div class="projects">
      <div class="proj">
        <h4><a href="https://github.com/YOUR-USERNAME/project-1" target="_blank" style="color:inherit; text-decoration:none">Project One</a></h4>
        <p>Short description — React • Node • Deployed</p>
      </div>
      <div class="proj">
        <h4><a href="https://github.com/YOUR-USERNAME/project-2" target="_blank" style="color:inherit; text-decoration:none">Project Two</a></h4>
        <p>Short description — Python • FastAPI • Docker</p>
      </div>
      <div class="proj">
        <h4><a href="https://github.com/YOUR-USERNAME/project-3" target="_blank" style="color:inherit; text-decoration:none">Project Three</a></h4>
        <p>Short description — Next.js • Static Blog</p>
      </div>
      <div class="proj">
        <h4><a href="https://github.com/YOUR-USERNAME/project-4" target="_blank" style="color:inherit; text-decoration:none">Project Four</a></h4>
        <p>Short description — Tooling / CLI</p>
      </div>
    </div>

    <div class="footer">
      <div style="color:var(--muted); font-size:13px">⭐ Proactive • Clean code • Open to collaborate</div>
      <div class="ctas">
        <a class="btn" href="https://github.com/YOUR-USERNAME" target="_blank">View GitHub</a>
        <a class="btn" href="mailto:hello@you.com">Hire / Contact</a>
      </div>
    </div>
  </div>
</div>

</body>
</html>
