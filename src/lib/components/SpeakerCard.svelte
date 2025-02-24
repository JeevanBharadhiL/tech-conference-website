<!-- src/lib/components/SpeakerCard.svelte -->
<script lang="ts">
  import { Card, CardBody, CardSubtitle, CardText } from 'sveltestrap';
  export let speaker: { name: string; title: string; bio: string; image: string };

  let isHovered: boolean = false;
</script>

<Card class="cell-card" on:mouseover={() => isHovered = true} on:mouseout={() => isHovered = false}>
  <div class="speaker-profile">
    <img src={speaker.image} class="profile-img" alt={speaker.name} />
    <h3 class="speaker-name">{speaker.name}</h3>
  </div>
  <CardBody>
    <CardSubtitle class="mb-2 text-muted card-subtitle">{speaker.title}</CardSubtitle>
    <CardText class="card-text">{speaker.bio}</CardText>
  </CardBody>
</Card>

<style>
  .cell-card {
    background: var(--card-bg);
    border-radius: 12px; /* Slight curve for cell-like appearance */
    box-shadow: var(--shadow);
    overflow: hidden;
    transition: var(--transition);
    position: relative;
    width: 100%;
    max-width: 300px; /* Ensure card fits neatly in grid */
    clip-path: polygon(0% 5%, 95% 5%, 100% 50%, 95% 95%, 5% 95%, 0% 50%); /* Hexagonal clip for cell-like effect */
    background: linear-gradient(135deg, rgba(15, 52, 96, 0.1), rgba(239, 69, 96, 0.1)); /* Subtle abstract gradient */
    border: 2px solid var(--gradient-1); /* Abstract art-inspired border */
  }

  .cell-card:hover {
    transform: scale(1.03) rotate(-1deg); /* Subtle hover effect */
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
    background: var(--gradient-2); /* Vibrant hover gradient */
  }

  .speaker-profile {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 1rem;
    background: var(--gradient-1); /* Abstract art-inspired background */
    border-radius: 12px 12px 0 0;
    animation: pulse 5s infinite ease-in-out; /* Slowed down */
  }

  .profile-img {
    width: 150px; /* Professional, not too large */
    height: 150px;
    border-radius: 50%; /* Circular profile */
    object-fit: cover; /* Maintain aspect ratio */
    transition: var(--transition);
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    border: 3px solid var(--bg-primary); /* Subtle border for contrast */
  }

  .cell-card:hover .profile-img {
    transform: scale(1.05); /* Subtle zoom on hover */
    box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
  }

  .speaker-name {
    font-size: 1.5rem;
    font-weight: 600;
    color: var(--text-primary);
    margin-top: 1rem;
    text-align: center;
    text-shadow: 0 0 5px rgba(255, 255, 255, 0.5);
    animation: slideAndRotate 4s ease-in-out infinite; /* Slowed down */
  }

  .card-subtitle, .card-text {
    color: var(--text-secondary);
    animation: fadeIn 3s ease-in-out infinite alternate; /* Slowed down */
  }

  @keyframes pulse {
    0% { transform: scale(1); box-shadow: var(--shadow); }
    50% { transform: scale(1.02); box-shadow: 0 6px 15px rgba(0, 0, 0, 0.3); }
    100% { transform: scale(1); box-shadow: var(--shadow); }
  }

  @keyframes slideAndRotate {
    0% { transform: translateX(-5px) rotate(0deg); opacity: 0.9; }
    50% { transform: translateX(5px) rotate(1deg); opacity: 1; }
    100% { transform: translateX(0) rotate(0deg); opacity: 0.9; }
  }

  @keyframes fadeIn {
    0% { opacity: 0.8; }
    100% { opacity: 1; }
  }

  @media (max-width: 768px) {
    .cell-card {
      max-width: 250px;
      margin: 0.5rem;
    }

    .profile-img {
      width: 120px;
      height: 120px;
    }

    .speaker-name {
      font-size: 1.2rem;
    }
  }
</style>