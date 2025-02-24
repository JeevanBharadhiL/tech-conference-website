<script lang="ts">
  import { onMount } from 'svelte';

  let isLightMode = true;

  const toggleTheme = () => {
    isLightMode = !isLightMode;
    document.documentElement.setAttribute('data-theme', isLightMode ? 'light' : 'dark');
  };
</script>

<header class="navbar">
  <div class="logo">Tech_Conference..<span class="dot">.</span></div>

  <nav class="nav-links">
    <a href="/">Home</a>
    <a href="/speakers">Speakers</a>
    <a href="/schedule">Schedule</a>
    <a href="/sponsors">Sponsors</a>
    <a href="/about">About</a>
    <a href="/contact">Contact</a>
  </nav>

  <div class="search-bar">
    <span class="search-icon">🔍</span>
    <input type="text" placeholder="Search by Inspiration">
  </div>

  <div class="theme-toggle">
    <button class="light-mode-btn" on:click={toggleTheme}>
      {isLightMode ? '🌞 Light Mode' : '🌙 Dark Mode'}
    </button>
  </div>
</header>

<!-- Page Content Slot -->
<main class="container">
  <slot />  <!-- This ensures your page content is displayed below the navbar -->
</main>

<footer class="footer">
  <p>© 2025 Tech Conference. All Rights Reserved.</p>
</footer>

<style>
  /* Navbar styling */
  .navbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: #f4ebe9; /* Light pastel shade */
    padding: 0.8rem 2rem;
    border-bottom: 1px solid #ddd;
  }

  /* Logo */
  .logo {
    font-size: 1.8rem;
    font-weight: bold;
    display: flex;
    align-items: center;
  }
  
  .dot {
    color: black;
  }

  /* Navigation Links */
  .nav-links {
    display: flex;
    gap: 1.5rem;
  }

  .nav-links a {
    text-decoration: none;
    color: black;
    font-size: 1rem;
    font-weight: 500;
  }

  .nav-links a:hover {
    opacity: 0.7;
  }

  /* Search Bar */
  .search-bar {
    display: flex;
    align-items: center;
    background: rgba(0, 0, 0, 0.05);
    padding: 0.5rem 1rem;
    border-radius: 20px;
  }

  .search-bar input {
    border: none;
    background: transparent;
    outline: none;
    padding-left: 8px;
    font-size: 1rem;
  }

  /* Theme Toggle Button */
  .theme-toggle {
    display: flex;
    align-items: center;
  }

  .light-mode-btn {
    background: transparent;
    border: none;
    font-size: 1rem;
    cursor: pointer;
  }

  /* Main Content */
  .container {
    max-width: 1200px;
    margin: 2rem auto;
    padding: 2rem;
  }

  /* Footer */
  .footer {
    text-align: center;
    padding: 1rem 0;
    background: #f4ebe9;
    position: fixed;
    bottom: 0;
    width: 100%;
  }
</style>
