<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Alex Morgan | Software Engineer & Designer</title>
  <style>
    :root {
      --bg: #090d16;
      --card: rgba(255, 255, 255, 0.03);
      --card-hover: rgba(255, 255, 255, 0.06);
      --border: rgba(255, 255, 255, 0.08);
      --border-focus: #6366f1;
      --text: #f8fafc;
      --text-muted: #94a3b8;
      --accent: #6366f1;
      --accent-gradient: linear-gradient(135deg, #6366f1 0%, #a855f7 100%);
      --tag-bg: rgba(99, 102, 241, 0.12);
      --tag-text: #818cf8;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
    }

    body {
      background-color: var(--bg);
      color: var(--text);
      line-height: 1.6;
      scroll-behavior: smooth;
    }

    /* Container & Layout */
    .container {
      max-width: 1080px;
      margin: 0 auto;
      padding: 0 1.5rem;
    }

    /* Navigation */
    nav {
      position: sticky;
      top: 0;
      z-index: 50;
      backdrop-filter: blur(16px);
      background: rgba(9, 13, 22, 0.85);
      border-bottom: 1px solid var(--border);
    }

    .nav-inner {
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 70px;
    }

    .nav-logo {
      font-weight: 700;
      font-size: 1.15rem;
      letter-spacing: -0.5px;
      color: var(--text);
      text-decoration: none;
    }

    .nav-links {
      display: flex;
      gap: 1.75rem;
      list-style: none;
    }

    .nav-links a {
      color: var(--text-muted);
      text-decoration: none;
      font-size: 0.9rem;
      font-weight: 500;
      transition: color 0.2s;
    }

    .nav-links a:hover {
      color: var(--text);
    }

    /* Hero Section */
    .hero {
      padding: 6rem 0 4rem;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 4px 12px;
      border-radius: 9999px;
      background: rgba(34, 197, 94, 0.1);
      color: #4ade80;
      font-size: 0.8rem;
      font-weight: 600;
      margin-bottom: 1.5rem;
      border: 1px solid rgba(34, 197, 94, 0.2);
    }

    .badge::before {
      content: "";
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background: #22c55e;
    }

    .hero h1 {
      font-size: clamp(2.5rem, 5vw, 3.75rem);
      font-weight: 800;
      line-height: 1.15;
      letter-spacing: -1px;
      margin-bottom: 1.25rem;
    }

    .highlight {
      background: var(--accent-gradient);
      -webkit-background-clip: text;
      -webkit-fill-color: transparent;
      -webkit-text-fill-color: transparent;
    }

    .hero p {
      font-size: 1.15rem;
      color: var(--text-muted);
      max-width: 650px;
      margin-bottom: 2rem;
    }

    .hero-actions {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 0.75rem 1.5rem;
      border-radius: 8px;
      font-weight: 600;
      font-size: 0.9rem;
      text-decoration: none;
      cursor: pointer;
      transition: all 0.2s ease;
      border: 1px solid transparent;
    }

    .btn-primary {
      background: var(--accent);
      color: #fff;
    }

    .btn-primary:hover {
      opacity: 0.9;
      transform: translateY(-2px);
    }

    .btn-secondary {
      background: var(--card);
      border-color: var(--border);
      color: var(--text);
    }

    .btn-secondary:hover {
      background: var(--card-hover);
      transform: translateY(-2px);
    }

    /* Shared Section Headers */
    .section {
      padding: 5rem 0;
      border-top: 1px solid var(--border);
    }

    .section-title {
      margin-bottom: 2.5rem;
    }

    .section-title h2 {
      font-size: 1.75rem;
      font-weight: 700;
      letter-spacing: -0.5px;
      margin-bottom: 0.5rem;
    }

    .section-title p {
      color: var(--text-muted);
      font-size: 0.95rem;
    }

    /* Skills Grid */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(130px, 1fr));
      gap: 1rem;
    }

    .skill-card {
      background: var(--card);
      border: 1px solid var(--border);
      padding: 1rem;
      border-radius: 8px;
      text-align: center;
      font-size: 0.9rem;
      font-weight: 500;
      color: var(--text-muted);
      transition: border-color 0.2s, color 0.2s;
    }

    .skill-card:hover {
      border-color: var(--accent);
      color: var(--text);
    }

    /* Projects Grid */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 1.5rem;
    }

    .project-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 1.75rem;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      transition: transform 0.2s, border-color 0.2s;
    }

    .project-card:hover {
      transform: translateY(-4px);
      border-color: rgba(99, 102, 241, 0.4);
    }

    .project-card h3 {
      font-size: 1.25rem;
      margin-bottom: 0.5rem;
    }

    .project-card p {
      color: var(--text-muted);
      font-size: 0.9rem;
      margin-bottom: 1.25rem;
    }

    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
      margin-bottom: 1.5rem;
    }

    .tag {
      font-size: 0.75rem;
      padding: 2px 8px;
      border-radius: 4px;
      background: var(--tag-bg);
      color: var(--tag-text);
      font-weight: 500;
    }

    .project-links {
      display: flex;
      gap: 1rem;
    }

    .project-links a {
      color: var(--text);
      font-size: 0.85rem;
      text-decoration: none;
      font-weight: 600;
      display: inline-flex;
      align-items: center;
      gap: 4px;
    }

    .project-links a:hover {
      color: var(--accent);
    }

    /* Experience Timeline */
    .timeline {
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
    }

    .timeline-item {
      background: var(--card);
      border: 1px solid var(--border);
      padding: 1.5rem;
      border-radius: 10px;
    }

    .timeline-header {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      flex-wrap: wrap;
      gap: 0.5rem;
      margin-bottom: 0.5rem;
    }

    .timeline-header h3 {
      font-size: 1.1rem;
    }

    .timeline-header span {
      color: var(--text-muted);
      font-size: 0.85rem;
    }

    .timeline-company {
      color: var(--accent);
      font-size: 0.9rem;
      font-weight: 600;
      margin-bottom: 0.75rem;
    }

    .timeline-item p {
      color: var(--text-muted);
      font-size: 0.9rem;
    }

    /* Contact Section */
    .contact-box {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 2.5rem;
      max-width: 600px;
      margin: 0 auto;
    }

    .form-group {
      margin-bottom: 1.25rem;
    }

    label {
      display: block;
      font-size: 0.85rem;
      color: var(--text-muted);
      margin-bottom: 0.4rem;
    }

    input, textarea {
      width: 100%;
      padding: 0.75rem 1rem;
      border-radius: 8px;
      border: 1px solid var(--border);
      background: rgba(0, 0, 0, 0.2);
      color: var(--text);
      font-size: 0.95rem;
      outline: none;
      transition: border-color 0.2s;
    }

    input:focus, textarea:focus {
      border-color: var(--border-focus);
    }

    /* Footer */
    footer {
      border-top: 1px solid var(--border);
      padding: 2rem 0;
      text-align: center;
      color: var(--text-muted);
      font-size: 0.85rem;
    }

    @media (max-width: 640px) {
      .nav-links { display: none; }
      .hero { padding: 4rem 0 3rem; }
      .contact-box { padding: 1.5rem; }
    }
  </style>
