<template>
  <footer class="site-footer">
    <div class="inner">
      <div class="brand">
        <strong>Bale Concordia</strong>
        <span>Cabins & Mountain Resort</span>
      </div>

      <div class="copyright">© {{ year }} Bale Concordia. All rights reserved.</div>
    </div>
  </footer>
</template>

<script setup>
import { ref } from 'vue'
const year = new Date().getFullYear()
</script>

<style scoped>
.site-footer {
  /* green themed background */
  background: linear-gradient(90deg, #0b7a52, #065f46);
  color: #ffffff;
  padding: 1.2rem 0;
}
.site-footer .inner {
  display: flex;
  gap: 1rem;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  padding: 0 1rem; /* add horizontal padding so text doesn't touch edges */
}
.brand strong { color: #ffffff; font-weight: 700; display:block }
.brand span { font-size: 0.9rem; color: rgba(255,255,255,0.9) }
.copyright { font-size: 0.9rem; color: rgba(255,255,255,0.85); padding-left: 0.5rem; padding-right: 0.5rem; }

@media (max-width: 700px) {
  .site-footer .inner { flex-direction: column; align-items: flex-start }
}
</style>
