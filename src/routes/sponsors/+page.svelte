<script lang="ts">
  import { Container } from 'sveltestrap';
  import { sponsors } from '$lib/data/sponsors';
</script>

<Container>
  <div class="sponsors-container">
    <h1 class="page-title">Our Sponsors</h1>
    <div class="sponsors-logos">
      {#each sponsors as sponsor}
        <div class="sponsor-logo">
          <img src={sponsor.logo} alt={sponsor.name} />
        </div>
      {/each}
    </div>
  </div>
</Container>

<style>
  /* Sponsors Section */
  .sponsors-container {
    max-width: 1200px;
    margin: 2rem auto;
    text-align: center;
  }

  /* Title */
  .page-title {
    font-size: 2.5rem;
    font-weight: bold;
    margin-bottom: 2rem;
    color: var(--text-primary);
  }

  /* Sponsors Row */
  .sponsors-logos {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 3rem;
    flex-wrap: wrap;
    padding: 1rem 0;
  }

  /* Sponsor Logos */
  .sponsor-logo img {
    max-width: 120px; /* Adjust size */
    height: auto;
    opacity: 0.8;
    transition: transform 0.3s ease, opacity 0.3s ease;
  }

  /* Hover Effect */
  .sponsor-logo img:hover {
    opacity: 1;
    transform: scale(1.1);
  }

  /* Responsive */
  @media (max-width: 768px) {
    .sponsors-logos {
      gap: 2rem;
    }
    
    .sponsor-logo img {
      max-width: 90px;
    }
  }
</style>
