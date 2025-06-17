<script>
    const about = {
        name: 'Vaibhav Jadhav',
        role: 'Frontend Developer',
        location: 'Pune, India',
        description:
            'Frontend Developer with around 3+ years of experience. I specialize in building modern web applications using HTML, CSS, JavaScript, Svelte, and React. My expertise lies in creating responsive and user-friendly interfaces.',
			interests:
    'When I’m not coding, I enjoy reading fiction novels, exploring nature on hiking trips, and experimenting with photography. In my free time, I also love watching tech videos and learning about the latest developments in web technologies and design trends.',
    };

    const projects = [
        {
            name: 'CalcMaster',
            description: 'A versatile calculator app with multiple functionalities, including scientific, Loan, and currency conversion.',
            link: 'https://calc-master-nu.vercel.app/',
        },
        {
            name: 'StockZa',
            description: 'An intuitive app to track and analyze stock market trends with real-time data visualization.',
            link: 'https://stock-za.vercel.app/',
        },
        {
            name: 'Fin Dash',
            description: 'A personal finance management tool to track expenses, budgets, and savings goals.',
            link: 'https://finance-coral-ten.vercel.app/',
        },
    ];

    const technologies = [
        { name: 'Svelte', image: 'https://upload.wikimedia.org/wikipedia/commons/1/1b/Svelte_Logo.svg' },
        { name: 'JavaScript', image: 'https://upload.wikimedia.org/wikipedia/commons/6/6a/JavaScript-logo.png' },
        { name: 'HTML', image: 'https://upload.wikimedia.org/wikipedia/commons/6/61/HTML5_logo_and_wordmark.svg' },
        { name: 'CSS', image: 'https://upload.wikimedia.org/wikipedia/commons/d/d5/CSS3_logo_and_wordmark.svg' },
        { name: 'React', image: 'https://upload.wikimedia.org/wikipedia/commons/a/a7/React-icon.svg' },
        { name: 'Node.js', image: 'https://upload.wikimedia.org/wikipedia/commons/d/d9/Node.js_logo.svg' },
    ];

    const contact = {
        email: 'vhjadhav9313@gmail.com',
        phone: '+91 7972985106',
        location: 'Trivandrum, India',
    };
</script>

