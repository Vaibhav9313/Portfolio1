<script>
  const about = {
        name: 'Vaibhav Jadhav',
        role: 'Frontend Developer',
        location: 'Pune, India',
        description:
            'Frontend Developer with around 3+ years of experience. I specialize in building modern web applications using HTML, CSS, JavaScript, Svelte, and React. My expertise lies in creating responsive and user-friendly interfaces.',
			interests: 'When I’m not coding, I enjoy reading fiction novels, exploring nature on hiking trips, and experimenting with photography. In my free time, I also love watching tech videos and learning about the latest developments in web technologies and design trends.',
    };
</script>

<main>
    <section id="about" class="section">
        <h2 class="section-title">About Me</h2>
        <div class="about-content">
            <p>{about.description}</p>
            <p>{about.interests}</p>
        </div>
    </section>
</main>

<style>
    .about-content {
        max-width: 700px;
        margin: 0 auto;
        font-size: 1rem;
    }
    @media (max-width: 768px) {
        .about-content {
            font-size: 0.95rem;
        }
    }
    @media (max-width: 480px) {
        .about-content {
            font-size: 0.9rem;
        }
    }
</style>