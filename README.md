<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio| Front-End Developer</title>
    <style>
        :root {
            --bg-color: #ffffff;
            --text-color: #333333;
            --primary-color: #1021b6;
            --section-bg: rgba(233, 233, 233, 0.85);
            --card-bg: #f8f9fa;
            --footer-bg: #f0f4ff;
        }

        .dark-mode {
            --bg-color: #121212;
            --text-color: #f0f0f0;
            --primary-color: #4a6bff;
            --section-bg: rgba(30, 30, 30, 0.85);
            --card-bg: #1e1e1e;
            --footer-bg: #0a0a1a;
        }

        /* Global Styles */
        body {
            margin: 0;
            min-height: 100vh;
            background: var(--bg-color);
            color: var(--text-color);
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            transition: background 0.5s ease, color 0.5s ease;
        }

        /* Animated Gradient Background (only for light mode) */
        body:not(.dark-mode) {
            background: linear-gradient(-45deg, #1021b6, #23a6d5, #9b59b6, #e74c3c);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Navigation */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background-color: var(--section-bg);
            backdrop-filter: blur(8px);
            z-index: 1000;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        .nav-links {
            display: flex;
            gap: 1.5rem;
        }

        .nav-links a {
            color: var(--text-color);
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: var(--primary-color);
        }

        .menu-toggle {
            display: none;
            background: none;
            border: none;
            color: var(--text-color);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Theme Toggle */
        .theme-toggle {
            background: none;
            border: none;
            color: var(--text-color);
            font-size: 1.2rem;
            cursor: pointer;
            padding: 0.5rem;
            border-radius: 50%;
            transition: transform 0.3s;
        }

        .theme-toggle:hover {
            transform: rotate(30deg);
        }

        /* Sections */
        section {
            background-color: var(--section-bg);
            backdrop-filter: blur(8px);
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            margin: 5rem auto;
            padding: 2rem;
            max-width: 800px;
            transition: all 0.5s ease;
        }

        h1, h2, h3 {
            color: var(--primary-color);
        }

        /* Home Section */
        #home {
            text-align: center;
            padding-top: 8rem;
        }

        #home h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        #home p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
        }

        button {
            background: var(--primary-color);
            color: rgb(231, 231, 231);
            padding: 0.8rem 1.5rem;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            transition: background 0.3s, transform 0.3s;
        }

        button:hover {
            background: #0a1a8c;
            transform: translateY(-2px);
        }

        /* About Section */
        #about ul {
            list-style-type: none;
            padding: 0;
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 1rem;
        }

        #about li {
            background: var(--card-bg);
            padding: 0.8rem;
            border-radius: 5px;
            transition: transform 0.3s;
        }

        #about li:hover {
            transform: translateY(-5px);
        }

        /* Projects Section */
        .projects-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .project-card {
            background: var(--card-bg);
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .project-card h3 {
            margin-top: 0;
        }

        .project-card a {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: bold;
            display: inline-block;
            margin-top: 1rem;
        }

        /* Contact Section */
        #contact-form {
            display: flex;
            flex-direction: column;
            gap: 1rem;
            margin-top: 2rem;
        }

        #contact-form input,
        #contact-form textarea {
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            background: var(--bg-color);
            color: var(--text-color);
        }

        #contact-form textarea {
            min-height: 150px;
            resize: vertical;
        }

        .social-links {
            margin-top: 2rem;
            display: flex;
            gap: 1.5rem;
        }

        .social-links a {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s;
        }

        .social-links a:hover {
            color: #0a1a8c;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 2rem;
            background: var(--footer-bg);
            margin-top: 3rem;
            transition: all 0.5s ease;
        }

        /* Fun Fact */
        .fun-fact {
            max-width: 800px;
            margin: 2rem auto;
            padding: 0 1rem;
            font-style: italic;
            text-align: center;
        }

        /* Image */
        .profile-img {
            display: block;
            margin: 2rem auto;
            border-radius: 50%;
            width: 150px;
            height: 150px;
            object-fit: cover;
            border: 3px solid var(--primary-color);
            transition: all 0.5s ease;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                position: fixed;
                top: 70px;
                left: 0;
                width: 100%;
                background-color: var(--section-bg);
                backdrop-filter: blur(8px);
                flex-direction: column;
                align-items: center;
                padding: 1rem 0;
                gap: 1rem;
                transform: translateY(-150%);
                transition: transform 0.3s ease;
            }

            .nav-links.active {
                transform: translateY(0);
            }

            .menu-toggle {
                display: block;
            }

            section {
                margin: 5rem 1rem;
                padding: 1.5rem;
            }

            #home {
                padding-top: 6rem;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <header>
        <h2>My Portfolio
        </h2>
        <nav>
            <button class="menu-toggle">☰</button>
            <div class="nav-links">
                <a href="#home">Home</a>
                <a href="#about">About</a>
                <a href="#projects">Projects</a>
                <a href="#contact">Contact</a>
                <button class="theme-toggle" id="themeToggle">🌓</button>
            </div>
        </nav>
    </header>

    <!-- Home Section -->
    <section id="home">
<!-- Profile Image -->
    <img src="your-image.jpg" alt="Supersabe at work" class="profile-img">
        <h1>Hi, I'm <span style="color: var(--primary-color);">Abdullah Saberedowo
        </span></h1>
        <p>Aspiring Front-End Developer | TECH/PYTHON/HTML/CSS/JavaScript Enthusiast</p>
        <button onclick="location.href='#projects'">See My Projects</button>
    </section>

    <!-- About Section -->
    <section id="about">
        <h2>About Me</h2>
        <p>
            I'm a passionate self-taught developer currently mastering front-end web designing. 
            I love turning ideas into interactive, user-friendly websites. 
            When I'm not coding, I enjoy making designs, video editing and animation.
            AI is my playground.
        </p>
        <h3>My Skills</h3>
        <ul>
            <li>HTML5 & CSS3</li>
            <li>JavaScript</li>
            <li>Git & GitHub</li>
            <li>Responsive Design</li>
            <li>Graphics Design</li>
            <li>Video Editing and Animation</li>
        </ul>
    </section>

    <!-- Projects Section -->