<main class="portfolio">
    <!-- Navbar -->
    <nav class="navbar">
        <div class="logo">Vaibhav</div>
    </nav>

    <!-- About -->
    <section id="about" class="section">
        <h2 class="section-title">About Me</h2>
        <div class="about-content">
            <p>{about.description}</p>
            <p>{about.interests}</p>
        </div>
    </section>

    <!-- Projects -->
    <section id="projects" class="section">
        <h2 class="section-title">My Projects</h2>
        <div class="projects-container">
            {#each projects as project}
                <div class="project-card">
                    <h3 class="project-name">{project.name}</h3>
                    <p class="project-description">{project.description}</p>
                    <a href={project.link} target="_blank" rel="noopener noreferrer" class="project-link">View Project</a>
                </div>
            {/each}
        </div>
    </section>

    <!-- Technologies -->
    <section id="technologies" class="section">
        <h2 class="section-title">Technologies</h2>
        <div class="technologies-container">
            {#each technologies as tech}
                <div class="tech-card">
                    <img src={tech.image} alt={tech.name} class="tech-image" />
                    <p class="tech-name">{tech.name}</p>
                </div>
            {/each}
        </div>
    </section>

    <!-- Contact -->
    <footer id="contact" class="section">
        <h2 class="section-title">Contact Me</h2>
        <div class="contact-info">
            <p>Email: {contact.email}</p>
            <p>Phone: {contact.phone}</p>
            <p>Location: {contact.location}</p>
        </div>
    </footer>
</main>

<style>
    /* General Styles */
    body {
        margin: 0;
        font-family: Arial, sans-serif;
        background: #121212;
        color: #ffffff;
    }

    .navbar {
        display: flex;
        align-items: center;
        padding: 1rem 1.5rem;
        background: rgba(0, 0, 0, 0.8);
        position: sticky;
        top: 0;
        z-index: 1000;
        border-bottom: 1px solid #2e2e2e;
    }

    .logo {
        font-size: 1.25rem;
        font-weight: bold;
        color: #00bcd4;
    }

    .section {
        padding: 2rem 1rem;
        text-align: center;
        animation: fadeIn 1.2s ease-in-out;
    }

    .section-title {
        font-size: 1.5rem;
        font-weight: bold;
        margin-bottom: 1.5rem;
        color: #00bcd4;
    }

    .about-content {
        max-width: 700px;
        margin: 0 auto;
        font-size: 1rem;
    }

    /* Projects */
    .projects-container {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        gap: 1rem;
    }

    .project-card {
        background: rgba(255, 255, 255, 0.08);
        padding: 1rem;
        border-radius: 12px;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.4);
        transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .project-card:hover {
        transform: translateY(-5px);
        box-shadow: 0 6px 12px rgba(0, 0, 0, 0.6);
    }

    .project-name {
        font-size: 1.1rem;
        color: #bb86fc;
        margin-bottom: 0.5rem;
    }

    .project-description {
        font-size: 0.95rem;
        color: #dcdcdc;
        margin-bottom: 0.75rem;
    }

    .project-link {
        font-size: 0.9rem;
        color: #00bcd4;
        font-weight: bold;
        text-decoration: none;
    }

    .project-link:hover {
        text-decoration: underline;
    }

    /* Technologies - Improved Grid */
    .technologies-container {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
        gap: 1.5rem;
        padding: 1rem;
        justify-content: center;
        align-items: stretch;
    }

    .tech-card {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        text-align: center;
        background: rgba(255, 255, 255, 0.08);
        padding: 1rem;
        border-radius: 10px;
        transition: transform 0.3s ease, box-shadow 0.3s ease;
        min-height: 120px;
        box-shadow: 0 2px 6px rgba(0, 0, 0, 0.3);
    }

    .tech-card:hover {
        transform: translateY(-4px);
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.4);
    }

    .tech-image {
        width: 50px;
        height: 50px;
        object-fit: contain;
        margin-bottom: 0.75rem;
    }

    .tech-name {
        font-size: 0.95rem;
        color: #ffffff;
        font-weight: 500;
    }

    /* Contact */
    .contact-info p {
        margin: 0.5rem 0;
        font-size: 0.95rem;
    }

    /* Media Queries */
    @media (max-width: 768px) {
        .logo {
            font-size: 1.1rem;
        }

        .section-title {
            font-size: 1.35rem;
        }

        .about-content {
            font-size: 0.95rem;
        }

        .projects-container {
            gap: 1rem;
        }

        .project-card {
            padding: 0.75rem;
        }

        .project-name {
            font-size: 1.05rem;
        }

        .project-description {
            font-size: 0.9rem;
        }

        .technologies-container {
            grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            gap: 1rem;
            padding: 0.5rem;
        }

        .tech-card {
            min-height: 100px;
            padding: 1rem;
        }

        .tech-image {
            width: 40px;
            height: 40px;
        }

        .tech-name {
            font-size: 0.85rem;
        }

        .contact-info p {
            font-size: 0.9rem;
        }
    }

    @media (max-width: 480px) {
        .logo {
            font-size: 1rem;
        }

        .section-title {
            font-size: 1rem;
        }

        .about-content {
            font-size: 0.9rem;
        }

        .projects-container {
            gap: 0.75rem;
        }

        .project-card {
            padding: 0.5rem;
        }

        .project-name {
            font-size: 1rem;
        }

        .project-description {
            font-size: 0.85rem;
        }

        .technologies-container {
            grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
            gap: 0.75rem;
        }

        .tech-card {
            min-height: 90px;
            padding: 0.75rem;
        }

        .tech-image {
            width: 35px;
            height: 35px;
        }

        .tech-name {
            font-size: 0.8rem;
        }

        .contact-info p {
            font-size: 0.85rem;
        }
    }

    /* Fade-In Animation */
    @keyframes fadeIn {
        from {
            opacity: 0;
            transform: translateY(20px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }
</style>
