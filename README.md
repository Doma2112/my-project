<!doctype html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width,initial-scale=1" />
    <title>Moh — Personal Homepage</title>
    <meta name="description" content="Personal homepage of Moh, a web designer and developer specializing in accessible, responsive web experiences." />
    <meta name="author" content="Moh" />
    <style>
        :root{
            --bg:#0f1724; --card:#0b1220; --muted:#94a3b8; --accent:#38bdf8; --glass: rgba(255,255,255,0.04);
            --radius:12px; --max-w:1100px; --gap:20px; font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
        }
        *{box-sizing:border-box}
        html,body{height:100%}
        body{
            margin:0;
            background:linear-gradient(180deg,#071022 0%,#071427 60%);
            color: #e6eef6;
            -webkit-font-smoothing:antialiased;
            -moz-osx-font-smoothing:grayscale;
            line-height:1.45;
            padding:36px 20px;
            display:flex;
            justify-content:center;
            align-items:flex-start;
        }
        .container{
            width:100%;
            max-width:var(--max-w);
        }
        header{
            display:flex;
            align-items:center;
            justify-content:space-between;
            gap:12px;
            margin-bottom:28px;
        }
        .brand{
            display:flex;
            gap:12px;
            align-items:center;
            text-decoration:none;
            color:inherit;
        }
        .logo{
            width:44px;height:44px;border-radius:10px;background:linear-gradient(135deg,var(--accent),#60a5fa);
            display:inline-grid;place-items:center;font-weight:700;color:#04263b;
            box-shadow:0 6px 18px rgba(8,20,30,0.6);
        }
        nav{display:flex;gap:12px;align-items:center}
        .nav-link{
            color:var(--muted);text-decoration:none;padding:8px 10px;border-radius:8px;font-size:0.95rem;
        }
        .nav-link:hover{color:var(--accent);background:var(--glass)}
        .cta{
            background:var(--accent);color:#04263b;padding:8px 14px;border-radius:10px;text-decoration:none;font-weight:600;
            box-shadow:0 6px 18px rgba(56,189,248,0.08);
        }

        main{
            background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
            border-radius:var(--radius);
            padding:28px;
            box-shadow: 0 10px 30px rgba(2,6,23,0.6);
            backdrop-filter: blur(6px);
        }

        .hero{
            display:grid;
            grid-template-columns:1fr 360px;
            gap:var(--gap);
            align-items:center;
        }
        @media (max-width:880px){
            .hero{grid-template-columns:1fr; padding-bottom:6px}
            header{flex-direction:column;align-items:flex-start}
            nav{order:2}
        }
        h1{
            margin:0 0 10px 0;font-size:clamp(1.6rem,2.8vw,2.4rem);
            line-height:1.05;
        }
        p.lead{margin:0 0 18px 0;color:var(--muted);font-size:1rem;max-width:60ch}
        .actions{display:flex;gap:12px;flex-wrap:wrap}
        .card{
            background: linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.02));
            border:1px solid rgba(255,255,255,0.03);
            padding:16px;border-radius:12px;
            color:var(--muted);
        }

        .feature-grid{
            display:grid;
            grid-template-columns:repeat(3,1fr);
            gap:12px;
            margin-top:18px;
        }
        @media (max-width:760px){.feature-grid{grid-template-columns:repeat(1,1fr)}}
        .feature{
            background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
            border-radius:10px;padding:14px;border:1px solid rgba(255,255,255,0.03);
        }
        .feature h3{margin:0 0 8px 0;font-size:1rem}
        footer{margin-top:20px;color:var(--muted);font-size:0.9rem;display:flex;justify-content:space-between;gap:12px;flex-wrap:wrap}
        .avatar{
            width:100%;height:220px;border-radius:10px;display:block;background:
            linear-gradient(135deg, rgba(56,189,248,0.12), rgba(99,102,241,0.08));
            border:1px solid rgba(255,255,255,0.02);padding:14px; color:var(--muted)
        }
        .small{font-size:0.85rem;color:var(--muted)}
        /* improved focus styles */
        a:focus, button:focus{
            outline:3px solid var(--accent);
            outline-offset:2px;
            border-radius:4px;
        }
        /* skip to main content link for accessibility */
        .skip-link {
            position: absolute;
            top: -40px;
            left: 0;
            background: var(--accent);
            color: #04263b;
            padding: 8px;
            border-radius: 4px;
            text-decoration: none;
            font-weight: 600;
            z-index: 100;
        }
        .skip-link:focus {
            top: 10px;
        }
        /* improved semantic sections */
        section {
            margin-top: 32px;
            scroll-margin-top: 20px;
        }
        section h2 {
            margin-top: 0;
            position: relative;
            padding-bottom: 8px;
        }
        section h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 2px;
            background: var(--accent);
            border-radius: 2px;
        }
        /* improved bio section */
        .bio-content {
            line-height: 1.6;
            margin-bottom: 24px;
        }
        .bio-content p {
            margin-bottom: 16px;
        }
        /* improved project cards */
        .project-card {
            transition: transform 0.2s ease, box-shadow 0.2s ease;
            cursor: pointer;
        }
        .project-card:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(2,6,23,0.8);
        }
        /* improved contact form */
        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 16px;
            margin-top: 16px;
        }
        .form-group {
            display: flex;
            flex-direction: column;
            gap: 6px;
        }
        .form-group label {
            font-size: 0.9rem;
            color: var(--muted);
        }
        .form-group input,
        .form-group textarea {
            padding: 10px;
            border-radius: 8px;
            background: rgba(255,255,255,0.03);
            border: 1px solid rgba(255,255,255,0.08);
            color: #e6eef6;
            font-family: inherit;
            font-size: 0.95rem;
        }
        .form-group input:focus,
        .form-group textarea:focus {
            outline: 2px solid var(--accent);
            border-color: transparent;
        }
        .form-group textarea {
            min-height: 120px;
            resize: vertical;
        }
        .submit-btn {
            align-self: flex-start;
            background: var(--accent);
            color: #04263b;
            border: none;
            padding: 10px 20px;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: opacity 0.2s ease;
        }
        .submit-btn:hover {
            opacity: 0.9;
        }
    </style>
