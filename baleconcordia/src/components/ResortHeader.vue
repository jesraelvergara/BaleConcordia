<template>
  <div class="resort-header-wrap">
    <div class="header-banner">
      <img src="../assets/header.jpg" alt="Bale Concordia Resort" />

      <div class="banner-content">
        <div class="title-band">
          <div class="text">
            <h1>Bale Concordia</h1>
            <p class="tag">Cabins & Resort</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// Animations removed — keep script empty
</script>

<style scoped>
.header-banner {
  position: relative;
  overflow: hidden;
}
.header-banner img {
  width: 100%;
  height: 320px;
  object-fit: cover;
  border-radius: 0;
  display: block;
  margin-bottom: 1rem;
}

/* subtle dark gradient for better contrast */
.header-banner::after {
  content: '';
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  background: linear-gradient(180deg, rgba(6,20,12,0.10) 0%, rgba(6,20,12,0.45) 100%);
  pointer-events: none;
}

.banner-content {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  display: flex;
  justify-content: flex-start;
  pointer-events: none;
  padding: 0;
}

/* horizontal band behind the title spanning across the header */
.title-band {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 28px;
  height: 84px;
  background: rgba(255,255,255,0.6);
  border-radius: 0;
  display: flex;
  align-items: center;
  padding: 12px 32px;
  box-shadow: 0 10px 30px rgba(18, 23, 28, 0.08);
  pointer-events: auto;
}

.title-band .text { display: flex; flex-direction: column; }

.header-banner h1 {
  margin: 0 0 6px 0;
  font-size: 1.9rem;
  line-height: 1;
  font-weight: 700;
  color: #065f46;
  letter-spacing: -0.02em;
}
.header-banner .tag {
  margin: 0;
  font-size: 0.98rem;
  color: rgba(0,0,0,0.75);
  font-weight: 500;
}

@media (min-width: 1100px) {
  .header-banner img { height: 420px; }
  .title-band { bottom: 36px; height: 104px; }
  .header-banner h1 { font-size: 2.6rem; }
  .header-banner .tag { font-size: 1.05rem; }
}

.resort-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  padding: 0.6rem 0 1.2rem 0;
  border-bottom: 1px solid var(--color-border);
}
.left {
  display: flex;
  align-items: center;
  gap: 1rem;
}
.logo {
  width: 64px;
  height: 64px;
  object-fit: contain;
  border-radius: 12px;
  box-shadow: 0 6px 18px rgba(22, 28, 37, 0.08);
}
</style>
