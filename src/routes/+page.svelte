<script lang="ts">
  import { onMount } from 'svelte';
  import { Container, Row, Col } from 'sveltestrap';
  import Hero from '$lib/components/Hero.svelte';
  import SpeakerCard from '$lib/components/SpeakerCard.svelte';
  import { speakers } from '$lib/data/speakers';

  let eventDate = new Date("2025-03-01T00:00:00").getTime();
  let countdown = { days: 0, hours: 0, minutes: 0, seconds: 0 };

  function updateCountdown() {
    const now = new Date().getTime();
    const distance = eventDate - now;

    countdown = {
      days: Math.floor(distance / (1000 * 60 * 60 * 24)),
      hours: Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)),
      minutes: Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60)),
      seconds: Math.floor((distance % (1000 * 60)) / 1000)
    };

    console.log(countdown); // Debugging log to check values

    if (distance < 0) {
      countdown = { days: 0, hours: 0, minutes: 0, seconds: 0 };
    }
  }

  onMount(() => {
    updateCountdown();
    const interval = setInterval(updateCountdown, 1000);
    return () => clearInterval(interval);
  });
</script>

<Container>
  <div class="card-block" style="background: var(--home-color);">
    <Hero />

    <!-- Countdown Timer -->
    <div class="countdown-container">
      <h3>Event Starts In</h3>
      <div class="countdown-timer">
        <div class="time-box">
          <div class="time-number">{countdown.days}</div>
          <div class="time-label">Days</div>
        </div>
        <div class="time-box">
          <div class="time-number">{countdown.hours}</div>
          <div class="time-label">Hours</div>
        </div>
        <div class="time-box">
          <div class="time-number">{countdown.minutes}</div>
          <div class="time-label">Minutes</div>
        </div>
        <div class="time-box">
          <div class="time-number">{countdown.seconds}</div>
          <div class="time-label">Seconds</div>
        </div>
      </div>
    </div>

    <!-- Register Now Button -->
    <button class="register-btn">Register Now</button>
  </div>

  <h2 class="speakers-title">Keynote Speakers</h2>
  <div class="card-block d-flex flex-wrap justify-content-center" style="background: var(--home-color);">
    <Row>
      {#each speakers.slice(0, 3) as speaker}
        <Col md="4" class="mb-4">
          <SpeakerCard {speaker} />
        </Col>
      {/each}
    </Row>
  </div>
</Container>

<style>
  .card-block {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    border-radius: 12px;
    padding: 2rem;
  }

  .countdown-container {
    text-align: center;
    margin-top: 1rem;
    padding: 1rem;
  }

  .countdown-timer {
    display: flex;
    justify-content: center;
    gap: 1.5rem;
    font-size: 1.2rem;
  }

  .time-box {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 15px;
    background: #f8f9fa; /* Light gray background */
    color: black;
    border-radius: 12px;
    min-width: 90px;
    text-align: center;
    font-weight: bold;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    transition: transform 0.3s ease-in-out;
  }

  .time-box:hover {
    transform: scale(1.1);
  }

  .time-number {
    font-size: 2rem;
    font-weight: bold;
    color: black; /* Ensure visibility */
    display: block;
  }

  .time-label {
    font-size: 1rem;
    opacity: 0.8;
  }

  @keyframes flip {
    0% {
      transform: rotateX(90deg);
      opacity: 0;
    }
    100% {
      transform: rotateX(0deg);
      opacity: 1;
    }
  }

  .register-btn {
    margin-top: 1rem;
    padding: 10px 20px;
    background: var(--secondary-color);
    color: white;
    border: none;
    cursor: pointer;
    font-size: 1.2rem;
    border-radius: 5px;
  }

  .register-btn:hover {
    background: var(--accent-color);
  }

  .speakers-title {
    font-size: 2.5rem;
    text-align: center;
    margin: 3rem 0 2rem;
    color: var(--text-primary);
  }

  @media (max-width: 768px) {
    .card-block {
      padding: 1rem;
    }

    .speakers-title {
      font-size: 2rem;
    }

    .countdown-timer {
      font-size: 1rem;
      gap: 1rem;
    }

    .time-box {
      min-width: 70px;
      padding: 10px;
    }

    .time-number {
      font-size: 1.5rem;
    }

    .time-label {
      font-size: 0.8rem;
    }
  }
</style>