</head>
<body>
    <!-- Skip to main content for accessibility -->
    <a href="#main-content" class="skip-link">Skip to main content</a>

    <div class="container" role="main" id="main-content">
        <header>
            <a class="brand" href="#" aria-label="Homepage - Moh">
                <span class="logo" aria-hidden="true">M</span>
                <div>
                    <strong>Moh</strong>
                    <div class="small">Web Designer & Developer</div>
                </div>
            </a>

            <nav aria-label="Primary navigation">
                <a class="nav-link" href="#about">About</a>
                <a class="nav-link" href="#projects">Projects</a>
                <a class="nav-link" href="#skills">Skills</a>
                <a class="nav-link" href="#contact">Contact</a>
                <a class="cta" href="#contact" aria-label="Get in touch with Moh">Get in touch</a>
            </nav>
        </header>

        <main>
            <section class="hero" aria-labelledby="welcome-heading">
                <div>
                    <h1 id="welcome-heading">Hello — I'm Moh. I design and build accessible web experiences.</h1>
                    <p class="lead">I'm a passionate web developer with 5+ years of experience creating responsive, user-friendly websites and applications. I specialize in front-end technologies and accessibility-focused design.</p>

                    <div class="actions" role="group" aria-label="Primary actions">
                        <a class="cta" href="#projects">View my work</a>
                        <a class="nav-link" href="#about">Learn more about me</a>
                        <a class="nav-link" href="#contact" aria-label="Contact Moh directly">Contact me</a>
                    </div>

                    <div class="feature-grid">
                        <div class="feature">
                            <h3>Accessibility First</h3>
                            <p class="small">All my projects follow WCAG guidelines with semantic HTML, ARIA labels, and keyboard navigation support.</p>
                        </div>
                        <div class="feature">
                            <h3>Performance Optimized</h3>
                            <p class="small">Lightweight, fast-loading websites with optimized assets and efficient code practices.</p>
                        </div>
                        <div class="feature">
                            <h3>Responsive Design</h3>
                            <p class="small">Fluid layouts that work beautifully on all devices from mobile to desktop screens.</p>
                        </div>
                    </div>
                </div>

                <aside class="card" aria-labelledby="profile-title">
                    <h2 id="profile-title" style="margin-top:0">Quick Info</h2>
                    <div class="avatar" role="img" aria-label="Abstract representation of Moh's profile">
                        <div style="display:flex;flex-direction:column;gap:6px">
                            <strong>Mohammed "Moh" Ahmed</strong>
                            <span class="small">Front-end Developer & UI/UX Designer</span>
                            <p class="small" style="margin-top:12px">Email: <a href="mailto:mamzy120@gmail.com" style="color:var(--accent)">mamzy120@gmail.com</a></p>
                            <p class="small">Location:Nigeria,Abuja,Nasarawa,Kaduna</p>
                            <p class="small">Availability: Open to new opportunities</p>
                            
                        </div>
                    </div>

                    <p class="small" style="margin:12px 0 0 0">
                        Connect: 
                        <a class="nav-link" href="https://github.com/Doma2112/my-project.git" style="padding:4px 6px" target="_blank" rel="noopener noreferrer" aria-label="Moh's GitHub profile">GitHub</a> 
                        <a class="nav-link" href="https://linkedin.com/in/moh" style="padding:4px 6px" target="_blank" rel="noopener noreferrer" aria-label="Moh's LinkedIn profile">LinkedIn</a>
                        <a class="nav-link" href="https://twitter.com/moh" style="padding:4px 6px" target="_blank" rel="noopener noreferrer" aria-label="Moh's Twitter profile">Twitter</a>
                    </p>
                </aside>
            </section>

            <section id="about" aria-labelledby="about-heading">
                <h2 id="about-heading">About Me</h2>
                <div class="bio-content">
                    <p>I'm a dedicated web professional with a passion for creating digital experiences that are not only visually appealing but also accessible to everyone. My journey in web development began over five years ago, and since then I've worked with various startups and established companies to bring their digital visions to life.</p>
                    
                    <p>My philosophy centers around the belief that good design is inclusive design. I prioritize accessibility in all my projects, ensuring that people with disabilities can navigate and interact with websites effectively. I stay updated with the latest web standards and best practices, particularly in the areas of responsive design, performance optimization, and progressive enhancement.</p>
                    
                    <p>When I'm not coding, you can find me contributing to open-source projects, writing technical articles about web accessibility, or exploring new frameworks and tools. I'm also an advocate for sustainable web design practices that reduce digital carbon footprints.</p>
                    
                    <p>I'm currently expanding my skills in full-stack development while continuing to advocate for more accessible and inclusive web experiences across the industry.</p>
                </div>
            </section>

            <section id="skills" aria-labelledby="skills-heading">
                <h2 id="skills-heading">Technical Skills</h2>
                <div class="card">
                    <div style="display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 16px;">
                        <div>
                            <h3 style="margin-top: 0; font-size: 1rem;">Front-end</h3>
                            <ul class="small" style="margin: 0; padding-left: 20px;">
                                <li>HTML5 & Semantic Markup</li>
                                <li>CSS3 & Sass/SCSS</li>
                                <li>JavaScript (ES6+)</li>
                                <li>React.js</li>
                                <li>Vue.js</li>
                                <li>TypeScript</li>
                            </ul>
                        </div>
                        <div>
                            <h3 style="margin-top: 0; font-size: 1rem;">Tools & Practices</h3>
                            <ul class="small" style="margin: 0; padding-left: 20px;">
                                <li>Git & GitHub</li>
                                <li>Webpack & Vite</li>
                                <li>Responsive Design</li>
                                <li>Accessibility Testing</li>
                                <li>Performance Optimization</li>
                                <li>Cross-browser Testing</li>
                            </ul>
                        </div>
                        <div>
                            <h3 style="margin-top: 0; font-size: 1rem;">Design</h3>
                            <ul class="small" style="margin: 0; padding-left: 20px;">
                                <li>UI/UX Principles</li>
                                <li>Figma & Adobe XD</li>
                                <li>Design Systems</li>
                                <li>WCAG 2.1 Compliance</li>
                                <li>Prototyping</li>
                                <li>User Testing</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </section>

            <section id="projects" aria-labelledby="projects-heading">
                <h2 id="projects-heading">Featured Projects</h2>
                <div class="card project-card" style="margin-bottom: 16px;">
                    <article>
                        <div style="display:flex;gap:12px;align-items:flex-start;flex-wrap:wrap">
                            <div style="flex:1;min-width:200px">
                                <h3 style="margin:0">Accessible E-commerce Platform</h3>
                                <p class="small" style="margin:6px 0 0 0">A fully accessible online shopping platform with screen reader support, keyboard navigation, and high contrast modes. Built with React, TypeScript, and ARIA labels.</p>
                                <div style="margin-top: 8px;">
                                    <span class="small" style="background: rgba(56,189,248,0.1); padding: 2px 8px; border-radius: 10px; margin-right: 6px;">React</span>
                                    <span class="small" style="background: rgba(56,189,248,0.1); padding: 2px 8px; border-radius: 10px; margin-right: 6px;">TypeScript</span>
                                    <span class="small" style="background: rgba(56,189,248,0.1); padding: 2px 8px; border-radius: 10px;">Accessibility</span>
                                </div>
                            </div>
                            <div style="min-width:160px;text-align:right">
                                <a class="nav-link" href="#" style="display:inline-block">View Project →</a>
                            </div>
                        </div>
                    </article>
                </div>
                
                <div class="card project-card" style="margin-bottom: 16px;">
                    <article>
                        <div style="display:flex;gap:12px;align-items:flex-start;flex-wrap:wrap">
                            <div style="flex:1;min-width:200px">
                                <h3 style="margin:0">Educational Resource Portal</h3>
                                <p class="small" style="margin:6px 0 0 0">A responsive learning platform with interactive modules and quizzes. Focused on performance with lazy loading, image optimization, and service workers for offline access.</p>
                                <div style="margin-top: 8px;">
                                    <span class="small" style="background: rgba(56,189,248,0.1); padding: 2px 8px; border-radius: 10px; margin-right: 6px;">Vue.js</span>
                                    <span class="small" style="background: rgba(56,189,248,0.1); padding: 2px 8px; border-radius: 10px; margin-right: 6px;">PWA</span>
                                    <span class="small" style="background: rgba(56,189,248,0.1); padding: 2px 8px; border-radius: 10px;">Performance</span>
                                </div>
                            </div>
                            <div style="min-width:160px;text-align:right">
                                <a class="nav-link" href="#" style="display:inline-block">View Project →</a>
                            </div>
                        </div>
                    </article>
                </div>
                
                <div class="card project-card">
                    <article>
                        <div style="display:flex;gap:12px;align-items:flex-start;flex-wrap:wrap">
                            <div style="flex:1;min-width:200px">
                                <h3 style="margin:0">Nonprofit Organization Website</h3>
                                <p class="small" style="margin:6px 0 0 0">A complete website redesign for a local nonprofit, improving accessibility scores by 40% and mobile performance by 60%. Implemented multilingual support and donation portal.</p>
                                <div style="margin-top: 8px;">
                                    <span class="small" style="background: rgba(56,189,248,0.1); padding: 2px 8px; border-radius: 10px; margin-right: 6px;">HTML/CSS</span>
                                    <span class="small" style="background: rgba(56,189,248,0.1); padding: 2px 8px; border-radius: 10px; margin-right: 6px;">JavaScript</span>
                                    <span class="small" style="background: rgba(56,189,248,0.1); padding: 2px 8px; border-radius: 10px;">Multilingual</span>
                                </div>
                            </div>
                            <div style="min-width:160px;text-align:right">
                                <a class="nav-link" href="#" style="display:inline-block">View Project →</a>
                            </div>
                        </div>
                    </article>
                </div>
            </section>

            <section id="contact" aria-labelledby="contact-heading">
                <h2 id="contact-heading">Get In Touch</h2>
                <div class="card">
                    <p>I'm always interested in hearing about new opportunities, whether it's a potential project, collaboration, or just to chat about web accessibility and development.</p>
                    
                    <div class="contact-form">
                        <div class="form-group">
                            <label for="name">Your Name</label>
                            <input type="text" id="name" name="name" required aria-required="true">
                        </div>
                        
                        <div class="form-group">
                            <label for="email">Your Email</label>
                            <input type="email" id="email" name="email" required aria-required="true">
                        </div>
                        
                        <div class="form-group">
                            <label for="message">Your Message</label>
                            <textarea id="message" name="message" required aria-required="true"></textarea>
                        </div>
                        
                        <button type="submit" class="submit-btn">Send Message</button>
                    </div>
                    
                    <p class="small" style="margin-top: 20px;">
                        You can also reach me directly at <a href="mailto:moh@example.com" style="color:var(--accent)">mamzy120@gmail.com</a> or connect with me on social media.
                    </p>
                    <p class="small"> contact Phone number <span>08024694958,09036391954</span></p>
                </div>
            </section>

            <footer aria-labelledby="footer-heading">
                <div id="footer-heading">© <time datetime="2025">2025</time> Moh — Built with semantic HTML & accessible CSS</div>
                <div class="small">
                    <a href="#main-content" class="nav-link" style="padding: 4px 8px;">Back to top ↑</a>
                </div>
            </footer>
        </main>
    </div>

    <script>
        // Enhanced JavaScript for better accessibility and user experience
        (function(){ 
            'use strict';
            
            // Smooth scrolling for anchor links
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    const href = this.getAttribute('href');
                    
                    // Don't prevent default for # links that should scroll
                    if (href !== '#') {
                        e.preventDefault();
                        
                        const targetId = href.substring(1);
                        const targetElement = document.getElementById(targetId);
                        
                        if (targetElement) {
                            // Update URL without page jump
                            history.pushState(null, null, href);
                            
                            // Smooth scroll to target
                            targetElement.scrollIntoView({
                                behavior: 'smooth',
                                block: 'start'
                            });
                            
                            // Focus the target for keyboard users
                            targetElement.setAttribute('tabindex', '-1');
                            targetElement.focus();
                            setTimeout(() => {
                                targetElement.removeAttribute('tabindex');
                            }, 1000);
                        }
                    }
                });
            });
            
            // Simple form handling
            const contactForm = document.querySelector('.contact-form');
            if (contactForm) {
                const submitBtn = contactForm.querySelector('.submit-btn');
                
                submitBtn.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    const name = document.getElementById('name').value.trim();
                    const email = document.getElementById('email').value.trim();
                    const message = document.getElementById('message').value.trim();
                    
                    // Basic validation
                    if (!name || !email || !message) {
                        alert('Please fill in all fields before sending.');
                        return;
                    }
                    
                    if (!/^\S+@\S+\.\S+$/.test(email)) {
                        alert('Please enter a valid email address.');
                        return;
                    }
                    
                    // In a real implementation, this would be an AJAX request
                    alert(`Thank you, ${name}! Your message has been sent. I'll get back to you soon.`);
                    
                    // Reset form
                    document.getElementById('name').value = '';
                    document.getElementById('email').value = '';
                    document.getElementById('message').value = '';
                    
                    // Focus back to name field for screen readers
                    document.getElementById('name').focus();
                });
            }
            
            // Keyboard shortcuts for accessibility
            window.addEventListener('keydown', function(e) {
                // 'P' key to jump to projects section
                if (e.key === 'p' && !e.altKey && !e.ctrlKey && !e.metaKey) {
                    const projectsSection = document.getElementById('projects');
                    if (projectsSection) {
                        projectsSection.scrollIntoView({behavior: 'smooth', block: 'start'});
                        projectsSection.setAttribute('tabindex', '-1');
                        projectsSection.focus();
                    }
                }
                
                // 'C' key to jump to contact section
                if (e.key === 'c' && !e.altKey && !e.ctrlKey && !e.metaKey) {
                    const contactSection = document.getElementById('contact');
                    if (contactSection) {
                        contactSection.scrollIntoView({behavior: 'smooth', block: 'start'});
                        contactSection.setAttribute('tabindex', '-1');
                        contactSection.focus();
                    }
                }
                
                // '1' key to jump to top
                if (e.key === '1' && !e.altKey && !e.ctrlKey && !e.metaKey) {
                    const mainContent = document.getElementById('main-content');
                    if (mainContent) {
                        mainContent.scrollIntoView({behavior: 'smooth', block: 'start'});
                        mainContent.setAttribute('tabindex', '-1');
                        mainContent.focus();
                    }
                }
            });
            
            // Add focus styles for keyboard navigation
            document.addEventListener('keydown', function(e) {
                if (e.key === 'Tab') {
                    document.body.classList.add('keyboard-navigation');
                }
            });
            
            document.addEventListener('mousedown', function() {
                document.body.classList.remove('keyboard-navigation');
            });
            
            // Add CSS for keyboard navigation indicator
            const style = document.createElement('style');
            style.textContent = `
                .keyboard-navigation a:focus,
                .keyboard-navigation button:focus,
                .keyboard-navigation input:focus,
                .keyboard-navigation textarea:focus {
                    outline: 3px solid var(--accent) !important;
                    outline-offset: 2px !important;
                }
            `;
            document.head.appendChild(style);
        }());
    </script>
</body>
</html>
