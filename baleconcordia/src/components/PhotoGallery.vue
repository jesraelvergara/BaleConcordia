<template>
  <section id="photo-gallery" class="photo-gallery">
    <h2>Photo Gallery</h2>
    <p class="lead">A selection of moments from around the resort.</p>

    <div class="grid">
      <button
        v-for="(img, idx) in images"
        :key="idx"
        class="thumb postcard"
        @click="open(idx)"
        :aria-label="`Open image ${idx + 1}`"
      >
        <div class="postcard-inner">
          <img :src="img" :alt="`Gallery image ${idx + 1}`" />
          <div class="postcard-footer"></div>
        </div>
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
  // repeat or add placeholders to fill a 3x3 grid
  new URL('../assets/cabin4.jpg', import.meta.url).href,
  new URL('../assets/cabin5.jpg', import.meta.url).href,
  new URL('../assets/cabin6.jpg', import.meta.url).href,
  new URL('../assets/cabin7.jpg', import.meta.url).href,
  new URL('../assets/cabin8.jpg', import.meta.url).href,
  new URL('../assets/cabin9.jpg', import.meta.url).href,
  new URL('../assets/cabin12.jpg', import.meta.url).href,
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
  margin: 0;
  padding: 0;
  scroll-margin-top: 2rem; /* offset for smooth scroll */
}
.photo-gallery h2 {
  margin: 0 0 0.25rem 0;
  font-size: 1.4rem;
}
.photo-gallery .lead {
  margin: 0 0 1.5rem 0;
  color: rgba(0,0,0,0.65);
}
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
  padding: 1rem 0;
}

/* Postcard/Polaroid style */
.thumb.postcard {
  border: 0;
  padding: 0;
  background: transparent;
  cursor: pointer;
  transition: transform 0.3s ease;
}

.postcard-inner {
  background: #ffffff;
  padding: 12px 12px 32px 12px; /* extra bottom padding for polaroid effect */
  box-shadow: 
    0 2px 8px rgba(0,0,0,0.08),
    0 8px 20px rgba(0,0,0,0.06);
  border-radius: 2px;
  transition: all 0.3s ease;
}

.thumb.postcard:hover .postcard-inner {
  transform: translateY(-4px) rotate(0deg);
  box-shadow: 
    0 6px 16px rgba(0,0,0,0.12),
    0 12px 32px rgba(0,0,0,0.1);
}

/* Add slight rotation to odd/even items for organic look */
.thumb.postcard:nth-child(odd) .postcard-inner {
  transform: rotate(-1deg);
}
.thumb.postcard:nth-child(even) .postcard-inner {
  transform: rotate(1deg);
}
.thumb.postcard:nth-child(3n) .postcard-inner {
  transform: rotate(0.5deg);
}

.thumb.postcard img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  display: block;
  border-radius: 1px;
}

.postcard-footer {
  height: 20px; /* space at bottom like polaroid */
}

@media (min-width: 1100px) {
  .thumb.postcard img { height: 240px; }
  .grid { gap: 2rem; }
}

@media (max-width: 700px) {
  .grid { 
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }
  .thumb.postcard img { height: 160px; }
}

/* lightbox */
.lightbox {
  position: fixed;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(4,8,6,0.85);
  z-index: 1200;
  backdrop-filter: blur(4px);
}
.lightbox-inner img {
  max-width: 90vw;
  max-height: 85vh;
  box-shadow: 
    0 20px 60px rgba(0,0,0,0.4),
    0 8px 24px rgba(0,0,0,0.3);
  border-radius: 0;
}
.close {
  position: fixed;
  top: 28px;
  right: 28px;
  background: rgba(255,255,255,0.95);
  border: none;
  width: 48px;
  height: 48px;
  border-radius: 50%;
  font-size: 24px;
  cursor: pointer;
  box-shadow: 0 4px 12px rgba(0,0,0,0.15);
  transition: all 0.2s ease;
}
.close:hover {
  background: #ffffff;
  transform: scale(1.05);
}
.nav {
  position: fixed;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(255,255,255,0.95);
  border: none;
  width: 48px;
  height: 64px;
  border-radius: 8px;
  font-size: 32px;
  cursor: pointer;
  box-shadow: 0 4px 12px rgba(0,0,0,0.15);
  transition: all 0.2s ease;
}
.nav:hover {
  background: #ffffff;
  transform: translateY(-50%) scale(1.05);
}
.prev { left: 20px; }
.next { right: 20px; }
</style>
