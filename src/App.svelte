<script>
	const about = {
	  name: 'Vaibhav Jadhav',
	  role: 'Frontend Developer',
	  location: 'Pune, India',
	  description:
		'Frontend Developer with around 2.8 years of experience. I specialize in building modern web applications using HTML, CSS, JavaScript, React, and Svelte. My expertise lies in creating responsive and user-friendly interfaces.',
	  interests:
		'When I’m not coding, I enjoy organizing tech workshops, contributing to open-source projects, and participating in community initiatives like water harvesting campaigns.',
	};
  
	const projects = [
	  {
		name: 'All-in-One Calculator',
		description: 'A versatile calculator app with multiple functionalities, including scientific, BMI, and unit conversion.',
		link: 'https://calc-master-nu.vercel.app/',
	  },
	  {
		name: 'Stocks App',
		description: 'An intuitive app to track and analyze stock market trends with real-time data visualization.',
		link: 'https://stock-za.vercel.app/',
	  },
	  {
		name: 'Finance App',
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
	  email: 'jadhavaibhav2704@gmail.com',
	  phone: '+91 7972985106',
	  location: 'Pune, India',
	};
  
	// Hamburger Menu Logic
	document.addEventListener('DOMContentLoaded', () => {
	  const menuToggle = document.getElementById('menu-toggle');
	  const navLinks = document.getElementById('nav-links');
  
	  if (menuToggle && navLinks) {
		menuToggle.addEventListener('click', () => {
		  navLinks.classList.toggle('active');
		});
	  } else {
		console.error('Required elements (menu-toggle or nav-links) are missing from the DOM.');
	  }
	});
  </script>
  
  <main class="portfolio">
	<!-- Navbar -->
	<nav class="navbar">
	  <div class="logo">Vaibhav</div>
	  <button id="menu-toggle" class="menu-toggle">&#9776;</button>
	  <ul class="nav-links" id="nav-links">
		<li><a href="#about">About</a></li>
		<li><a href="#projects">Projects</a></li>
		<li><a href="#technologies">Technologies</a></li>
		<li><a href="#contact">Contact</a></li>
	  </ul>
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
	  justify-content: space-between;
	  align-items: center;
	  padding: 1rem;
	  background: rgba(0, 0, 0, 0.8);
	  position: sticky;
	  top: 0;
	  z-index: 1000;
	}
  
	.logo {
	  font-size: 1.25rem;
	  font-weight: bold;
	  color: #00bcd4;
	}
  
	.menu-toggle {
	  display: none;
	  font-size: 1.5rem;
	  background: none;
	  border: none;
	  color: white;
	  cursor: pointer;
	}
  
	.nav-links {
	  display: flex;
	  gap: 1.5rem;
	  list-style: none;
	  transition: max-height 0.3s ease, opacity 0.3s ease;
	  max-height: 500px; /* Adjust as needed */
	  overflow: hidden;
	}
  
	.nav-links a {
	  color: white;
	  font-size: 1rem;
	  text-decoration: none;
	  transition: color 0.3s ease, transform 0.3s ease;
	}
  
	.nav-links a:hover {
	  color: #00bcd4;
	  transform: scale(1.1);
	}
  
	@media (max-width: 768px) {
	  .menu-toggle {
		display: block;
	  }
  
	  .nav-links {
		flex-direction: column;
		gap: 0.75rem;
		max-height: 0;
		opacity: 0;
		pointer-events: none; /* Disable interaction when collapsed */
	  }
  
	  .nav-links.active {
		max-height: 500px; /* Expand to show links */
		opacity: 1;
		pointer-events: auto; /* Enable interaction when expanded */
	  }
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
	}
  
	/* Technologies */
	.technologies-container {
	  display: grid;
	  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
	  gap: 1rem;
	  justify-content: center;
	}
  
	.tech-card {
	  display: flex;
	  flex-direction: column;
	  align-items: center;
	  background: rgba(255, 255, 255, 0.08);
	  padding: 1rem;
	  border-radius: 10px;
	  transition: transform 0.3s ease;
	}
  
	.tech-card:hover {
	  transform: scale(1.05);
	}
  
	.tech-image {
	  width: 40px;
	  height: 40px;
	  object-fit: contain;
	  margin-bottom: 0.5rem;
	  max-width: 100%;
	}
  
	.tech-name {
	  font-size: 0.85rem;
	  color: #ffffff;
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
		gap: 1rem;
	  }
  
	  .tech-card {
		width: 90px;
	  }
  
	  .tech-image {
		width: 38px;
		height: 38px;
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
		gap: 0.75rem;
	  }
  
	  .tech-card {
		width: 80px;
	  }
  
	  .tech-image {
		width: 35px;
		height: 35px;
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