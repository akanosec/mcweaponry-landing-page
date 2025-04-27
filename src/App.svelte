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

  .gallery {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* 3 columns on desktop */
    gap: 1rem;
    margin: 4rem auto;
    width: 90%;
    max-width: 1200px;
  }

  .gallery-image {
    width: 100%;
    height: auto;
    object-fit: cover;
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    transition: transform 0.3s ease;
  }

  .gallery-image:hover {
    transform: scale(1.05);
  }

  @media (max-width: 1024px) {
    .gallery {
      grid-template-columns: repeat(2, 1fr);
    }
  }

  /* Responsive change for mobile */
  @media (max-width: 768px) {
    .gallery {
        grid-template-columns: 1fr; /* 1 column on mobile */
    }
  }

  section {
  padding: 4rem 2rem;
}

/*
.gallery-section {
  background-color: #121212;
  color: #fff;
}
*/

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
<section class="gallery">
  {#each galleryImages as image (image)}
    <img src={`/images/${image}`} alt="{image}" class="gallery-image" />
  {/each}
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
