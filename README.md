PORTFOLIO SOURCE CODE Shivnarayan Chaurasiya — Full Stack Developer
shivnarayanchaurasiya594@gmail.com
github.com/ShivnarayanChaurasiya | linkedin.com/in/shivnarayan-chaurasiya-285499322
FILE: portfolio.html
Stack: HTML5 | CSS3 | Vanilla JavaScript
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dev Portfolio | Full Stack Developer</title>
<link
href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap"
rel="stylesheet">
<style>
:root {
--bg: #0a0a0f;
--surface: #111118;
--card: #16161f;
--border: #2a2a3a;
--accent: #00e5ff;
--accent2: #ff6b35;
--accent3: #7c3aed;
--text: #e8e8f0;
--muted: #7070a0;
--font-head: 'Syne', sans-serif;
--font-mono: 'Space Mono', monospace;
}
* { margin: 0; padding: 0; box-sizing: border-box; }
html { scroll-behavior: smooth; }
body {
background: var(--bg);
color: var(--text);
font-family: var(--font-mono);
overflow-x: hidden;
}
/* Animated background grid */
body::before {
content: '';
position: fixed;
inset: 0;
background-image:
linear-gradient(rgba(0,229,255,0.03) 1px, transparent 1px),
linear-gradient(90deg, rgba(0,229,255,0.03) 1px, transparent 1px);
background-size: 60px 60px;
pointer-events: none;
z-index: 0;
}
/* ■■ NAV ■■ */
nav {
position: fixed;
top: 0; left: 0; right: 0;
z-index: 100;
display: flex;
justify-content: space-between;
align-items: center;
padding: 1.2rem 4rem;
background: rgba(10,10,15,0.85);
backdrop-filter: blur(16px);
border-bottom: 1px solid var(--border);
}
.logo {
font-family: var(--font-head);
font-size: 1.2rem;
font-weight: 800;
color: var(--accent);
letter-spacing: -1px;
}
.logo span { color: var(--accent2); }
nav ul {
list-style: none;
display: flex;
gap: 2.5rem;
}
nav a {
color: var(--muted);
text-decoration: none;
font-size: 0.75rem;
letter-spacing: 2px;
text-transform: uppercase;
transition: color 0.2s;
}
nav a:hover { color: var(--accent); }
.nav-cta {
background: var(--accent);
color: var(--bg) !important;
padding: 0.5rem 1.2rem;
font-weight: 700;
clip-path: polygon(8px 0%, 100% 0%, calc(100% - 8px) 100%, 0% 100%);
transition: background 0.2s, transform 0.2s !important;
}
.nav-cta:hover { background: var(--accent2) !important; transform: scale(1.05); }
/* ■■ HERO ■■ */
#hero {
min-height: 100vh;
display: flex;
align-items: center;
padding: 8rem 4rem 4rem;
position: relative;
z-index: 1;
}
.hero-inner {
max-width: 1200px;
margin: 0 auto;
width: 100%;
display: grid;
grid-template-columns: 1fr 1fr;
gap: 4rem;
align-items: center;
}
.hero-tag {
font-size: 0.7rem;
letter-spacing: 4px;
color: var(--accent);
text-transform: uppercase;
margin-bottom: 1.2rem;
display: flex;
align-items: center;
gap: 0.8rem;
}
.hero-tag::before {
content: '';
width: 40px;
height: 1px;
background: var(--accent);
}
h1 {
font-family: var(--font-head);
font-size: clamp(3rem, 6vw, 5.5rem);
font-weight: 800;
line-height: 1;
letter-spacing: -3px;
margin-bottom: 1.5rem;
}
h1 .line2 {
color: transparent;
-webkit-text-stroke: 1.5px var(--accent);
display: block;
}
h1 .line3 {
color: var(--accent2);
display: block;
}
.hero-desc {
color: var(--muted);
font-size: 0.85rem;
line-height: 1.9;
margin-bottom: 2.5rem;
max-width: 480px;
}
.hero-btns {
display: flex;
gap: 1rem;
flex-wrap: wrap;
}
.btn-primary {
background: var(--accent);
color: var(--bg);
padding: 0.9rem 2rem;
font-family: var(--font-mono);
font-size: 0.8rem;
font-weight: 700;
letter-spacing: 1px;
border: none;
cursor: pointer;
clip-path: polygon(10px 0%, 100% 0%, calc(100% - 10px) 100%, 0% 100%);
transition: all 0.2s;
text-decoration: none;
display: inline-block;
}
.btn-primary:hover { background: var(--accent2); transform: translateY(-2px); }
.btn-outline {
border: 1px solid var(--border);
color: var(--text);
padding: 0.9rem 2rem;
font-family: var(--font-mono);
font-size: 0.8rem;
letter-spacing: 1px;
background: transparent;
cursor: pointer;
transition: all 0.2s;
text-decoration: none;
display: inline-block;
}
.btn-outline:hover { border-color: var(--accent); color: var(--accent); }
/* Hero right: code block */
.hero-code {
background: var(--card);
border: 1px solid var(--border);
border-radius: 2px;
overflow: hidden;
position: relative;
}
.code-header {
background: var(--surface);
padding: 0.8rem 1.2rem;
display: flex;
align-items: center;
gap: 0.5rem;
border-bottom: 1px solid var(--border);
}
.dot { width: 10px; height: 10px; border-radius: 50%; }
.dot.r { background: #ff5f57; }
.dot.y { background: #febc2e; }
.dot.g { background: #28c840; }
.code-filename {
margin-left: auto;
font-size: 0.65rem;
color: var(--muted);
}
.code-body {
padding: 1.5rem;
font-size: 0.75rem;
line-height: 1.8;
overflow-x: auto;
}
.c-kw { color: #c792ea; }
.c-cls { color: #82aaff; }
.c-fn { color: #82aaff; }
.c-str { color: #c3e88d; }
.c-ann { color: #ffcb6b; }
.c-cm { color: #546e7a; }
.c-num { color: var(--accent2); }
/* ■■ SECTIONS ■■ */
section {
padding: 6rem 4rem;
position: relative;
z-index: 1;
}
.section-header {
max-width: 1200px;
margin: 0 auto 4rem;
}
.section-tag {
font-size: 0.65rem;
letter-spacing: 4px;
color: var(--accent2);
text-transform: uppercase;
margin-bottom: 0.8rem;
}
.section-title {
font-family: var(--font-head);
font-size: clamp(2rem, 4vw, 3rem);
font-weight: 800;
letter-spacing: -2px;
}
/* ■■ SKILLS ■■ */
#skills { background: var(--surface); }
.skills-grid {
max-width: 1200px;
margin: 0 auto;
display: grid;
grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
gap: 1.5rem;
}
.skill-card {
background: var(--card);
border: 1px solid var(--border);
padding: 2rem;
position: relative;
overflow: hidden;
transition: border-color 0.3s, transform 0.3s;
}
.skill-card::before {
content: '';
position: absolute;
top: 0; left: 0; right: 0;
height: 2px;
background: linear-gradient(90deg, var(--accent), var(--accent3));
transform: scaleX(0);
transform-origin: left;
transition: transform 0.3s;
}
.skill-card:hover { border-color: var(--accent); transform: translateY(-4px); }
.skill-card:hover::before { transform: scaleX(1); }
.skill-icon {
font-size: 2rem;
margin-bottom: 1rem;
}
.skill-name {
font-family: var(--font-head);
font-size: 1.1rem;
font-weight: 700;
margin-bottom: 0.5rem;
}
.skill-desc {
font-size: 0.72rem;
color: var(--muted);
line-height: 1.7;
margin-bottom: 1.2rem;
}
.skill-tags {
display: flex;
flex-wrap: wrap;
gap: 0.4rem;
}
.tag {
font-size: 0.6rem;
letter-spacing: 1px;
text-transform: uppercase;
padding: 0.3rem 0.7rem;
border: 1px solid var(--border);
color: var(--muted);
transition: all 0.2s;
}
.skill-card:hover .tag { border-color: var(--accent); color: var(--accent); }
/* ■■ PROJECTS ■■ */
#projects { background: var(--bg); }
.projects-grid {
max-width: 1200px;
margin: 0 auto;
display: grid;
grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
gap: 1.5rem;
}
.project-card {
background: var(--card);
border: 1px solid var(--border);
overflow: hidden;
transition: all 0.3s;
position: relative;
}
.project-card:hover { border-color: var(--accent2); transform: translateY(-6px); box-shadow: 0 20px 60px
rgba(255,107,53,0.1); }
.project-img {
height: 180px;
display: flex;
align-items: center;
justify-content: center;
font-size: 4rem;
position: relative;
overflow: hidden;
}
.project-img.p1 { background: linear-gradient(135deg, #0d1b2a, #1a3a5c); }
.project-img.p2 { background: linear-gradient(135deg, #1a0d2e, #3c1f7a); }
.project-img.p3 { background: linear-gradient(135deg, #0d2e1a, #1f7a3c); }
.project-body { padding: 1.5rem; }
.project-num {
font-size: 0.6rem;
color: var(--accent2);
letter-spacing: 3px;
margin-bottom: 0.5rem;
}
.project-title {
font-family: var(--font-head);
font-size: 1.2rem;
font-weight: 700;
margin-bottom: 0.8rem;
}
.project-desc {
font-size: 0.72rem;
color: var(--muted);
line-height: 1.7;
margin-bottom: 1.2rem;
}
.project-stack {
display: flex;
flex-wrap: wrap;
gap: 0.4rem;
margin-bottom: 1.5rem;
}
.stack-tag {
font-size: 0.6rem;
background: rgba(0,229,255,0.08);
color: var(--accent);
border: 1px solid rgba(0,229,255,0.2);
padding: 0.25rem 0.6rem;
letter-spacing: 1px;
}
.project-links { display: flex; gap: 0.8rem; }
.proj-link {
font-size: 0.65rem;
letter-spacing: 2px;
text-transform: uppercase;
color: var(--muted);
text-decoration: none;
transition: color 0.2s;
padding-bottom: 2px;
border-bottom: 1px solid var(--border);
}
.proj-link:hover { color: var(--accent); border-color: var(--accent); }
/* ■■ EXPERIENCE ■■ */
#experience { background: var(--surface); }
.timeline {
max-width: 800px;
margin: 0 auto;
position: relative;
}
.timeline::before {
content: '';
position: absolute;
left: 0;
top: 0; bottom: 0;
width: 1px;
background: linear-gradient(to bottom, var(--accent), transparent);
}
.timeline-item {
padding: 0 0 3rem 2.5rem;
position: relative;
}
.timeline-item::before {
content: '';
position: absolute;
left: -4px; top: 6px;
width: 9px; height: 9px;
background: var(--accent);
clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
}
.tl-date {
font-size: 0.65rem;
letter-spacing: 3px;
color: var(--accent2);
text-transform: uppercase;
margin-bottom: 0.5rem;
}
.tl-role {
font-family: var(--font-head);
font-size: 1.1rem;
font-weight: 700;
margin-bottom: 0.2rem;
}
.tl-company {
font-size: 0.75rem;
color: var(--muted);
margin-bottom: 0.8rem;
}
.tl-desc {
font-size: 0.72rem;
color: var(--muted);
line-height: 1.8;
}
/* ■■ CONTACT ■■ */
#contact { background: var(--bg); }
.contact-inner {
max-width: 700px;
margin: 0 auto;
text-align: center;
}
.contact-email {
font-family: var(--font-head);
font-size: clamp(1.5rem, 4vw, 2.5rem);
font-weight: 800;
color: var(--accent);
letter-spacing: -1px;
text-decoration: none;
display: block;
margin: 2rem 0;
transition: color 0.2s;
}
.contact-email:hover { color: var(--accent2); }
.social-links {
display: flex;
justify-content: center;
gap: 2rem;
margin-top: 2rem;
}
.social-link {
font-size: 0.7rem;
letter-spacing: 3px;
text-transform: uppercase;
color: var(--muted);
text-decoration: none;
transition: color 0.2s;
padding: 0.5rem 1rem;
border: 1px solid var(--border);
}
.social-link:hover { color: var(--accent); border-color: var(--accent); }
/* ■■ FOOTER ■■ */
footer {
border-top: 1px solid var(--border);
padding: 2rem 4rem;
display: flex;
justify-content: space-between;
align-items: center;
font-size: 0.65rem;
color: var(--muted);
letter-spacing: 2px;
position: relative;
z-index: 1;
}
/* ■■ ANIMATIONS ■■ */
@keyframes fadeUp {
from { opacity: 0; transform: translateY(30px); }
to { opacity: 1; transform: translateY(0); }
}
@keyframes blink {
0%, 100% { opacity: 1; }
50% { opacity: 0; }
}
.cursor {
display: inline-block;
width: 2px;
height: 1em;
background: var(--accent);
margin-left: 4px;
animation: blink 1s infinite;
vertical-align: middle;
}
.animate-in {
animation: fadeUp 0.7s ease both;
}
.delay-1 { animation-delay: 0.1s; }
.delay-2 { animation-delay: 0.2s; }
.delay-3 { animation-delay: 0.3s; }
.delay-4 { animation-delay: 0.4s; }
/* Glowing orbs */
.orb {
position: fixed;
border-radius: 50%;
filter: blur(120px);
pointer-events: none;
z-index: 0;
opacity: 0.12;
}
.orb1 { width: 600px; height: 600px; background: var(--accent3); top: -200px; right: -200px; }
.orb2 { width: 400px; height: 400px; background: var(--accent); bottom: 20%; left: -150px; }
/* Responsive */
@media (max-width: 768px) {
nav { padding: 1rem 1.5rem; }
nav ul { display: none; }
section, #hero { padding: 5rem 1.5rem 3rem; }
.hero-inner { grid-template-columns: 1fr; }
.hero-code { display: none; }
footer { flex-direction: column; gap: 0.5rem; text-align: center; }
}
</style>
</head>
<body>
<div class="orb orb1"></div>
<div class="orb orb2"></div>
<!-- NAV -->
<nav>
<div class="logo">Shivnarayan<span>.</span>dev</div>
<ul>
<li><a href="#skills">Skills</a></li>
<li><a href="#projects">Projects</a></li>
<li><a href="https://github.com/ShivnarayanChaurasiya" target="_blank">GitHub</a></li>
<li><a href="#contact" class="nav-cta">Hire Me</a></li>
</ul>
</nav>
<!-- HERO -->
<section id="hero">
<div class="hero-inner">
<div>
<div class="hero-tag animate-in">Open to freelance & internship opportunities</div>
<h1 class="animate-in delay-1">
Shivnarayan
<span class="line2">Chaurasiya</span>
<span class="line3">Developer</span>
</h1>
<p class="hero-desc animate-in delay-2">
Passionate <strong>Full Stack Developer</strong> skilled in <strong>Java</strong>, <strong>Spring
Boot</strong>, and <strong>JavaScript</strong>. I love building clean, functional web applications and RESTful APIs.
Currently looking for freelance projects and opportunities to grow.
</p>
<div class="hero-btns animate-in delay-3">
<a href="#projects" class="btn-primary">View Projects</a>
<a href="#contact" class="btn-outline">Get In Touch</a>
</div>
</div>
<!-- Code Block -->
<div class="hero-code animate-in delay-4">
<div class="code-header">
<div class="dot r"></div>
<div class="dot y"></div>
<div class="dot g"></div>
<span class="code-filename">DeveloperProfile.java</span>
</div>
<div class="code-body">
<pre><span class="c-ann">@RestController</span>
<span class="c-ann">@RequestMapping</span>(<span class="c-str">"/api/dev"</span>)
<span class="c-kw">public class</span> <span class="c-cls">DeveloperProfile</span> {
<span class="c-kw">private final</span> String name = <span class="c-str">"Shivnarayan Chaurasiya"</span>;
<span class="c-kw">private final</span> String role =
<span class="c-str">"Full Stack Developer"</span>;
<span class="c-ann">@GetMapping</span>(<span class="c-str">"/skills"</span>)
<span class="c-kw">public</span> List&lt;String&gt; <span class="c-fn">getSkills</span>() {
<span class="c-kw">return</span> Arrays.asList(
<span class="c-str">"Java"</span>, <span class="c-str">"Spring Boot"</span>,
<span class="c-str">"JavaScript"</span>, <span class="c-str">"HTML/CSS"</span>,
<span class="c-str">"REST APIs"</span>, <span class="c-str">"MySQL"</span>
);
}
<span class="c-ann">@GetMapping</span>(<span class="c-str">"/status"</span>)
<span class="c-kw">public</span> String <span class="c-fn">getStatus</span>() {
<span class="c-kw">return</span> <span class="c-str">"Open to work ■"</span>;
}
}</pre>
</div>
</div>
</div>
</section>
<!-- SKILLS -->
<section id="skills">
<div class="section-header">
<div class="section-tag">What I work with</div>
<h2 class="section-title">Technical Skills</h2>
</div>
<div class="skills-grid">
<div class="skill-card">
<div class="skill-icon">■</div>
<div class="skill-name">Java</div>
<div class="skill-desc">Core Java, OOP, Collections, Multithreading, JDBC, Maven/Gradle build tools.</div>
<div class="skill-tags">
<span class="tag">Java 17+</span>
<span class="tag">OOP</span>
<span class="tag">Collections</span>
<span class="tag">Maven</span>
</div>
</div>
<div class="skill-card">
<div class="skill-icon">■</div>
<div class="skill-name">Spring Boot</div>
<div class="skill-desc">Building RESTful APIs, microservices, Spring Security, JPA/Hibernate, Spring Data.</div>
<div class="skill-tags">
<span class="tag">REST API</span>
<span class="tag">Spring MVC</span>
<span class="tag">JPA</span>
<span class="tag">Security</span>
</div>
</div>
<div class="skill-card">
<div class="skill-icon">■</div>
<div class="skill-name">JavaScript</div>
<div class="skill-desc">ES6+, async/await, DOM manipulation, Fetch API, React basics, Node.js
fundamentals.</div>
<div class="skill-tags">
<span class="tag">ES6+</span>
<span class="tag">Async/Await</span>
<span class="tag">DOM</span>
<span class="tag">React</span>
</div>
</div>
<div class="skill-card">
<div class="skill-icon">■</div>
<div class="skill-name">HTML & CSS</div>
<div class="skill-desc">Semantic HTML5, Flexbox, Grid, responsive design, animations, Bootstrap/Tailwind.</div>
<div class="skill-tags">
<span class="tag">HTML5</span>
<span class="tag">CSS3</span>
<span class="tag">Responsive</span>
<span class="tag">Bootstrap</span>
</div>
</div>
<div class="skill-card">
<div class="skill-icon">■■</div>
<div class="skill-name">Databases</div>
<div class="skill-desc">MySQL, PostgreSQL, query optimization, schema design, Hibernate ORM integration.</div>
<div class="skill-tags">
<span class="tag">MySQL</span>
<span class="tag">PostgreSQL</span>
<span class="tag">Hibernate</span>
<span class="tag">SQL</span>
</div>
</div>
<div class="skill-card">
<div class="skill-icon">■■</div>
<div class="skill-name">Tools & DevOps</div>
<div class="skill-desc">Git, GitHub, Postman, IntelliJ IDEA, VS Code, Docker basics, Linux CLI.</div>
<div class="skill-tags">
<span class="tag">Git</span>
<span class="tag">Postman</span>
<span class="tag">Docker</span>
<span class="tag">Linux</span>
</div>
</div>
</div>
</section>
<!-- PROJECTS -->
<section id="projects">
<div class="section-header">
<div class="section-tag">What I've built</div>
<h2 class="section-title">Projects</h2>
</div>
<div class="projects-grid">
<div class="project-card">
<div class="project-img p1">■</div>
<div class="project-body">
<div class="project-num">01 / PROJECT</div>
<div class="project-title">E-Commerce REST API</div>
<div class="project-desc">Full-featured backend for an online store with product management, cart, orders, JWT
authentication, and payment integration.</div>
<div class="project-stack">
<span class="stack-tag">Spring Boot</span>
<span class="stack-tag">Java</span>
<span class="stack-tag">MySQL</span>
<span class="stack-tag">JWT</span>
</div>
<div class="project-links">
<a href="#" class="proj-link">GitHub →</a>
<a href="#" class="proj-link">Live Demo →</a>
</div>
</div>
</div>
<div class="project-card">
<div class="project-img p2">■</div>
<div class="project-body">
<div class="project-num">02 / PROJECT</div>
<div class="project-title">Task Manager App</div>
<div class="project-desc">Full-stack task management tool with React frontend, Spring Boot backend, real-time
updates, and user role management.</div>
<div class="project-stack">
<span class="stack-tag">React</span>
<span class="stack-tag">Spring Boot</span>
<span class="stack-tag">PostgreSQL</span>
<span class="stack-tag">REST</span>
</div>
<div class="project-links">
<a href="#" class="proj-link">GitHub →</a>
<a href="#" class="proj-link">Live Demo →</a>
</div>
</div>
</div>
<div class="project-card">
<div class="project-img p3">■</div>
<div class="project-body">
<div class="project-num">03 / PROJECT</div>
<div class="project-title">Chat Application</div>
<div class="project-desc">Real-time chat app using WebSockets and Spring Boot with user authentication, rooms,
and message history persistence.</div>
<div class="project-stack">
<span class="stack-tag">WebSockets</span>
<span class="stack-tag">Java</span>
<span class="stack-tag">JavaScript</span>
<span class="stack-tag">MySQL</span>
</div>
<div class="project-links">
<a href="#" class="proj-link">GitHub →</a>
<a href="#" class="proj-link">Live Demo →</a>
</div>
</div>
</div>
</div>
</section>
<!-- ABOUT / FRESHER -->
<section id="experience">
<div class="section-header">
<div class="section-tag">My journey</div>
<h2 class="section-title">About Me</h2>
</div>
<div class="timeline">
<div class="timeline-item">
<div class="tl-date">2025 — Present</div>
<div class="tl-role">Fresher — Actively Looking for Opportunities</div>
<div class="tl-company">Open to Internships & Freelance · Ghaziabad, India</div>
<div class="tl-desc">Passionate full stack developer eager to work on real-world projects. Building personal
projects using Java, Spring Boot, and JavaScript to sharpen my skills.</div>
</div>
<div class="timeline-item">
<div class="tl-date">Ongoing</div>
<div class="tl-role">Self-Learning & Project Building</div>
<div class="tl-company">Personal Development · Remote</div>
<div class="tl-desc">Continuously learning through online courses, documentation, and hands-on coding. Built
multiple projects involving REST APIs, Spring Boot backends, and JavaScript frontends.</div>
</div>
<div class="timeline-item">
<div class="tl-date">Education</div>
<div class="tl-role">Computer Science</div>
<div class="tl-company">Uttar Pradesh, India</div>
<div class="tl-desc">Strong foundation in Java, OOP, data structures, databases, and web development. Passionate
about backend development and building scalable systems.</div>
</div>
</div>
</section>
<!-- CONTACT -->
<section id="contact">
<div class="contact-inner">
<div class="section-tag" style="text-align:center">Let's work together</div>
<h2 class="section-title" style="text-align:center; letter-spacing:-2px;">Got a project<br>in mind?</h2>
<a href="mailto:shivnarayanchaurasiya594@gmail.com" class="contact-email">shivnarayanchaurasiya594@gmail.com<span
class="cursor"></span></a>
<p style="font-size:0.75rem; color:var(--muted); line-height:1.8;">
Available for freelance projects, internships, and full-time opportunities.<br>
Response time: within 24 hours.
</p>
<div class="social-links">
<a href="https://www.linkedin.com/in/shivnarayan-chaurasiya-285499322/" target="_blank"
class="social-link">LinkedIn</a>
<a href="https://github.com/ShivnarayanChaurasiya" target="_blank" class="social-link">GitHub</a>
<a href="mailto:shivnarayanchaurasiya594@gmail.com" class="social-link">Email ✉</a>
</div>
</div>
</section>
<!-- FOOTER -->
<footer>
<span>© 2026 — Shivnarayan Chaurasiya</span>
<span>Built with HTML · CSS · JavaScript</span>
<span>Ghaziabad, India ■■</span>
</footer>
<script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
// Scroll animations
const observer = new IntersectionObserver((entries) => {
entries.forEach(entry => {
if (entry.isIntersecting) {
entry.target.style.opacity = '1';
entry.target.style.transform = 'translateY(0)';
}
});
}, { threshold: 0.1 });
document.querySelectorAll('.skill-card, .project-card,
© 2026 Shivnarayan Chaurasiya — Ghaziabad, India ■■
