<template>
  <div class="resort-header-wrap">
    <div class="header-banner">
      <img src="../assets/header.jpg" alt="Bale Concordia Resort" />
      <div class="image-overlay"></div>

      <div class="banner-content">
        <div class="title-band">
          <div class="text">
            <div class="brand-mark">
              <span class="material-icons">nature</span>
            </div>
            <h1>Bale Concordia</h1>
            <p class="tag">Cabins & Resort</p>
            <div class="accent-line"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
</script>

<style scoped>
.header-banner {
  position: relative;
  overflow: hidden;
}

.header-banner img {
  width: 100%;
  height: 420px;
  object-fit: cover;
  display: block;
  margin-bottom: 0;
}

/* Modern gradient overlay for better text contrast */
.image-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    180deg,
    rgba(6,20,12,0.15) 0%,
    rgba(6,20,12,0.35) 50%,
    rgba(6,20,12,0.55) 100%
  );
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

/* Modern glass-morphism title band */
.title-band {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  padding: 2.5rem 1rem 2.5rem 1rem; /* adjusted horizontal padding */
  background: linear-gradient(
    to right,
    rgba(255,255,255,0.92) 0%,
    rgba(255,255,255,0.85) 100%
  );
  backdrop-filter: blur(12px) saturate(180%);
  -webkit-backdrop-filter: blur(12px) saturate(180%);
  pointer-events: auto;
  border-top: 1px solid rgba(255,255,255,0.3);
  box-shadow: 0 -4px 24px rgba(0,0,0,0.08);
}

.title-band .text {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  max-width: 1200px;
  margin: 0; /* removed auto margin to align left */
  padding-left: 1rem; /* add left padding to move text left */
}

/* Brand icon/mark */
.brand-mark {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 48px;
  height: 48px;
  background: linear-gradient(135deg, #065f46, #0a8a5e);
  border-radius: 12px;
  margin-bottom: 0.75rem;
  box-shadow: 0 4px 12px rgba(6,95,70,0.2);
}

.brand-mark .material-icons {
  font-size: 28px;
  color: #ffffff;
}

.header-banner h1 {
  margin: 0;
  font-size: 3rem;
  line-height: 1;
  font-weight: 700;
  color: #065f46;
  letter-spacing: -0.03em;
  text-shadow: 0 2px 8px rgba(255,255,255,0.3);
}

.header-banner .tag {
  margin: 0;
  font-size: 1.1rem;
  color: rgba(0,0,0,0.7);
  font-weight: 500;
  letter-spacing: 0.02em;
  text-transform: uppercase;
  font-size: 0.85rem;
}

/* Decorative accent line */
.accent-line {
  width: 80px;
  height: 4px;
  background: linear-gradient(90deg, #065f46, rgba(6,95,70,0.2));
  border-radius: 2px;
  margin-top: 1rem;
}

/* Responsive adjustments */
@media (min-width: 1100px) {
  .header-banner img { height: 520px; }
  .title-band { padding: 3rem 2rem; }
  .title-band .text { padding-left: 2rem; } /* more left padding on desktop */
  .header-banner h1 { font-size: 3.5rem; }
  .header-banner .tag { font-size: 0.95rem; }
  .brand-mark { width: 56px; height: 56px; }
  .brand-mark .material-icons { font-size: 32px; }
}

@media (max-width: 900px) {
  .header-banner img { height: 360px; }
  .title-band { padding: 2rem 1rem; }
  .title-band .text { padding-left: 0.75rem; }
  .header-banner h1 { font-size: 2.2rem; }
  .header-banner .tag { font-size: 0.8rem; }
  .brand-mark { width: 40px; height: 40px; margin-bottom: 0.5rem; }
  .brand-mark .material-icons { font-size: 24px; }
  .accent-line { width: 60px; height: 3px; margin-top: 0.75rem; }
}

@media (max-width: 600px) {
  .header-banner img { height: 280px; }
  .title-band { padding: 1.5rem 0.75rem; }
  .title-band .text { padding-left: 0.5rem; }
  .header-banner h1 { font-size: 1.8rem; }
  .header-banner .tag { font-size: 0.75rem; }
}
</style>
