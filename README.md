<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Abdi Serbessa — Full Stack Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --bg: #F9F8F4;
    --surface: #F0EEE6;
    --ink: #14181A;
    --ink-soft: #4B5450;
    --line: #D8D3C4;
    --teal: #1B4B43;
    --teal-soft: #E4ECE9;
    --ochre: #B8863B;
    --ochre-soft: #F3E7D4;
    --radius: 3px;
  }

  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth;}

  body{
    background:var(--bg);
    color:var(--ink);
    font-family:'Inter', sans-serif;
    font-size:16px;
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }

  a{color:inherit;}
  ::selection{background:var(--teal); color:#fff;}

  :focus-visible{
    outline:2px solid var(--teal);
    outline-offset:3px;
  }

  .wrap{
    max-width:1080px;
    margin:0 auto;
    padding:0 32px;
  }

  .eyebrow{
    font-family:'JetBrains Mono', monospace;
    font-size:12.5px;
    letter-spacing:.08em;
    text-transform:uppercase;
    color:var(--teal);
    display:flex;
    align-items:center;
    gap:8px;
  }
  .eyebrow::before{
    content:"";
    width:7px; height:7px;
    background:var(--ochre);
    display:inline-block;
    border-radius:50%;
  }

  h1,h2,h3{
    font-family:'Space Grotesk', sans-serif;
    letter-spacing:-.01em;
  }

  /* ---------- NAV ---------- */
  header{
    position:sticky; top:0; z-index:50;
    background:rgba(249,248,244,.9);
    backdrop-filter:blur(8px);
    border-bottom:1px solid var(--line);
  }
  nav{
    display:flex; align-items:center; justify-content:space-between;
    padding:18px 32px;
    max-width:1080px;
    margin:0 auto;
  }
  .logo{
    font-family:'JetBrains Mono', monospace;
    font-weight:500;
    font-size:15px;
  }
  .logo span{color:var(--ochre);}
  .navlinks{
    display:flex; gap:28px;
    list-style:none;
    font-family:'JetBrains Mono', monospace;
    font-size:13px;
  }
  .navlinks a{
    text-decoration:none;
    color:var(--ink-soft);
    transition:color .2s;
  }
  .navlinks a:hover{color:var(--teal);}
  .navtoggle{display:none;}

  /* ---------- HERO ---------- */
  .hero{
    padding:96px 0 72px;
    border-bottom:1px solid var(--line);
  }
  .hero-grid{
    display:grid;
    grid-template-columns:1.3fr 1fr;
    gap:56px;
    align-items:start;
  }
  .hero h1{
    font-size:clamp(40px, 6vw, 68px);
    line-height:1.02;
    margin:18px 0 20px;
  }
  .hero h1 em{
    font-style:normal;
    color:var(--teal);
  }
  .hero p.lede{
    max-width:52ch;
    font-size:18px;
    color:var(--ink-soft);
    margin-bottom:28px;
  }
  .langs{
    display:flex; gap:10px; flex-wrap:wrap;
    margin-bottom:32px;
  }
  .lang-pill{
    font-family:'JetBrains Mono', monospace;
    font-size:12px;
    border:1px solid var(--line);
    padding:6px 12px;
    border-radius:20px;
    background:var(--surface);
    color:var(--ink-soft);
  }
  .cta-row{display:flex; gap:14px; flex-wrap:wrap;}
  .btn{
    font-family:'JetBrains Mono', monospace;
    font-size:13px;
    text-decoration:none;
    padding:12px 20px;
    border-radius:var(--radius);
    display:inline-flex;
    align-items:center;
    gap:8px;
    transition:transform .15s ease, background .15s ease;
  }
  .btn-primary{background:var(--teal); color:#fff;}
  .btn-primary:hover{transform:translateY(-2px); background:#153e37;}
  .btn-ghost{border:1px solid var(--line); color:var(--ink);}
  .btn-ghost:hover{transform:translateY(-2px); border-color:var(--teal);}

  /* schema panel */
  .record{
    background:var(--ink);
    color:#EDEAE0;
    border-radius:6px;
    padding:22px 24px;
    font-family:'JetBrains Mono', monospace;
    font-size:13px;
    line-height:2;
  }
  .record .rec-title{
    color:#7C8B85;
    font-size:11px;
    text-transform:uppercase;
    letter-spacing:.1em;
    margin-bottom:10px;
    display:block;
  }
  .record .k{color:#7FAF9E;}
  .record .s{color:#D9A45B;}
  .record .row{display:flex; justify-content:space-between; gap:16px; border-bottom:1px dashed #2A302D; padding:5px 0;}
  .record .row:last-child{border-bottom:none;}

  /* ---------- SECTION SHELL ---------- */
  section{padding:72px 0; border-bottom:1px solid var(--line);}
  .sec-head{
    display:flex; align-items:baseline; justify-content:space-between;
    margin-bottom:36px;
    flex-wrap:wrap; gap:8px;
  }
  .sec-head h2{font-size:30px;}
  .sec-head .tag{
    font-family:'JetBrains Mono', monospace;
    font-size:12px;
    color:var(--ink-soft);
  }

  /* ---------- ABOUT ---------- */
  .about-grid{
    display:grid;
    grid-template-columns:1.4fr 1fr;
    gap:48px;
  }
  .about-grid p{color:var(--ink-soft); font-size:16.5px; margin-bottom:16px; max-width:60ch;}
  .facts{
    border:1px solid var(--line);
    border-radius:6px;
    overflow:hidden;
  }
  .facts .row{
    display:flex; justify-content:space-between;
    padding:14px 18px;
    border-bottom:1px solid var(--line);
    font-size:14px;
  }
  .facts .row:last-child{border-bottom:none;}
  .facts .row span:first-child{
    font-family:'JetBrains Mono', monospace;
    color:var(--ink-soft);
    font-size:12px;
    text-transform:uppercase;
    letter-spacing:.06em;
  }

  /* ---------- STACK ---------- */
  .stack-groups{
    display:grid;
    grid-template-columns:repeat(auto-fit, minmax(220px, 1fr));
    gap:28px;
  }
  .stack-card{
    border:1px solid var(--line);
    border-radius:6px;
    padding:22px;
    background:var(--surface);
  }
  .stack-card h3{
    font-family:'JetBrains Mono', monospace;
    font-size:12.5px;
    text-transform:uppercase;
    letter-spacing:.08em;
    color:var(--teal);
    margin-bottom:14px;
    font-weight:500;
  }
  .chip-row{display:flex; flex-wrap:wrap; gap:8px;}
  .chip{
    font-size:13.5px;
    padding:6px 12px;
    background:#fff;
    border:1px solid var(--line);
    border-radius:20px;
  }

  /* ---------- PROJECTS ---------- */
  .projects{
    display:grid;
    grid-template-columns:repeat(auto-fit, minmax(320px, 1fr));
    gap:24px;
  }
  .project-card{
    border:1px solid var(--line);
    border-radius:8px;
    padding:28px;
    background:#fff;
    display:flex;
    flex-direction:column;
    gap:14px;
    transition:box-shadow .2s ease, transform .2s ease;
  }
  .project-card:hover{
    box-shadow:0 12px 28px -18px rgba(20,24,26,.25);
    transform:translateY(-3px);
  }
  .project-card .ptag{
    font-family:'JetBrains Mono', monospace;
    font-size:11px;
    color:var(--ochre);
    text-transform:uppercase;
    letter-spacing:.08em;
  }
  .project-card h3{font-size:21px;}
  .project-card p{color:var(--ink-soft); font-size:15px;}
  .project-card .chip-row{margin-top:auto; padding-top:8px;}
  .project-card .chip{font-size:12px; padding:4px 10px; background:var(--teal-soft); border-color:var(--teal-soft); color:var(--teal);}
  .project-link{
    font-family:'JetBrains Mono', monospace;
    font-size:13px;
    color:var(--teal);
    text-decoration:none;
    display:inline-flex; align-items:center; gap:6px;
  }
  .project-link:hover{text-decoration:underline;}

  /* ---------- EXPERIENCE / TIMELINE ---------- */
  .timeline{
    position:relative;
    padding-left:28px;
    border-left:1px solid var(--line);
  }
  .tl-item{
    position:relative;
    padding-bottom:36px;
  }
  .tl-item:last-child{padding-bottom:0;}
  .tl-item::before{
    content:"";
    position:absolute;
    left:-33px; top:4px;
    width:9px; height:9px;
    border-radius:50%;
    background:var(--bg);
    border:2px solid var(--teal);
  }
  .tl-date{
    font-family:'JetBrains Mono', monospace;
    font-size:12px;
    color:var(--ink-soft);
    margin-bottom:6px;
    display:block;
  }
  .tl-item h3{font-size:19px; margin-bottom:4px;}
  .tl-item .org{color:var(--teal); font-size:14.5px; font-weight:500; margin-bottom:8px; display:block;}
  .tl-item p{color:var(--ink-soft); font-size:15px; max-width:62ch;}

  /* ---------- CONTACT ---------- */
  .contact{border-bottom:none;}
  .contact-box{
    background:var(--ink);
    color:#EDEAE0;
    border-radius:10px;
    padding:56px 48px;
    display:grid;
    grid-template-columns:1.2fr 1fr;
    gap:40px;
    align-items:center;
  }
  .contact-box h2{color:#fff; font-size:34px; margin-bottom:14px;}
  .contact-box p{color:#A9B3AD; font-size:16px; max-width:44ch;}
  .contact-links{
    display:flex; flex-direction:column; gap:14px;
    font-family:'JetBrains Mono', monospace;
    font-size:14px;
  }
  .contact-links a{
    text-decoration:none;
    color:#EDEAE0;
    display:flex; justify-content:space-between;
    border-bottom:1px solid #2A302D;
    padding-bottom:10px;
    transition:color .2s;
  }
  .contact-links a span:first-child{color:#7C8B85;}
  .contact-links a:hover{color:var(--ochre);}

  footer{
    text-align:center;
    padding:28px 0 40px;
    font-family:'JetBrains Mono', monospace;
    font-size:12px;
    color:var(--ink-soft);
  }

  @media (max-width:800px){
    .navlinks{display:none;}
    .hero-grid, .about-grid, .contact-box{grid-template-columns:1fr;}
    .wrap{padding:0 20px;}
  }

  @media (prefers-reduced-motion: reduce){
    *{transition:none !important; scroll-behavior:auto !important;}
  }
</style>
</head>
<body>

<header>
  <nav>
    <div class="logo"><strong>abdi<span>.</span>se</strong></div>
    <ul class="navlinks">
      <li><strong><a href="#about">About</a></strong></li>
      <li><strong><a href="#stack">Stack</a></strong></li>
      <li><strong><a href="#projects">Projects</a></strong></li>
      <li><strong><a href="#experience">Experience</a></strong></li>
      <li><strong><a href="#contact">Contact</a></strong></li>
    </ul>
  </nav>
</header>

<section class="hero">
  <div class="wrap hero-grid">
    <div>
      <span class="eyebrow">Full Stack Developer</span>
      <h1>Abdi Serbessa builds <em>clean, scalable</em> web systems.</h1>
      <p class="lede">Software Engineering graduate turning full-stack applications and database systems into real-world, production-ready solutions — from tourism platforms to finance systems.</p>
      <div class="langs">
        <span class="lang-pill">EN — English</span>
        <span class="lang-pill">AM — Amharic</span>
        <span class="lang-pill">OM — Afaan Oromo</span>
      </div>
      <div class="cta-row">
        <a class="btn btn-primary" href="mailto:abdiserbess19@gmail.com">Email me</a>
        <a class="btn btn-ghost" href="https://github.com/AbdiSerbessa" target="_blank" rel="noopener">GitHub ↗</a>
        <a class="btn btn-ghost" href="https://www.linkedin.com/in/abdi-serbessa-8431442a0" target="_blank" rel="noopener">LinkedIn ↗</a>
      </div>
    </div>

    <div class="record">
      <span class="rec-title">// profile record</span>
      <div class="row"><span class="k">role</span><span>Full Stack Developer</span></div>
      <div class="row"><span class="k">location</span><span>Addis Ababa, ET</span></div>
      <div class="row"><span class="k">education</span><span>B.Sc. Software Eng.</span></div>
      <div class="row"><span class="k">stack[]</span><span class="s">React, Node, PostgreSQL</span></div>
      <div class="row"><span class="k">status</span><span>Open to opportunities</span></div>
    </div>
  </div>
</section>

<section id="about">
  <div class="wrap about-grid">
    <div>
      <span class="eyebrow">About</span>
      <h2 style="margin-top:14px;">Focused on solving real problems with efficient code.</h2>
      <p style="margin-top:20px;">I'm a Software Engineering graduate from Adama Science and Technology University with hands-on experience building full-stack web applications and scalable database systems. I specialize in clean, high-performance applications using HTML, CSS, JavaScript, React.js, Next.js, Node.js, and PostgreSQL.</p>
      <p>I care about designing user-centric digital solutions — and I'm always eager to build efficient, scalable systems that solve real-world problems, whether that's a tourism platform reaching an entire region or a finance system running inside a factory.</p>
    </div>
    <div class="facts">
      <div class="row"><span>Based in</span><span>Addis Ababa, Ethiopia</span></div>
      <div class="row"><span>Education</span><span>Adama Science &amp; Tech University</span></div>
      <div class="row"><span>Currently</span><span>Advanced Full Stack Training, IBT College</span></div>
      <div class="row"><span>Languages</span><span>English, Amharic, Afaan Oromo</span></div>
      <div class="row"><span>Email</span><span>abdiserbess19@gmail.com</span></div>
      <div class="row"><span>Phone</span><span>+251 943 350 427</span></div>
    </div>
  </div>
</section>

<section id="stack">
  <div class="wrap">
    <div class="sec-head">
      <h2>Technical stack</h2>
      <span class="tag">// languages, frameworks &amp; tools</span>
    </div>
    <div class="stack-groups">
      <div class="stack-card">
        <h3>Frontend</h3>
        <div class="chip-row">
          <span class="chip">HTML</span><span class="chip">CSS</span><span class="chip">JavaScript</span><span class="chip">React.js</span><span class="chip">Next.js</span>
        </div>
      </div>
      <div class="stack-card">
        <h3>Backend</h3>
        <div class="chip-row">
          <span class="chip">Node.js</span><span class="chip">REST APIs</span>
        </div>
      </div>
      <div class="stack-card">
        <h3>Database</h3>
        <div class="chip-row">
          <span class="chip">PostgreSQL</span><span class="chip">Schema Design</span>
        </div>
      </div>
      <div class="stack-card">
        <h3>Practice</h3>
        <div class="chip-row">
          <span class="chip">Full-stack architecture</span><span class="chip">Scalable systems</span><span class="chip">Clean UI/UX</span>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="projects">
  <div class="wrap">
    <div class="sec-head">
      <h2>Selected projects</h2>
      <span class="tag">// end-to-end builds</span>
    </div>
    <div class="projects">
      <div class="project-card">
        <span class="ptag">Full-Stack Platform</span>
        <h3>Oromia Tourism Management System</h3>
        <p>A full-stack platform built for the Oromia Tourism Commission, streamlining digital information access and helping promote regional tourism destinations online.</p>
        <div class="chip-row">
          <span class="chip">React.js</span><span class="chip">Node.js</span><span class="chip">PostgreSQL</span>
        </div>
        <a class="project-link" href="https://github.com/AbdiSerbessa" target="_blank" rel="noopener">View on GitHub ↗</a>
      </div>

      <div class="project-card">
        <span class="ptag">Enterprise System</span>
        <h3>Finance Management System</h3>
        <p>Built during my time at Mugher Cement Factory — a system to manage and track internal financial operations, improving accuracy and reducing manual processes.</p>
        <div class="chip-row">
          <span class="chip">JavaScript</span><span class="chip">Node.js</span><span class="chip">PostgreSQL</span>
        </div>
        <a class="project-link" href="https://github.com/AbdiSerbessa" target="_blank" rel="noopener">View on GitHub ↗</a>
      </div>

      <div class="project-card">
        <span class="ptag">In Training</span>
        <h3>Advanced Full Stack Projects</h3>
        <p>Ongoing project work as part of the Advanced Full Stack Development Training at IBT College of Canada, covering modern JS, React, Node.js and PostgreSQL practices.</p>
        <div class="chip-row">
          <span class="chip">React</span><span class="chip">Node.js</span><span class="chip">PostgreSQL</span>
        </div>
        <a class="project-link" href="https://github.com/AbdiSerbessa" target="_blank" rel="noopener">View on GitHub ↗</a>
      </div>
    </div>
  </div>
</section>

<section id="experience">
  <div class="wrap">
    <div class="sec-head">
      <h2>Experience &amp; education</h2>
      <span class="tag">// timeline</span>
    </div>
    <div class="timeline">
      <div class="tl-item">
        <span class="tl-date">Ongoing</span>
        <h3>Advanced Full Stack Development Training</h3>
        <span class="org">IBT College of Canada</span>
        <p>Intensive training in JavaScript, React, Node.js and PostgreSQL, focused on building production-grade full-stack applications.</p>
      </div>
      <div class="tl-item">
        <span class="tl-date">Prior role</span>
        <h3>Full Stack Developer</h3>
        <span class="org">Mugher Cement Factory</span>
        <p>Designed and built a Finance Management System to support internal financial operations and reporting.</p>
      </div>
      <div class="tl-item">
        <span class="tl-date">Education</span>
        <h3>B.Sc. in Software Engineering</h3>
        <span class="org">Adama Science and Technology University</span>
        <p>Graduated with a focus on software design, full-stack development, and database systems.</p>
      </div>
    </div>
  </div>
</section>

<section id="contact" class="contact">
  <div class="wrap">
    <div class="contact-box">
      <div>
        <h2>Let's build something.</h2>
        <p>Open to full-stack roles and freelance projects. Reach out by email or connect on LinkedIn and GitHub.</p>
      </div>
      <div class="contact-links">
        <a href="mailto:abdiserbess19@gmail.com"><span>Email</span><span>abdiserbess19@gmail.com</span></a>
        <a href="tel:+251943350427"><span>Phone</span><span>+251 943 350 427</span></a>
        <a href="https://www.linkedin.com/in/abdi-serbessa-8431442a0" target="_blank" rel="noopener"><span>LinkedIn</span><span>abdi-serbessa</span></a>
        <a href="https://github.com/AbdiSerbessa" target="_blank" rel="noopener"><span>GitHub</span><span>AbdiSerbessa</span></a>
        <a href="#"><span>Location</span><span>Addis Ababa, Ethiopia</span></a>
      </div>
    </div>
  </div>
</section>

<footer>© 2026 Abdi Serbessa — Full Stack Developer</footer>

</body>
</html>## Hi there 👋

<!--
**AbdiSerbessa/AbdiSerbessa** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
