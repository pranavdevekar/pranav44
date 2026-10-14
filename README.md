<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>pranav devekar | Portfolio</title>
  <meta name="description" content="Personal portfolio website for a developer, designer, or creative professional." />
  <style>
    :root {
      --bg: #0f172a;
      --bg-soft: #111827;
      --panel: #1f2937;
      --panel-2: #0b1220;
      --text: #e5e7eb;
      --muted: #94a3b8;
      --primary: #7c3aed;
      --primary-2: #22c55e;
      --accent: #38bdf8;
      --border: rgba(148, 163, 184, 0.2);
      --shadow: 0 10px 30px rgba(0, 0, 0, 0.25);
      --radius: 18px;
      --container: 1120px;
    }

    * { box-sizing: border-box; }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      font-family: Arial, Helvetica, sans-serif;
      background: linear-gradient(135deg, var(--bg) 0%, var(--bg-soft) 100%);
      color: var(--text);
      line-height: 1.6;
    }

    img {
      max-width: 100%;
      display: block;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    .container {
      width: min(var(--container), calc(100% - 2rem));
      margin: 0 auto;
    }

    header {
      position: sticky;
      top: 0;
      z-index: 50;
      backdrop-filter: blur(14px);
      background: rgba(15, 23, 42, 0.7);
      border-bottom: 1px solid var(--border);
    }

    .nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      min-height: 70px;
    }

    .brand {
      font-size: 1.2rem;
      font-weight: 800;
      letter-spacing: 0.05em;
    }

    .brand span {
      color: var(--primary-2);
    }

    .nav-links {
      display: flex;
      gap: 1.5rem;
      align-items: center;
      flex-wrap: wrap;
    }

    .nav-links a {
      color: var(--muted);
      transition: color 0.2s ease;
      font-weight: 600;
    }

    .nav-links a:hover {
      color: var(--text);
    }

    .nav-links .btn {
      margin-left: 0.5rem;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 0.9rem 1.5rem;
      border-radius: 999px;
      border: 1px solid transparent;
      background: linear-gradient(135deg, var(--primary), var(--accent));
      color: white;
      font-weight: 700;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
      box-shadow: var(--shadow);
    }

    .btn:hover {
      transform: translateY(-2px);
    }

    .btn.secondary {
      background: transparent;
      border-color: var(--border);
      box-shadow: none;
    }

    section {
      padding: 5.5rem 0;
    }

    .hero {
      min-height: 90vh;
      display: flex;
      align-items: center;
      padding-top: 4rem;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.3fr 0.7fr;
      align-items: center;
      gap: 3rem;
    }

    .eyebrow {
      display: inline-block;
      padding: 0.45rem 0.9rem;
      background: rgba(124, 58, 237, 0.12);
      border: 1px solid rgba(124, 58, 237, 0.3);
      border-radius: 999px;
      color: #d8c3ff;
      font-size: 0.8rem;
      font-weight: 700;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      margin-bottom: 1.2rem;
    }

    h1 {
      font-size: clamp(2.8rem, 5vw, 5rem);
      line-height: 1.04;
      margin: 0 0 1rem;
      letter-spacing: -0.05em;
    }

    .gradient-text {
      background: linear-gradient(135deg, #c4b5fd 0%, #67e8f9 50%, #86efac 100%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .lead {
      max-width: 640px;
      color: var(--muted);
      font-size: 1.08rem;
      margin-bottom: 2rem;
    }

    .hero-actions {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
      margin-bottom: 2rem;
    }

    .socials {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .socials a {
      width: 42px;
      height: 42px;
      border-radius: 50%;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      background: rgba(255,255,255,0.03);
      border: 1px solid var(--border);
      color: var(--text);
      font-weight: 700;
      transition: transform 0.2s ease, border-color 0.2s ease;
    }

    .socials a:hover {
      transform: translateY(-2px);
      border-color: rgba(124, 58, 237, 0.4);
    }

    .profile-card {
      position: relative;
      background: linear-gradient(180deg, rgba(255,255,255,0.04), rgba(255,255,255,0.01));
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 1rem;
      box-shadow: var(--shadow);
    }

    .profile-photo {
      position: relative;
      border-radius: 22px;
      overflow: hidden;
      min-height: 520px;
      background:
        linear-gradient(135deg, rgba(124,58,237,0.3), rgba(56,189,248,0.2)),
        #172033;
      border: 1px solid rgba(255,255,255,0.08);
    }

    .profile-photo::before {
      content: "";
      position: absolute;
      inset: 20px;
      border-radius: 18px;
      background: radial-gradient(circle at 50% 20%, rgba(255,255,255,0.15), rgba(255,255,255,0.02) 35%, transparent 55%),
                  linear-gradient(180deg, rgba(15,23,42,0.2), rgba(15,23,42,0.8));
      border: 1px solid rgba(255,255,255,0.06);
    }

    .profile-badge {
      position: absolute;
      bottom: 20px;
      left: 20px;
      right: 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 1rem;
      padding: 1rem 1.1rem;
      border-radius: 16px;
      background: rgba(15, 23, 42, 0.7);
      border: 1px solid rgba(148,163,184,0.12);
      backdrop-filter: blur(8px);
    }

    .badge-title {
      font-size: 0.72rem;
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 0.08em;
    }

    .badge-value {
      font-size: 1.2rem;
      font-weight: 800;
      margin-top: 0.2rem;
    }

    .stats {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
      margin-top: 1.5rem;
    }

    .stat {
      flex: 1 1 120px;
      background: rgba(255,255,255,0.02);
      border: 1px solid var(--border);
      border-radius: 14px;
      padding: 0.9rem 1rem;
    }

    .stat strong {
      display: block;
      font-size: 1.5rem;
      margin-bottom: 0.2rem;
    }

    .stat span {
      color: var(--muted);
      font-size: 0.85rem;
    }

    .section-heading {
      margin-bottom: 2rem;
    }

    .section-heading h2 {
      margin: 0;
      font-size: clamp(2rem, 3vw, 3rem);
      letter-spacing: -0.04em;
    }

    .section-heading p {
      color: var(--muted);
      margin-top: 0.75rem;
      max-width: 650px;
    }

    .about-grid {
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 2rem;
      align-items: start;
    }

    .about-card, .skill-card, .project-card, .contact-card {
      background: rgba(255,255,255,0.02);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 1.5rem;
      box-shadow: var(--shadow);
    }

    .about-card p {
      color: var(--muted);
      margin: 0 0 1rem;
      font-size: 1.02rem;
    }

    .info-list {
      list-style: none;
      padding: 0;
      margin: 1.2rem 0 0;
      display: grid;
      gap: 0.75rem;
    }

    .info-list li {
      display: flex;
      justify-content: space-between;
      gap: 1rem;
      border-bottom: 1px solid var(--border);
      padding-bottom: 0.75rem;
      color: var(--muted);
    }

    .info-list li strong {
      color: var(--text);
      font-weight: 700;
    }

    .skills-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 1.5rem;
    }

    .skill-card h3 {
      margin-top: 0;
      margin-bottom: 1rem;
      font-size: 1.1rem;
    }

    .chip-list {
      display: flex;
      flex-wrap: wrap;
      gap: 0.7rem;
    }

    .chip {
      padding: 0.55rem 0.8rem;
      border-radius: 999px;
      background: rgba(124,58,237,0.12);
      border: 1px solid rgba(124,58,237,0.2);
      color: #e2d7ff;
      font-size: 0.85rem;
      font-weight: 700;
    }

    .projects-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 1.5rem;
    }

    .project-card {
      display: flex;
      flex-direction: column;
      gap: 1rem;
      overflow: hidden;
    }

    .project-thumb {
      height: 200px;
      border-radius: 14px;
      background: linear-gradient(135deg, rgba(124,58,237,0.4), rgba(56,189,248,0.24), rgba(34,197,94,0.2));
      border: 1px solid rgba(255,255,255,0.08);
      position: relative;
      overflow: hidden;
    }

    .project-thumb::before {
      content: "";
      position: absolute;
      inset: 18px;
      border-radius: 12px;
      background: rgba(15,23,42,0.42);
      border: 1px solid rgba(255,255,255,0.06);
    }

    .project-card h3 {
      margin: 0;
      font-size: 1.3rem;
    }

    .project-card p {
      color: var(--muted);
      margin: 0;
    }

    .project-links {
      margin-top: auto;
      display: flex;
      gap: 0.8rem;
      flex-wrap: wrap;
    }

    .project-links a {
      font-weight: 700;
      color: #dbeafe;
    }

    .contact-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.5rem;
    }

    .contact-card {
      min-height: 100%;
    }

    .contact-card h3 {
      margin-top: 0;
      margin-bottom: 0.75rem;
    }

    .contact-list {
      list-style: none;
      padding: 0;
      margin: 1rem 0 0;
      display: grid;
      gap: 0.9rem;
    }

    .contact-list li {
      display: flex;
      align-items: center;
      gap: 0.8rem;
      color: var(--muted);
    }

    .dot {
      width: 12px;
      height: 12px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--primary-2), var(--accent));
      box-shadow: 0 0 12px rgba(34,197,94,0.7);
    }

    form {
      display: grid;
      gap: 1rem;
    }

    .input-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
    }

    input, textarea {
      width: 100%;
      border: 1px solid var(--border);
      background: rgba(255,255,255,0.02);
      color: var(--text);
      border-radius: 12px;
      padding: 0.9rem 1rem;
      font: inherit;
      resize: vertical;
    }

    input::placeholder, textarea::placeholder {
      color: #8593a7;
    }

    footer {
      border-top: 1px solid var(--border);
      padding: 1.5rem 0 2.5rem;
      color: var(--muted);
      text-align: center;
    }

    @media (max-width: 900px) {
      .hero-grid,
      .about-grid,
      .contact-grid,
      .skills-grid,
      .projects-grid {
        grid-template-columns: 1fr;
      }

      .nav {
        flex-direction: column;
        justify-content: center;
        padding: 1rem 0;
      }

      .nav-links {
        justify-content: center;
      }
    }

    @media (max-width: 560px) {
      .input-row {
        grid-template-columns: 1fr;
      }

      .hero {
        padding-top: 2rem;
      }

      section {
        padding: 4rem 0;
      }

      .profile-photo {
        min-height: 420px;
      }
    }
  </style>
