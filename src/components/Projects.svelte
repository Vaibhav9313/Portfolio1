<script>
  // Define your projects based on the information from your resume and provided links
  const projects = [
    {
      name: 'All-in-One Calculator',
      description:
        'A versatile calculator app with multiple functionalities, including scientific, BMI, and unit conversion.',
      link: 'https://calc-master-nu.vercel.app/',
    },
    {
      name: 'Stocks App',
      description:
        'An intuitive app to track and analyze stock market trends with real-time data visualization.',
      link: 'https://stock-za.vercel.app/',
    },
    {
      name: 'Finance App',
      description:
        'A personal finance management tool to track expenses, budgets, and savings goals.',
      link: 'https://finance-coral-ten.vercel.app/',
    },
  ];
</script>

<section id="projects">
  <div class="section-container">
    <!-- Title -->
    <h2 class="section-title">My Projects</h2>

    <!-- Project Cards -->
    <div class="projects-container">
      {#each projects as project}
        <div class="project-card">
          <div class="project-header">
            <h3 class="project-name">{project.name}</h3>
            <div class="project-decoration"></div> <!-- Decorative animation -->
          </div>
          <p class="project-description">{project.description}</p>
          <a href={project.link} target="_blank" class="project-link">View Project</a>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  /* General Section Styling */
  section {
    padding: 4rem 1rem; /* Consistent padding for all sections */
    text-align: center;
    background: linear-gradient(135deg, #1a1a1a, #2c2c2c); /* Dark gradient background */
    color: white; /* Light text color for readability */
    overflow: hidden; /* Hide overflow for animations */
  }

  /* Container for Layout */
  .section-container {
    max-width: 1200px; /* Limit width for better focus */
    margin: 0 auto; /* Center the container */
  }

  /* Title Styling */
  .section-title {
    font-size: 2rem;
    font-weight: bold;
    margin-bottom: 2rem;
    color: #00bcd4; /* Teal accent color */
    letter-spacing: 1px;
    position: relative; /* For animation */
    animation: fadeInUp 1.5s ease-in-out;
  }

  /* Projects Container */
  .projects-container {
    display: flex;
    flex-direction: column; /* Stack cards vertically on smaller screens */
    align-items: center;
    gap: 2rem; /* Space between project cards */
  }

  /* Individual Project Card */
  .project-card {
    max-width: 400px; /* Limit width for better readability */
    padding: 1.5rem;
    border-radius: 12px;
    background: rgba(255, 255, 255, 0.1); /* Semi-transparent background */
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.4); /* Subtle shadow for depth */
    transition: transform 0.3s ease, box-shadow 0.3s ease; /* Smooth hover effect */
    position: relative; /* For decoration animation */
  }

  .project-card:hover {
    transform: translateY(-5px); /* Slight upward movement on hover */
    box-shadow: 0 6px 12px rgba(0, 0, 0, 0.6); /* Enhanced shadow on hover */
  }

  /* Project Header */
  .project-header {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 1rem;
  }

  /* Project Name */
  .project-name {
    font-size: 1.25rem;
    font-weight: bold;
    margin-bottom: 0.75rem;
    color: #bb86fc; /* Vibrant color for project names */
    transition: color 0.3s ease;
  }

  .project-card:hover .project-name {
    color: #00bcd4; /* Change color on hover */
  }

  /* Project Decoration (Animation) */
  .project-decoration {
    width: 100%;
    height: 2px;
    background: #bb86fc; /* Vibrant color */
    position: relative;
    overflow: hidden;
  }

  .project-decoration::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, #00bcd4, transparent);
    animation: slideIn 2s infinite ease-in-out;
  }

  /* Project Description */
  .project-description {
    font-size: 0.95rem;
    line-height: 1.5;
    margin-bottom: 1rem;
    color: #dcdcdc; /* Light gray for descriptions */
  }

  /* Project Link */
  .project-link {
    display: inline-block;
    font-size: 0.9rem;
    font-weight: bold;
    color: #00bcd4; /* Teal accent color for links */
    text-decoration: none;
    padding: 0.5rem 1rem;
    border-radius: 6px;
    background: rgba(0, 188, 212, 0.2); /* Semi-transparent teal background */
    transition: background 0.3s ease, color 0.3s ease; /* Smooth hover effect */
  }

  .project-link:hover {
    color: white; /* White text on hover */
    background: #00bcd4; /* Solid teal background on hover */
  }

  /* Animations */
  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(30px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes slideIn {
    0% {
      left: -100%;
    }
    50% {
      left: 0;
    }
    100% {
      left: 100%;
    }
  }

  /* Responsive Design */
  @media (min-width: 768px) {
    .projects-container {
      flex-direction: row; /* Arrange cards side-by-side on larger screens */
      justify-content: center; /* Center the cards horizontally */
      flex-wrap: wrap; /* Wrap cards if they exceed container width */
    }
  }
</style>