<section id="projects">
    <h2>My Projects</h2>
    <div class="projects-container">
        <div class="project-card">
            <h3>Portfolio Website</h3>
            <p>Built with pure HTML/CSS/JS. Responsive and interactive.</p>
            <a href="https://github.com/YOUR_USERNAME/YOUR_REPO/blob/main/index.html" target="_blank">View Code</a>
        </div>
    </div>
            <div class="project-card">
                <h3>Coming Soon: Daytracker</h3>
                <p>Tracking your day to keep up with your plans (Learning now!).</p>
                <a href="#">Preview</a>
            </div>
            <div class="project-card">
                <h3>JavaScript Calculator</h3>
                <p>A simple calculator built with vanilla JavaScript.</p>
                <a href="#">View Project</a>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
<section id="contact">
    <h2>Get In Touch</h2>
    <form id="contact-form" action="https://script.google.com/macros/s/AKfycbyF9mV3jJLzShTkqfSGYw8PVvSpG1zuH9-uMQKuA6nfoObZE4VmIAYJc2V7t5tVejVPPQ/exec" method="POST">
        <input type="text" name="name" placeholder="Your Full Name" required>
        <input type="email" name="email" placeholder="Your Email" required>
        <textarea name="message" placeholder="Your Message" required></textarea>
        <button type="submit">Send</button>
    </form>

    <!-- Social Media Referral Links -->
    <div class="social-referrals">
        <a href="https://linkedin.com/in/abdullah-saberedowo-676461355?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3BpSlMVDnNRU2Zjo%2FRHIy2gA%3D%3D" target="_blank" class="social-link">
            <img src="https://cdn-icons-png.flaticon.com/512/174/174857.png" alt="LinkedIn" width="20" height="20">
            <span>LinkedIn</span>
        </a>
        <a href="https://github.com/YOUR_GITHUB_USERNAME" target="_blank" class="social-link">
            <img src="https://cdn-icons-png.flaticon.com/512/25/25231.png" alt="GitHub" width="20" height="20">
            <span>GitHub</span>
        </a>
    </div>
</section>

<style>
    .social-referrals {
        display: flex;
        gap: 20px;
        margin-top: 30px;
        justify-content: center;
    }
    
    .social-link {
        display: flex;
        align-items: center;
        gap: 8px;
        text-decoration: none;
        color: var(--primary-color);
        font-weight: bold;
        padding: 8px 12px;
        border-radius: 5px;
        transition: all 0.3s ease;
    }
    
    .social-link:hover {
        background-color: rgba(16, 33, 182, 0.1);
        transform: translateY(-2px);
    }
    
    .social-link img {
        transition: transform 0.3s ease;
    }
    
    .social-link:hover img {
        transform: scale(1.1);
    }
</style>
        

    <!-- Fun Fact -->
    <p class="fun-fact">
        Fun fact: I started learning to code when I realized that I don't have to spend 3 hours manually renaming 100+ files. I knew there had to be a faster way!
    </p>


    <!-- Footer -->
    <footer>
        <p>© 2025 Supersabe. Built with ♥ and vanilla code.</p>
    </footer>

    <!-- JavaScript -->
    <script>
        // Dark/Light Mode Toggle
        const themeToggle = document.getElementById('themeToggle');
        themeToggle.addEventListener('click', () => {
            document.body.classList.toggle('dark-mode');
            localStorage.setItem('darkMode', document.body.classList.contains('dark-mode'));
            updateThemeIcon();
        });

        function updateThemeIcon() {
            themeToggle.textContent = document.body.classList.contains('dark-mode') ? '☀️' : '🌓';
        }

        // Check for saved theme preference
        if (localStorage.getItem('darkMode') === 'true') {
            document.body.classList.add('dark-mode');
        }
        updateThemeIcon();

        // Mobile Navigation
        const menuToggle = document.querySelector('.menu-toggle');
        const navLinks = document.querySelector('.nav-links');

        menuToggle.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });

        // Close mobile menu when clicking a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
            });
        });

        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Form Submission
        document.getElementById('contact-form').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const form = e.target;
            const submitButton = form.querySelector('button[type="submit"]');
            const messageDiv = document.getElementById('form-message');
            
            try {
                // Disable button during submission
                submitButton.disabled = true;
                messageDiv.textContent = "Sending...";
                messageDiv.style.color = "var(--primary-color)";
                
                const formData = new FormData(form);
                const response = await fetch(form.action, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(Object.fromEntries(formData.entries()))
                });
                
                if (!response.ok) throw new Error('Network error');
                
                // Success
                form.reset();
                messageDiv.textContent = "✅ Message sent successfully!";
                messageDiv.style.color = "green";
            } catch (error) {
                // Error
                messageDiv.textContent = "❌ Error sending message. Please try again.";
                messageDiv.style.color = "red";
                console.error('Form submission error:', error);
            } finally {
                submitButton.disabled = false;
            }
        });

        // Project Gallery Animation
        const projectCards = document.querySelectorAll('.project-card');
        projectCards.forEach((card, index) => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(20px)';
            card.style.transition = `all 0.5s ease ${index * 0.1}s`;
            
            // Trigger animation when card is in viewport
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, { threshold: 0.1 });
            
            observer.observe(card);
        });
    </script>
</body>
</html>
