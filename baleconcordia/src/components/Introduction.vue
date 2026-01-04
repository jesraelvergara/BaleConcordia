<template>
  <section class="introduction">
    <div class="media">
      <img :src="hero" alt="Resort view" />
    </div>
    <div class="copy">
      <h2>Welcome to Bale Concordia</h2>
      <p>
        Nestled in the heart of nature, Bale Concordia offers cozy cabins and curated experiences
        for guests seeking calm and adventure alike. Enjoy warm hospitality, scenic views, and
        thoughtfully designed spaces that feel like home.
      </p>
      <p>
        Whether you're planning a quiet retreat or an active getaway, our resort provides the
        perfect base for exploring the natural beauty of Concepcion, Tarlac.
      </p>
    </div>
  </section>
</template>

<script setup>
const hero = new URL('../assets/hero.jpg', import.meta.url).href
</script>

<style scoped>
.introduction {
  display: flex;
  gap: 1rem;
  align-items: center;
  position: relative;
}
.media {
  flex: 0 0 60%; /* make image larger */
}
.media img {
  width: 100%;
  height: 360px; /* increased height */
  object-fit: cover;
  border-radius: 0; /* removed radius to make image sharp-edged */
  box-shadow: 0 10px 30px rgba(18,23,28,0.06);
  display: block;
}
.copy {
  flex: 1;
  margin-left: -30%; /* overlap half of the image (30% of container over 60% image -> 50% overlap) */
  background: rgba(255,255,255,0.95);
  padding: 1.25rem;
  box-shadow: 0 8px 24px rgba(18,23,28,0.06);
  border-radius: 8px;
}
.copy h2 { margin: 0 0 0.5rem 0 }
.copy p { margin: 0 0 0.75rem 0; color: rgba(0,0,0,0.7) }

@media (max-width: 900px) {
  .introduction { flex-direction: column; }
  .media { flex: none; width: 100%; }
  .media img { height: 220px }
  .copy { margin-left: 0; background: transparent; padding: 0 }
}
</style>