</head>
<body>
  <header>
    <div class="container nav">
      <a href="#home" class="brand">Your <span>Name</span></a>
      <nav class="nav-links" aria-label="Main navigation">
        <a href="#about">About</a>
        <a href="#skills">Skills</a>
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
        <a href="mailto:you@example.com" class="btn secondary">Hire Me</a>
      </nav>
    </div>
  </header>

  <main>
    <section id="home" class="hero">
      <div class="container hero-grid">
        <div>
          <div class="eyebrow">Full-Stack Developer</div>
          <h1>
            I build <span class="gradient-text">modern digital experiences</span> that stand out.
          </h1>
          <p class="lead">
            I’m Your Name, a passionate developer focused on creating clean, user-friendly, and high-performing websites and applications.
          </p>
          <div class="hero-actions">
            <a href="#projects" class="btn">View Projects</a>
            <a href="#contact" class="btn secondary">Contact Me</a>
          </div>

          <div class="socials" aria-label="Social media links">
            <a href="https://github.com/yourusername" target="_blank" rel="noreferrer" aria-label="GitHub">GH</a>
            <a href="https://linkedin.com/in/yourusername" target="_blank" rel="noreferrer" aria-label="LinkedIn">IN</a>
            <a href="https://twitter.com/yourusername" target="_blank" rel="noreferrer" aria-label="Twitter">X</a>
          </div>
        </div>

        <div class="profile-card">
          <div class="profile-photo" aria-label="Profile image area">
            <div class="profile-badge">
              <div>
                <div class="badge-title">Available for</div>
                <div class="badge-value">Freelance</div>
              </div>
              <div class="badge-value">+3 yrs</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="about">
      <div class="container">
        <div class="section-heading">
          <h2>About Me</h2>
          <p>
            I love turning ideas into useful, beautiful digital products with attention to detail,
            smooth performance, and great user experience.
          </p>
        </div>

        <div class="about-grid">
          <div class="about-card">
            <p>
              I’m a developer with experience in front-end and back-end technologies, building modern
              responsive websites, dashboards, and web apps for clients and startups.
            </p>
            <p>
              My work focuses on blending design, functionality, and performance to deliver products
              that are both visually compelling and technically solid.
            </p>

            <ul class="info-list">
              <li><span>Location</span> <strong>City, Country</strong></li>
              <li><span>Email</span> <strong>you@example.com</strong></li>
              <li><span>Experience</span> <strong>3+ Years</strong></li>
            </ul>
          </div>

          <div class="about-card">
            <div class="stats">
              <div class="stat">
                <strong>25+</strong>
                <span>Projects</span>
              </div>
              <div class="stat">
                <strong>8+</strong>
                <span>Clients</span>
              </div>
              <div class="stat">
                <strong>99%</strong>
                <span>Quality</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="skills">
      <div class="container">
        <div class="section-heading">
          <h2>Skills</h2>
          <p>Tools and technologies I use to design and build exceptional digital products.</p>
        </div>

        <div class="skills-grid">
          <div class="skill-card">
            <h3>Frontend</h3>
            <div class="chip-list">
              <span class="chip">HTML5</span>
              <span class="chip">CSS3</span>
              <span class="chip">JavaScript</span>
              <span class="chip">React</span>
              <span class="chip">Tailwind</span>
              <span class="chip">Bootstrap</span>
            </div>
          </div>

          <div class="skill-card">
            <h3>Backend</h3>
            <div class="chip-list">
              <span class="chip">Node.js</span>
              <span class="chip">Express</span>
              <span class="chip">MongoDB</span>
              <span class="chip">MySQL</span>
              <span class="chip">REST API</span>
              <span class="chip">Firebase</span>
            </div>
          </div>

          <div class="skill-card">
            <h3>Design & Workflow</h3>
            <div class="chip-list">
              <span class="chip">Figma</span>
              <span class="chip">UI/UX</span>
              <span class="chip">Git</span>
              <span class="chip">GitHub</span>
              <span class="chip">SEO</span>
              <span class="chip">Responsive Design</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="projects">
      <div class="container">
        <div class="section-heading">
          <h2>Featured Projects</h2>
          <p>Some of my recent work across web design, development, and digital product building.</p>
        </div>

        <div class="projects-grid">
          <article class="project-card">
            <div class="project-thumb"></div>
            <h3>Project One</h3>
            <p>
              A modern SaaS landing page designed to convert visitors into customers with responsive UI and clean visual hierarchy.
            </p>
            <div class="project-links">
              <a href="#">Live Demo</a>
              <a href="#">GitHub</a>
            </div>
          </article>

          <article class="project-card">
            <div class="project-thumb"></div>
            <h3>Project Two</h3>
            <p>
              A dashboard for tracking business metrics, built with real-time charts, data filters, and a highly usable interface.
            </p>
            <div class="project-links">
              <a href="#">Live Demo</a>
              <a href="#">GitHub</a>
            </div>
          </article>

          <article class="project-card">
            <div class="project-thumb"></div>
            <h3>Project Three</h3>
            <p>
              An e-commerce storefront focused on product discovery, performance optimization, and conversion-focused UX.
            </p>
            <div class="project-links">
              <a href="#">Live Demo</a>
              <a href="#">GitHub</a>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section id="contact">
      <div class="container">
        <div class="section-heading">
          <h2>Let’s Work Together</h2>
          <p>Have a project in mind or want to collaborate? I’d love to hear from you.</p>
        </div>

        <div class="contact-grid">
          <div class="contact-card">
            <h3>Contact Details</h3>
            <ul class="contact-list">
              <li><span class="dot"></span> <span>Email: you@example.com</span></li>
              <li><span class="dot"></span> <span>Phone: +12 345 678 901</span></li>
              <li><span class="dot"></span> <span>Location: City, Country</span></li>
              <li><span class="dot"></span> <span>GitHub: github.com/yourusername</span></li>
            </ul>
          </div>

          <div class="contact-card">
            <h3>Send a Message</h3>
            <form action="#" method="post">
              <div class="input-row">
                <input type="text" name="name" placeholder="Your Name" />
                <input type="email" name="email" placeholder="Your Email" />
              </div>
              <input type="text" name="subject" placeholder="Subject" />
              <textarea name="message" rows="5" placeholder="Your Message"></textarea>
              <button type="submit" class="btn">Send Message</button>
            </form>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      © <span id="year"></span> Your Name. All rights reserved.
    </div>
  </footer>

  <script>
    document.getElementById("year").textContent = new Date().getFullYear();
  </script>
</body>
</html>
