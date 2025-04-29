<section id="about">
  <div class="about-container">
    <!-- Title -->
    <h2 class="about-title">About Me</h2>

    <!-- Content -->
    <div class="about-content">
      <!-- Text Section -->
      <div class="about-text">
        <p>
          Hi! I'm <strong>Vaibhav Jadhav</strong>, a Frontend Developer based in Pune, India, with over 
          <em>2.8 years of experience</em>. I specialize in building modern web applications using 
          <em>HTML, CSS, JavaScript, React, and Svelte</em>.
        </p>
        <p>
          My expertise lies in building responsive and user-friendly web applications using modern technologies like 
          <em>React, Svelte, and JavaScript</em>. I’ve contributed to projects such as enhancing a social media platform 
          and developing a reactive weather app, which dynamically adapts to real-time data for an optimal user experience.
        </p>
        <p>
          When I'm not coding, I enjoy organizing tech workshops, contributing to open-source projects, and 
          participating in community initiatives like water harvesting campaigns. I’m always eager to learn 
          new technologies and take on exciting challenges!
        </p>
      </div>

      <!-- Decorative Animation -->
      <div class="animation-box">
        <div class="circle"></div>
        <div class="circle"></div>
        <div class="circle"></div>
      </div>
    </div>
  </div>
</section>

<style>
  /* General Section Styling */
  section {
    padding: 3rem 1rem; /* Reduced padding for better spacing */
    text-align: center;
    background: linear-gradient(135deg, #1a1a1a, #2c2c2c); /* Dark gradient background */
    color: white; /* Light text color for readability */
    overflow: hidden; /* Hide overflow for animations */
  }

  /* Container for Layout */
  .about-container {
    max-width: 1000px; /* Reduced width for better focus */
    margin: 0 auto; /* Center the container */
  }

  /* Title Styling */
  .about-title {
    font-size: 2rem; /* Slightly smaller font size */
    font-weight: bold;
    margin-bottom: 1rem; /* Reduced spacing below the title */
    color: #00bcd4; /* New accent color (teal/cyan) */
    letter-spacing: 1px; /* Subtle letter spacing */
    position: relative; /* For animation */
    animation: fadeInUp 1.5s ease-in-out;
  }

  /* Content Layout (Text + Animation) */
  .about-content {
    display: flex;
    flex-direction: column; /* Stack content vertically on smaller screens */
    align-items: center;
    gap: 1.5rem; /* Reduced space between text and animation */
  }

  /* Text Styling */
  .about-text {
    max-width: 500px; /* Reduced text width for better readability */
    margin: 0 auto; /* Center the text */
    line-height: 1.5; /* Improved readability */
    font-size: 0.95rem; /* Slightly smaller font size */
    animation: fadeIn 1.5s ease-in-out;
  }

  .about-text p {
    margin-bottom: 0.75rem; /* Reduced spacing between paragraphs */
  }

  .about-text strong {
    color: #00bcd4; /* Highlight your name */
  }

  .about-text em {
    font-style: italic;
    color: #80cbc4; /* Highlight skills and interests */
  }

  /* Animation Box */
  .animation-box {
    position: relative;
    width: 150px;
    height: 150px;
    animation: float 3s infinite ease-in-out;
  }

  .circle {
    position: absolute;
    width: 50px;
    height: 50px;
    background: rgba(0, 188, 212, 0.3); /* Semi-transparent teal */
    border-radius: 50%;
    animation: pulse 2s infinite ease-in-out;
  }

  .circle:nth-child(1) {
    top: 0;
    left: 0;
    animation-delay: 0s;
  }

  .circle:nth-child(2) {
    top: 50%;
    right: 0;
    animation-delay: 0.5s;
  }

  .circle:nth-child(3) {
    bottom: 0;
    left: 50%;
    animation-delay: 1s;
  }

  /* Animations */
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

  @keyframes float {
    0% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-10px);
    }
    100% {
      transform: translateY(0);
    }
  }

  @keyframes pulse {
    0% {
      transform: scale(1);
      opacity: 0.3;
    }
    50% {
      transform: scale(1.2);
      opacity: 0.6;
    }
    100% {
      transform: scale(1);
      opacity: 0.3;
    }
  }

  /* Responsive Design */
  @media (min-width: 768px) {
    .about-content {
      flex-direction: row; /* Arrange text and animation side-by-side on larger screens */
      justify-content: space-between; /* Distribute space evenly */
    }

    .about-text {
      text-align: left; /* Align text to the left for better readability */
    }

    .animation-box {
      width: 200px;
      height: 200px;
    }

    .circle {
      width: 70px;
      height: 70px;
    }
  }
</style>