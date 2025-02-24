<!-- src/routes/speakers/+page.svelte -->
<script lang="ts">
  import { Container, Row, Col } from 'sveltestrap'; // Corrected to 'sveltestrap'
  import SpeakerCard from '$lib/components/SpeakerCard.svelte';
  import { speakers } from '$lib/data/speakers';
</script>

<div class="page-container">
  <Container class="speakers-container">
    <h1 class="page-title">Meet Our Speakers</h1>
    <div class="speakers-grid">
      <Row class="justify-content-center align-items-center">
        {#each speakers as speaker, index (speaker.name)} <!-- Use speaker.name as key for stability -->
          <Col md="4" class="mb-4 d-flex justify-content-center">
            <SpeakerCard {speaker} />
          </Col>
          {#if index < speakers.length - 1} <!-- Add line after each speaker except the last -->
            <Col md="12" class="divider-col">
              <hr class="speaker-divider" />
            </Col>
          {/if}
        {/each}
      </Row>
    </div>
  </Container>
</div>

<style>
  /* Full-page centering */
  .page-container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    padding: 2rem;
    background: var(--bg-primary);
    animation: swirlFade 5s infinite ease-in-out; /* Slowed down */
  }

  .speakers-container {
    max-width: 1200px;
    width: 100%;
    padding: 3rem 2rem;
    background: var(--card-bg);
    border-radius: 12px;
    box-shadow: var(--shadow);
    text-align: center;
    animation: pulse 4s infinite ease-in-out; /* Slowed down */
  }

  .page-title {
    font-size: 2.5rem;
    font-weight: 700;
    margin-bottom: 2rem;
    color: var(--text-primary);
    animation: slideAndRotate 4s ease-in-out infinite; /* Slowed down */
    text-shadow: 0 0 10px rgba(255, 255, 255, 0.3);
  }

  .speakers-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
    width: 100%;
    animation: slideLeft 5s ease-in-out infinite; /* Slowed down */
  }

  .justify-content-center.align-items-center {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
  }

  .d-flex.justify-content-center {
    display: flex;
    justify-content: center;
  }

  .divider-col {
    display: flex;
    justify-content: center;
    padding: 0.5rem 0;
  }

  .speaker-divider {
    width: 80%; /* Centered, not full width for professionalism */
    border: 1px solid #000000; /* Black line */
    margin: 0 auto; /* Center the line */
    animation: fadeIn 3s ease-in-out infinite alternate; /* Slowed down animation for subtlety */
  }

  @keyframes swirlFade {
    0% { background-position: 0% 0%; opacity: 0.9; }
    50% { background-position: 100% 100%; opacity: 1; }
    100% { background-position: 0% 0%; opacity: 0.9; }
  }

  @keyframes pulse {
    0% { transform: scale(1); box-shadow: var(--shadow); }
    50% { transform: scale(1.03); box-shadow: 0 6px 15px rgba(0, 0, 0, 0.3); }
    100% { transform: scale(1); box-shadow: var(--shadow); }
  }

  @keyframes slideAndRotate {
    0% { transform: translateX(-20px) rotate(0deg); opacity: 0; }
    50% { transform: translateX(10px) rotate(2deg); opacity: 1; }
    100% { transform: translateX(0) rotate(0deg); opacity: 1; }
  }

  @keyframes slideLeft {
    0% { transform: translateX(0); }
    50% { transform: translateX(-5px); }
    100% { transform: translateX(0); }
  }

  @keyframes fadeIn {
    0% { opacity: 0.8; }
    100% { opacity: 1; }
  }

  @media (max-width: 768px) {
    .speakers-container {
      padding: 2rem 1rem;
    }

    .page-title {
      font-size: 2rem;
    }

    .speakers-grid {
      grid-template-columns: 1fr; /* Stack on mobile */
      gap: 1rem;
    }

    .speaker-divider {
      width: 90%; /* Slightly wider on mobile for visibility */
    }
  }
</style>