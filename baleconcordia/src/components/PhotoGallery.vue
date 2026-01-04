<template>
  <section class="photo-gallery">
    <h2>Photo Gallery</h2>
    <p class="lead">A selection of moments from around the resort.</p>

    <div class="grid">
      <button
        v-for="(img, idx) in images"
        :key="idx"
        class="thumb"
        @click="open(idx)"
        :aria-label="`Open image ${idx + 1}`"
      >
        <img :src="img" :alt="`Gallery image ${idx + 1}`" />
      </button>
    </div>

    <div v-if="selected !== null" class="lightbox" @click.self="close">
      <button class="close" @click="close" aria-label="Close">×</button>
      <button class="nav prev" @click.stop="prev" aria-label="Previous">‹</button>
      <div class="lightbox-inner">
        <img :src="images[selected]" :alt="`Large image ${selected + 1}`" />
      </div>
      <button class="nav next" @click.stop="next" aria-label="Next">›</button>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

// Resolve asset URLs so Vite will process them correctly
const images = [
   
  new URL('../assets/cabin1.jpg', import.meta.url).href,
  new URL('../assets/cabin2.jpg', import.meta.url).href,
  new URL('../assets/cabin3.jpg', import.meta.url).href,
  // repeat or add placeholders to fill a 3x3 grid
  new URL('../assets/cabin4.jpg', import.meta.url).href,
  new URL('../assets/cabin5.jpg', import.meta.url).href,
  new URL('../assets/cabin6.jpg', import.meta.url).href,
  new URL('../assets/cabin7.jpg', import.meta.url).href,
  new URL('../assets/cabin8.jpg', import.meta.url).href,
  new URL('../assets/cabin9.jpg', import.meta.url).href,
]

const selected = ref(null)

function open(idx) {
  selected.value = idx
}
function close() {
  selected.value = null
}
function prev() {
  if (selected.value === null) return
  selected.value = (selected.value - 1 + images.length) % images.length
}
function next() {
  if (selected.value === null) return
  selected.value = (selected.value + 1) % images.length
}
</script>

<style scoped>
.photo-gallery {
  margin: 0; /* removed outer margin */
  padding: 0; /* remove padding as requested */
}
.photo-gallery h2 {
  margin: 0 0 0.25rem 0;
  font-size: 1.4rem;
}
.photo-gallery .lead {
  margin: 0 0 1rem 0;
  color: rgba(0,0,0,0.65);
}
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* 3 columns */
  grid-template-rows: repeat(3, 180px); /* 3 rows fixed height */
  gap: 0; /* removed gap between grid cells */
}
.thumb {
  border: 0;
  padding: 0;
  background: transparent;
  cursor: pointer;
  overflow: hidden;
}
.thumb img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: transform 0.3s ease;
  border-radius: 0; /* remove any corner radius */
}
.thumb:hover img { transform: scale(1.04); }

@media (min-width: 1100px) {
  .grid { grid-template-rows: repeat(3, 220px); }
}

/* lightbox */
.lightbox {
  position: fixed;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(4,8,6,0.6);
  z-index: 1200;
}
.lightbox-inner img {
  max-width: 92vw;
  max-height: 82vh;
  box-shadow: 0 18px 50px rgba(2,6,8,0.6);
  border-radius: 0; /* remove radius for full-bleed look */
}
.close {
  position: fixed;
  top: 28px;
  right: 28px;
  background: rgba(255,255,255,0.9);
  border: none;
  width: 44px;
  height: 44px;
  border-radius: 8px;
  font-size: 22px;
  cursor: pointer;
}
.nav {
  position: fixed;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(255,255,255,0.9);
  border: none;
  width: 44px;
  height: 64px;
  border-radius: 8px;
  font-size: 28px;
  cursor: pointer;
}
.prev { left: 20px; }
.next { right: 20px; }
</style>
