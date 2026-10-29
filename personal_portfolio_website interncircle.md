```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <!-- Viewport Meta Tag for Mobile Responsiveness -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Alex Morgan | Data Analyst & Web Developer</title>
  
  <!-- Font Awesome Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">

  <style>
    /* CSS RESETS & RELATIVE UNITS (rem) */
    *, *::before, *::after {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      font-size: 100%; /* 1rem = 16px */
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Inter', system-ui, -apple-system, sans-serif;
      line-height: 1.6;
      color: #334155;
      background-color: #f8fafc;
    }

    /* HEADER & NAVIGATION (Flexbox) */
    header {
      position: sticky;
      top: 0;
      z-index: 1000;
      background-color: rgba(15, 23, 42, 0.95);
      backdrop-filter: blur(8px);
      color: #ffffff;
      padding: 1rem 1.5rem;
      box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
    }

    .nav-container {
      max-width: 70rem;
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .logo {
      font-size: 1.25rem;
      font-weight: 700;
      color: #38bdf8;
      text-decoration: none;
    }

    nav ul {
      display: flex;
      list-style: none;
      gap: 1.5rem;
      flex-wrap: wrap;
    }

    nav a {
      color: #cbd5e1;
      text-decoration: none;
      font-weight: 500;
      font-size: 0.95rem;
      transition: color 0.2s ease;
    }

    nav a:hover {
      color: #38bdf8;
    }

    /* MAIN CONTENT LAYOUT */
    main {
      max-width: 70rem;
      margin: 0 auto;
      padding: 2rem 1.5rem;
    }

    section {
      margin-bottom: 4rem;
      scroll-margin-top: 5rem;
    }

    /* HEADINGS HIERARCHY */
    h1 {
      font-size: 2.5rem;
      font-weight: 800;
      color: #0f172a;
      line-height: 1.2;
      margin-bottom: 1rem;
    }

    h2 {
      font-size: 1.75rem;
      font-weight: 700;
      color: #0f172a;
      margin-bottom: 1.5rem;
      position: relative;
      padding-bottom: 0.5rem;
    }

    h2::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 0;
      width: 3.5rem;
      height: 0.25rem;
      background-color: #0284c7;
      border-radius: 0.125rem;
    }

    /* ABOUT / HERO SECTION (Flexbox) */
    .hero {
      display: flex;
      align-items: center;
      gap: 2.5rem;
      background-color: #ffffff;
      padding: 2.5rem;
      border-radius: 1rem;
      border: 1px solid #e2e8f0;
      box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1);
    }

    .hero-text {
      flex: 2;
    }

    .hero-text p {
      font-size: 1.1rem;
      color: #475569;
      margin-bottom: 1.5rem;
    }

    .badge {
      display: inline-block;
      background-color: #e0f2fe;
      color: #0369a1;
      font-weight: 600;
      font-size: 0.85rem;
      padding: 0.35rem 0.85rem;
      border-radius: 1rem;
      margin-bottom: 1rem;
    }

    .hero-avatar {
      flex: 1;
      display: flex;
      justify-content: center;
    }

    .avatar-img {
      width: 100%;
      max-width: 14rem;
      height: auto;
      border-radius: 50%;
      border: 4px solid #38bdf8;
      object-fit: cover;
    }

    /* SKILLS SECTION (CSS Grid) */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(15rem, 1fr));
      gap: 1.5rem;
    }

    .skill-card {
      background-color: #ffffff;
      padding: 1.5rem;
      border-radius: 0.75rem;
      border: 1px solid #e2e8f0;
      box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
    }

    .skill-card h3 {
      font-size: 1.1rem;
      color: #0f172a;
      margin-bottom: 0.75rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .skill-card h3 i {
      color: #0284c7;
    }

    .skill-list {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
      list-style: none;
    }

    .skill-tag {
      background-color: #f1f5f9;
      color: #334155;
      font-size: 0.85rem;
      font-weight: 500;
      padding: 0.3rem 0.7rem;
      border-radius: 0.375rem;
    }

    /* PROJECTS SECTION (CSS Grid) */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(18rem, 1fr));
      gap: 1.5rem;
    }

    .project-card {
      background-color: #ffffff;
      border-radius: 0.75rem;
      border: 1px solid #e2e8f0;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }

    .project-card:hover {
      transform: translateY(-0.25rem);
      box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
    }

    .project-content {
      padding: 1.5rem;
      display: flex;
      flex-direction: column;
      flex-grow: 1;
    }

    .project-title {
      font-size: 1.25rem;
      color: #0f172a;
      margin-bottom: 0.5rem;
    }

    .project-desc {
      font-size: 0.95rem;
      color: #64748b;
      margin-bottom: 1.25rem;
      flex-grow: 1;
    }

    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.4rem;
      margin-bottom: 1.25rem;
      list-style: none;
    }

    .project-tag {
      font-size: 0.75rem;
      background-color: #e2e8f0;
      color: #475569;
      padding: 0.2rem 0.5rem;
      border-radius: 0.25rem;
      font-weight: 600;
    }

    .project-link {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      color: #0284c7;
      text-decoration: none;
      font-weight: 600;
      font-size: 0.9rem;
    }

    .project-link:hover {
      text-decoration: underline;
    }

    /* CONTACT SECTION (Flexbox) */
    .contact-card {
      background-color: #0f172a;
      color: #ffffff;
      padding: 2.5rem;
      border-radius: 1rem;
      text-align: center;
    }

    .contact-card h2 {
      color: #ffffff;
    }

    .contact-card h2::after {
      left: 50%;
      transform: translateX(-50%);
    }

    .contact-card p {
      color: #94a3b8;
      max-width: 35rem;
      margin: 0 auto 2rem auto;
    }

    .contact-links {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 1rem;
      list-style: none;
    }

    .btn-contact {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      background-color: #0284c7;
      color: #ffffff;
      text-decoration: none;
      padding: 0.75rem 1.5rem;
      border-radius: 0.5rem;
      font-weight: 600;
      transition: background-color 0.2s ease;
    }

    .btn-contact:hover {
      background-color: #0369a1;
    }

    .btn-secondary {
      background-color: #334155;
    }

    .btn-secondary:hover {
      background-color: #475569;
    }

    /* FOOTER */
    footer {
      text-align: center;
      padding: 2rem 1.5rem;
      color: #64748b;
      font-size: 0.875rem;
      border-t: 1px solid #e2e8f0;
      background-color: #ffffff;
    }

    /* MEDIA QUERIES (Mobile responsiveness) */
    @media (max-width: 48rem) {
      .hero {
        flex-direction: column-reverse;
        text-align: center;
        padding: 1.5rem;
      }

      h1 {
        font-size: 2rem;
      }

      h2::after {
        left: 50%;
        transform: translateX(-50%);
      }

      .nav-container {
        flex-direction: column;
      }

      nav ul {
        justify-content: center;
      }
    }
  </style>
</head>
<body>

  <!-- Semantic Header & Navigation -->
  <header>
    <div class="nav-container">
      <a href="#" class="logo">&lt;AlexMorgan /&gt;</a>
      <nav>
        <ul>
          <li><a href="#about">About</a></li>
          <li><a href="#skills">Skills</a></li>
          <li><a href="#projects">Projects</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <!-- Main Content -->
  <main>

    <!-- About / Introduction Section -->
    <section id="about">
      <article class="hero">
        <div class="hero-text">
          <span class="badge">Open for Internships & Full-Time Roles</span>
          <h1>Data Analyst & Web Developer</h1>
          <p>
            Hello! I am Alex, a passionate technology student building dynamic data visualizations, automated reporting pipelines, and responsive web applications. I bridge data analysis with modern front-end web tools.
          </p>
          <a href="#projects" class="btn-contact">
            View My Work <i class="fa-solid fa-arrow-down"></i>
          </a>
        </div>
        <div class="hero-avatar">
          <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&q=80&w=400" alt="Alex Morgan Portfolio Avatar" class="avatar-img" width="400" height="400">
        </div>
      </article>
    </section>

    <!-- Skills Section (CSS Grid) -->
    <section id="skills">
      <h2>Technical Skills</h2>
      <div class="skills-grid">
        
        <div class="skill-card">
          <h3><i class="fa-solid fa-code"></i> Front-End Development</h3>
          <ul class="skill-list">
            <li class="skill-tag">HTML5</li>
            <li class="skill-tag">CSS3 / Flexbox</li>
            <li class="skill-tag">CSS Grid</li>
            <li class="skill-tag">JavaScript (ES6+)</li>
            <li class="skill-tag">Tailwind CSS</li>
          </ul>
        </div>

        <div class="skill-card">
          <h3><i class="fa-solid fa-chart-pie"></i> Data Analytics & Viz</h3>
          <ul class="skill-list">
            <li class="skill-tag">Python (Pandas)</li>
            <li class="skill-tag">Chart.js</li>
            <li class="skill-tag">Power BI</li>
            <li class="skill-tag">SQL</li>
            <li class="skill-tag">Excel / CSV Processing</li>
          </ul>
        </div>

        <div class="skill-card">
          <h3><i class="fa-solid fa-screwdriver-wrench"></i> Tools & Workflow</h3>
          <ul class="skill-list">
            <li class="skill-tag">Git / GitHub</li>
            <li class="skill-tag">GitHub Pages</li>
            <li class="skill-tag">VS Code</li>
            <li class="skill-tag">Figma</li>
          </ul>
        </div>

      </div>
    </section>

    <!-- Projects Section (CSS Grid) -->
    <section id="projects">
      <h2>Featured Projects</h2>
      <div class="projects-grid">

        <article class="project-card">
          <div class="project-content">
            <h3 class="project-title">Sales & Revenue Dashboard</h3>
            <p class="project-desc">
              An interactive sales analytics dashboard supporting CSV imports, custom dynamic slicers, KPI summary metrics, and business insights.
            </p>
            <ul class="project-tags">
              <li class="project-tag">HTML5</li>
              <li class="project-tag">Chart.js</li>
              <li class="project-tag">Tailwind</li>
            </ul>
            <a href="https://github.com/" target="_blank" rel="noopener noreferrer" class="project-link">
              View Repository <i class="fa-solid fa-arrow-up-right-from-square"></i>
            </a>
          </div>
        </article>

        <article class="project-card">
          <div class="project-content">
            <h3 class="project-title">Customer Segmentation Engine</h3>
            <p class="project-desc">
              In-browser K-Means clustering tool evaluating Recency, Frequency, and Monetary (RFM) customer behavior cohorts.
            </p>
            <ul class="project-tags">
              <li class="project-tag">JavaScript</li>
              <li class="project-tag">Machine Learning</li>
              <li class="project-tag">Chart.js</li>
            </ul>
            <a href="https://github.com/" target="_blank" rel="noopener noreferrer" class="project-link">
              View Repository <i class="fa-solid fa-arrow-up-right-from-square"></i>
            </a>
          </div>
        </article>

        <article class="project-card">
          <div class="project-content">
            <h3 class="project-title">AutoClean & Report Studio</h3>
            <p class="project-desc">
              Automated data preprocessing workflow cleaning nulls, deduplicating records, and rendering dynamic audit reports.
            </p>
            <ul class="project-tags">
              <li class="project-tag">Data Preprocessing</li>
              <li class="project-tag">PapaParse</li>
              <li class="project-tag">UI Automation</li>
            </ul>
            <a href="https://github.com/" target="_blank" rel="noopener noreferrer" class="project-link">
              View Repository <i class="fa-solid fa-arrow-up-right-from-square"></i>
            </a>
          </div>
        </article>

      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
      <div class="contact-card">
        <h2>Let's Connect</h2>
        <p>
          I am currently available for data analytics and front-end development internship opportunities. Feel free to reach out via email or LinkedIn!
        </p>
        <ul class="contact-links">
          <li>
            <a href="mailto:alex.morgan@example.com" class="btn-contact">
              <i class="fa-solid fa-envelope"></i> Email Me
            </a>
          </li>
          <li>
            <a href="https://linkedin.com" target="_blank" rel="noopener noreferrer" class="btn-contact btn-secondary">
              <i class="fa-brands fa-linkedin"></i> LinkedIn
            </a>
          </li>
          <li>
            <a href="https://github.com" target="_blank" rel="noopener noreferrer" class="btn-contact btn-secondary">
              <i class="fa-brands fa-github"></i> GitHub
            </a>
          </li>
        </ul>
      </div>
    </section>

  </main>

  <!-- Semantic Footer -->
  <footer>
    <p>&copy; 2026 Alex Morgan. Built with semantic HTML5 &amp; CSS Grid/Flexbox for Internship Submission.</p>
  </footer>

</body>
</html>
```