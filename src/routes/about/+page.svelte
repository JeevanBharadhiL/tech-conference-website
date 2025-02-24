<!-- src/routes/about/+page.svelte -->
<script lang="ts">
  import { Container } from 'sveltestrap';
</script>

<Container>
  <div class="card-block" style="background: var(--about-color);">
    <h1 class="page-title">About Tech Conference 2025</h1>
    <p class="intro-text">
      Tech Conference 2025 is a premier event bringing together innovators, developers, and industry leaders to explore the future of technology. Join us on June 15-17, 2025, in San Francisco for inspiring keynotes, hands-on workshops, and networking opportunities.
    </p>
  </div>
  <div class="map-container">
  <h2>Event Location</h2>
  <iframe
    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3151.8354345093747!2d144.9556516157084!3d-37.81732797975171!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x6ad65d43f1fef1b3%3A0x4a8d7f4dbe8fabc!2sMelbourne%20Convention%20and%20Exhibition%20Centre!5e0!3m2!1sen!2sau!4v1647956878774!5m2!1sen!2sau"
    width="100%"
    height="400"
    style="border:0;"
    allowfullscreen=""
    loading="lazy">
  </iframe>
</div>
</Container>

<style>
  .card-block {
    max-width: 800px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    border-radius: 12px;
  }

  .page-title {
    font-size: 3rem;
    text-align: center;
    margin-bottom: 2rem;
    color: var(--text-primary);
  }

  .intro-text {
    font-size: 1.2rem;
    line-height: 1.8;
    text-align: center;
    color: var(--text-primary);
    margin-bottom: 2rem;
  }

  @media (max-width: 768px) {
    .card-block {
      padding: 1rem;
    }

    .page-title {
      font-size: 2rem;
    }

    .intro-text {
      font-size: 1rem;
    }
  }

  .map-container {
    text-align: center;
    margin-top: 2rem;
  }
</style>