</head>
<body>

  <!-- Navbar -->
  <nav>
    <div class="container nav-inner">
      <a href="#" class="nav-logo">AM.</a>
      <ul class="nav-links">
        <li><a href="#about">About</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#experience">Experience</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
  </nav>

  <main class="container">
    <!-- Hero -->
    <section class="hero" id="about">
      <div class="badge">Available for full-time roles & freelance</div>
      <h1>Building resilient systems & <span class="highlight">intuitive digital products.</span></h1>
      <p>I am a full-stack engineer and UI designer specializing in TypeScript, React, Python, and scalable cloud architectures.</p>
      <div class="hero-actions">
        <a href="#projects" class="btn btn-primary">View Projects</a>
        <a href="#contact" class="btn btn-secondary">Get in Touch</a>
      </div>
    </section>

    <!-- Skills -->
    <section class="section" id="skills">
      <div class="section-title">
        <h2>Tech Stack & Capabilities</h2>
        <p>Core tools and frameworks I use to build production systems.</p>
      </div>
      <div class="skills-grid">
        <div class="skill-card">TypeScript</div>
        <div class="skill-card">React / Next.js</div>
        <div class="skill-card">Node.js</div>
        <div class="skill-card">Python</div>
        <div class="skill-card">PostgreSQL</div>
        <div class="skill-card">Docker</div>
        <div class="skill-card">Tailwind CSS</div>
        <div class="skill-card">GraphQL / REST</div>
      </div>
    </section>

    <!-- Projects -->
    <section class="section" id="projects">
      <div class="section-title">
        <h2>Featured Work</h2>
        <p>Selected applications, tools, and technical experiments.</p>
      </div>
      <div class="projects-grid">
        <div class="project-card">
          <div>
            <h3>FlowTrace APM</h3>
            <p>A distributed telemetry dashboard that monitors real-time database query latency and microservice health metrics.</p>
            <div class="project-tags">
              <span class="tag">Next.js</span>
              <span class="tag">TypeScript</span>
              <span class="tag">PostgreSQL</span>
              <span class="tag">Tailwind</span>
            </div>
          </div>
          <div class="project-links">
            <a href="#">Live Preview &rarr;</a>
            <a href="#">GitHub &rarr;</a>
          </div>
        </div>

        <div class="project-card">
          <div>
            <h3>Inventory Pulse</h3>
            <p>An enterprise material logistics system supporting raw movement reconciliation, batching, and production yield tracking.</p>
            <div class="project-tags">
              <span class="tag">React</span>
              <span class="tag">Node.js</span>
              <span class="tag">Docker</span>
              <span class="tag">REST API</span>
            </div>
          </div>
          <div class="project-links">
            <a href="#">Live Preview &rarr;</a>
            <a href="#">GitHub &rarr;</a>
          </div>
        </div>

        <div class="project-card">
          <div>
            <h3>VectorSearch CLI</h3>
            <p>Lightweight embedding search tool designed to index and query local markdown notes with zero network overhead.</p>
            <div class="project-tags">
              <span class="tag">Python</span>
              <span class="tag">FastAPI</span>
              <span class="tag">SQLite</span>
            </div>
          </div>
          <div class="project-links">
            <a href="#">Live Preview &rarr;</a>
            <a href="#">GitHub &rarr;</a>
          </div>
        </div>
      </div>
    </section>

    <!-- Experience -->
    <section class="section" id="experience">
      <div class="section-title">
        <h2>Work Experience</h2>
        <p>Career trajectory and technical contributions.</p>
      </div>
      <div class="timeline">
        <div class="timeline-item">
          <div class="timeline-header">
            <h3>Senior Frontend Engineer</h3>
            <span>2024 — Present</span>
          </div>
          <div class="timeline-company">Nexus Cloud Solutions</div>
          <p>Architected customer-facing analytics dashboards reducing load times by 42%. Mentored junior engineers and led the migration to Next.js App Router.</p>
        </div>

        <div class="timeline-item">
          <div class="timeline-header">
            <h3>Full-Stack Developer</h3>
            <span>2022 — 2024</span>
          </div>
          <div class="timeline-company">Aura Labs</div>
          <p>Built RESTful microservices in Node.js/Express, implemented role-based auth with OAuth2, and managed automated CI/CD deployment pipelines on AWS.</p>
        </div>
      </div>
    </section>

    <!-- Contact Form -->
    <section class="section" id="contact">
      <div class="section-title" style="text-align: center;">
        <h2>Let's Connect</h2>
        <p>Have a project in mind or interested in hiring? Drop a line below.</p>
      </div>
      <div class="contact-box">
        <form id="contactForm">
          <div class="form-group">
            <label for="name">Name</label>
            <input type="text" id="name" placeholder="Jane Doe" required />
          </div>
          <div class="form-group">
            <label for="email">Email</label>
            <input type="email" id="email" placeholder="jane@example.com" required />
          </div>
          <div class="form-group">
            <label for="message">Message</label>
            <textarea id="message" rows="4" placeholder="Tell me about your project..." required></textarea>
          </div>
          <button type="submit" class="btn btn-primary" style="width: 100%; justify-content: center;">Send Message</button>
        </form>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      <p>&copy; 2026 Alex Morgan. Built with semantic HTML & vanilla CSS.</p>
    </div>
  </footer>

  <script>
    document.getElementById('contactForm').addEventListener('submit', function(e) {
      e.preventDefault();
      const name = document.getElementById('name').value;
      alert(`Thanks for reaching out, ${name}! Your message has been recorded.`);
      this.reset();
    });
  </script>
</body>
</html># Factory-Manager