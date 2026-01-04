<template>
  <section id="location" class="location-section">
    <h2>Location</h2>
    <p class="lead">Find us on the map.</p>

    <div class="map">
      <iframe
        title="Bale Concordia Location"
        loading="lazy"
        src="https://www.google.com/maps?q=8J2H%2BHRX+Bale+Concordia%2C+Concepcion%2C+Tarlac%2C+Philippines&z=17&output=embed"
        allowfullscreen
      ></iframe>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.location-section { 
  margin: 2rem 0;
  scroll-margin-top: 2rem; /* offset for smooth scroll */
}
.location-section h2 { margin: 0 0 0.25rem 0; font-size: 1.4rem }
.location-section .lead { margin: 0 0 1rem 0; color: rgba(0,0,0,0.65) }

.map { margin-top: 1rem; height: 320px; border-radius: 8px; overflow: hidden; box-shadow: 0 8px 24px rgba(18,23,28,0.06) }
.map iframe { width: 100%; height: 100%; border: 0; display: block }

@media (min-width: 700px) {
  .map { height: 420px }
}
</style>
