<!-- src/lib/components/Hero.svelte -->
<script lang="ts">
  import { Button } from 'sveltestrap';
  import { goto } from '$app/navigation'; // Import for navigation

  export let title: string = 'Tech Conference 2025';
  export let tagline: string = 'Innovate, Connect, Celebrate';
  export let buttonText: string = 'Register Now';
  export let buttonLink: string = '/register';

  function handleClick() {
    goto(buttonLink);
  }
</script>

<div class="hero jumbotron">
  <div class="shape-circle" style="top: 20%; left: 5%;"></div>
  <div class="shape-triangle" style="bottom: 20%; right: 5%;"></div>
  <div class="hero-content">
    <h1>{title}</h1>
    <p>{tagline}</p>
    <Button color="primary" on:click={handleClick}>{buttonText}</Button>
  </div>
</div>

<style>
  .hero {
    position: relative;
    padding: 4rem 2rem 2rem;
    background: linear-gradient(135deg, #e9ecef 0%, #dee2e6 100%);
    border-radius: 8px;
    box-shadow: var(--shadow);
    margin-bottom: 2rem;
    overflow: hidden;
    animation: fadeIn 1s ease-in;
  }

  .hero-content {
    text-align: center;
    z-index: 1;
  }

  h1 {
    font-size: 4rem;
    margin-bottom: 1rem;
    color: var(--text-primary);
  }

  p {
    font-size: 1.5rem;
    margin-bottom: 2rem;
    color: var(--text-secondary);
  }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @media (max-width: 768px) {
    .hero {
      padding: 2rem 1rem 1rem;
    }

    h1 {
      font-size: 2.5rem;
    }

    p {
      font-size: 1.2rem;
    }
  }
</style>