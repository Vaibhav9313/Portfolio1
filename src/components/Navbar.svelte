<main>
    <nav class="navbar">
        <div class="logo">Vaibhav</div>
    </nav>
</main>

<style>
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
    @media (max-width: 768px) {
        .logo {
            font-size: 1.1rem;
        }
    }
    @media (max-width: 480px) {
        .logo {
            font-size: 1rem;
        }
    }
</style>