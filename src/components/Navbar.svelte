<script>
  // State for active section and mobile menu toggle
  export let activeSection;
  export let onNavigate;

  const sections = ['Home', 'About', 'Projects', 'Contact'];
  let isMenuOpen = false; // Tracks whether the mobile menu is open

  // Function to handle navigation
  function handleClick(section) {
    onNavigate(section); // Update the active section
    isMenuOpen = false; // Close the menu after navigation
  }

  // Toggle the mobile menu
  function toggleMenu() {
    isMenuOpen = !isMenuOpen; // Toggle the menu state
    console.log('Menu Open:', isMenuOpen); // Debugging line
  }

  // Close the menu when clicking outside
  function closeMenuOnClickOutside(event) {
    const navLinksMobile = document.querySelector('.nav-links.mobile');
    if (isMenuOpen && navLinksMobile && !navLinksMobile.contains(event.target)) {
      isMenuOpen = false; // Close the menu if clicking outside
    }
  }

  // Close the menu when resizing to a larger screen
  function handleResize() {
    if (window.innerWidth > 768) {
      isMenuOpen = false; // Close the mobile menu on larger screens
    }
  }

  // Add event listeners for outside clicks and screen resize
  import { onMount, onDestroy } from 'svelte';
  onMount(() => {
    document.addEventListener('click', closeMenuOnClickOutside);
    window.addEventListener('resize', handleResize);
  });

  onDestroy(() => {
    document.removeEventListener('click', closeMenuOnClickOutside);
    window.removeEventListener('resize', handleResize);
  });
</script>

<!-- Navbar -->
<nav class="navbar">
  <!-- Logo -->
  <div class="logo">My Portfolio</div>

  <!-- Desktop Navigation Links -->
  <ul class="nav-links desktop">
    {#each sections as section}
      <li
        class="nav-item"
        class:active={activeSection === section}
        on:click={() => handleClick(section)}
      >
        {section}
      </li>
    {/each}
  </ul>

  <!-- Hamburger Menu Button (Mobile) -->
  <button class="hamburger" on:click={(e) => { e.stopPropagation(); toggleMenu(); }}>
    {#if isMenuOpen}
      <span class="bar"></span>
      <span class="bar"></span>
      <span class="bar"></span>
    {:else}
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24">
        <path fill="none" d="M0 0h24v24H0z" />
        <path d="M3 18h18v-2H3v2zm0-5h18v-2H3v2zm0-7v2h18V6H3z" />
      </svg>
    {/if}
  </button>

  <!-- Mobile Navigation Links -->
  <ul class="nav-links mobile" style="display: {isMenuOpen ? 'flex' : 'none'};">
    {#each sections as section}
      <li
        class="nav-item"
        class:active={activeSection === section}
        on:click={() => handleClick(section)}
      >
        {section}
      </li>
    {/each}
  </ul>
</nav>

<style>
  /* General Navbar Styles */
  .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    background: linear-gradient(135deg, #1a1a1a, #2c2c2c);
    color: white;
    position: sticky;
    top: 0;
    z-index: 1000;
  }

  /* Logo */
  .logo {
    font-size: 1.5rem;
    font-weight: bold;
    cursor: default;
    letter-spacing: 1px;
  }

  /* Desktop Navigation Links */
  .nav-links.desktop {
    display: flex;
    gap: 1.5rem; /* Add spacing between links */
    list-style: none;
    margin: 0;
    padding: 0;
  }

  .nav-item {
    cursor: pointer;
    font-size: 1rem;
    font-weight: 500;
    transition: color 0.3s ease, transform 0.3s ease;
  }

  .nav-item:hover {
    color: #bb86fc; /* Vibrant accent color */
    transform: scale(1.01);
  }

  /* Active Tab Styling */
  .nav-item.active {
    color: #bb86fc; /* Vibrant accent color */
    border-bottom: 2px solid #bb86fc; /* Underline effect */
  }

  /* Hamburger Menu Button */
  .hamburger {
    display: none; /* Hidden on desktop */
    background: none;
    border: none;
    cursor: pointer;
    padding: 0;
    z-index: 1001;
  }

  .hamburger svg {
    width: 24px;
    height: 24px;
    fill: white;
  }

  /* Mobile Navigation Links */
  .nav-links.mobile {
    display: none;
    flex-direction: column;
    gap: 1rem;
    list-style: none;
    margin: 0;
    padding: 1rem;
    background: linear-gradient(135deg, #1a1a1a, #2c2c2c);
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%; /* Full width */
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
    z-index: 1000;
  }

  /* Responsive Styles */
  @media (max-width: 768px) {
    .nav-links.desktop {
      display: none; /* Hide desktop links on mobile */
    }

    .hamburger {
      display: block; /* Show hamburger menu on mobile */
    }

    .nav-links.mobile {
      width: 100%; /* Ensure full width on mobile */
    }
  }
</style>