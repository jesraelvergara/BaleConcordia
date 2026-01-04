<template>
  <article class="cabin-card">
    <div class="media" :style="`background-image: url(${image})`"></div>
    <div class="body">
      <div class="title-row">
        <h3>{{ title }}</h3>
        <div class="price">{{ price }}</div>
      </div>
      <p class="desc">{{ description }}</p>
      <div class="meta">
        <span><span class="material-icons">king_bed</span> {{ beds }} beds</span>
        <span><span class="material-icons">straighten</span> {{ area }} m²</span>
        <span><span class="material-icons">terrain</span> {{ view }}</span>
      </div>
      <div class="actions">
        <button class="btn">Details</button>
        <button class="btn primary">Reserve</button>
      </div>
    </div>
  </article>
</template>

<script setup>
const props = defineProps({
  image: { type: String, required: true },
  title: { type: String, required: true },
  price: { type: String, required: true },
  description: { type: String, default: '' },
  beds: { type: [Number, String], default: 2 },
  area: { type: [Number, String], default: 45 },
  view: { type: String, default: 'mountain' },
})
</script>

<style scoped>
.cabin-card {
  display: flex;
  flex-direction: column;
  border: 1px solid var(--color-border);
  border-radius: 12px;
  overflow: hidden;
  background: var(--color-background);
  box-shadow: 0 6px 20px rgba(18, 23, 28, 0.04);
}
.media {
  width: 100%;
  height: 180px;
  background-size: cover;
  background-position: center;
}
.body {
  padding: 1rem;
}
.title-row {
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap: 1rem;
}
.title-row h3 { margin: 0; font-size: 1.05rem; }
.price { color: hsl(160, 100%, 27%); font-weight: 700 }
.desc { color: rgba(0,0,0,0.65); margin: 0.6rem 0 }
.meta { display:flex; gap: 1rem; color: rgba(0,0,0,0.6); font-size: 0.9rem }
.meta .material-icons { vertical-align: middle; font-size: 18px; margin-right: 4px }
.actions { display:flex; gap: 0.5rem; margin-top: 0.8rem }
.btn { padding: 0.5rem 0.8rem; border-radius: 8px; border: 1px solid var(--color-border); background: transparent; cursor: pointer }
.btn.primary { background: hsl(160, 75%, 35%); color: white; border: none }
</style>
