<script>
  import { fade } from 'svelte/transition';
  const galleryImages = [
    '380_engraved.webp',
    'gun_museum.webp',
    'mp_riot.webp',
    'p90_riot.webp',
    'revolver_engraving.webp',
    'usmc_gun.webp'
  ];
</script>

<style>
 :global(body) {
    margin: 0;
    font-family: 'Playfair Display', serif;
    background-color: #0e0e0e;
    color: #f5f5f5;
  }

  .hero {
    position: relative;
    background-image: url('/images/background_engraving_silhouette.jpeg');
    background-size: cover;
    background-position: center;
    color: white;
    height: 40vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
  }

  .hero .overlay {
    position: absolute;
    inset: 0;
    background: rgba(0, 0, 0, 0.4); /* dark semi-transparent */
    z-index: 1;
  }

  .hero-content {
    background: rgba(0, 0, 0, 0.4);
    backdrop-filter: blur(6px);
    border-radius: 8px;
    padding: 1.5rem;
  }

  .hero h1 {
    font-family: 'Anton', sans-serif;
    font-size: 3.5rem;
    letter-spacing: 2px;
  }

  .tagline {
    font-weight: 300;
    font-size: 1.2rem;
    max-width: 700px;
    margin: 0 auto;
  }

  .gallery {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
    padding: 3rem 2rem;
  }

  .gallery img {
    width: 100%;
    border: 2px solid #333;
    border-radius: 8px;
    object-fit: cover;
    height: 300px;
    background-color: #1a1a1a;
  }

  section {
  padding: 4rem 2rem;
}

.gallery-section {
  background-color: #121212;
  color: #fff;
}

.contact-section {
  background-color: #000;
  color: #f5f5f5;
  text-align: center;
}

h2 {
  font-family: 'Anton', sans-serif;
  font-size: 2rem;
  margin-bottom: 2rem;
  position: relative;
}

h2::after {
  content: '';
  display: block;
  width: 80px;
  height: 3px;
  background: #e63946;
  margin: 0.5rem auto 0;
}

  footer {
    text-align: center;
    padding: 2rem 1rem;
    font-size: 0.9rem;
    color: #666;
    background-color: #111;
    margin-top: 4rem;
  }

  footer a {
    color: #999;
    margin: 0 0.5rem;
  }
</style>

<!-- Hero Section -->
<section class="hero">
  <div class="overlay"></div>
  <div class="hero-content">
    <h1>MC Weaponry</h1>
    <p>07/02FFL • Founded by ACGG Master Engraver Madeline Crumling</p>
    <p>We produce the finest in hand engraved firearms</p>
  </div>
</section>

<!-- Gallery Section -->
<section class="gallery-section">
  <h2>Showcase</h2>
  <div class="gallery">
    {#each galleryImages as image}
      <img src={`/images/${image}`} alt={image} transition:fade={{ duration: 800 }} />
    {/each}
  </div>
</section>

<!-- Contact Section -->
<section class="contact-section">
  <h2>Contact Us</h2>
  <p>Email <a href="mailto:scarlett@mcweaponry.com">scarlett@mcweaponry.com</a> or DM <a href="https://x.com/scarlettajc" target="_blank">@scarlettajc</a> on X</p>
</section>

<!-- Footer -->
<footer>
  <div>
    <a href="https://x.com/mcweaponry" target="_blank">@mcweaponry</a> |
    <a href="https://x.com/scarlettajc" target="_blank">@scarlettajc</a>
  </div>
  <div>© 2025 MC Weaponry</div>
</footer>
