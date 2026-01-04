<template>
  <section class="introduction">
    <div class="postcard-container">
      <div class="postcard-wrapper">
        <div class="postcard-frame">
          <div class="image-section">
            <img :src="hero" alt="Resort view" />
            <div class="image-overlay"></div>
          </div>
          <div class="content-section">
            <div class="postcard-stamp">
              <span class="material-icons">landscape</span>
            </div>
            <div class="content-inner">
              <h2>Welcome to Bale Concordia</h2>
              <div class="divider"></div>
              <p class="intro-text">
                Nestled in the heart of nature, Bale Concordia offers cozy cabins and curated experiences
                for guests seeking calm and adventure alike.
              </p>
              <p class="highlight">
                Enjoy warm hospitality, scenic views, and thoughtfully designed spaces that feel like home.
              </p>
              <div class="postcard-footer">
                <div class="location">
                  <span class="material-icons">place</span>
                  <span>Concepcion, Tarlac</span>
                </div>
                <div class="postmark">EST. 2025</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const hero = new URL('../assets/hero.jpg', import.meta.url).href
</script>

<style scoped>
.introduction {
  margin: 3rem 0;
  display: flex;
  justify-content: center;
}

.postcard-container {
  width: 100%; /* full width to match other sections */
  perspective: 1000px;
}

.postcard-wrapper {
  transition: transform 0.6s ease;
}

.postcard-wrapper:hover {
  transform: translateY(-8px);
}

.postcard-frame {
  background: #ffffff;
  border-radius: 0; /* removed radius */
  box-shadow: 
    0 4px 12px rgba(0,0,0,0.08),
    0 12px 32px rgba(0,0,0,0.06),
    0 0 0 1px rgba(0,0,0,0.04);
  overflow: hidden;
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  position: relative;
  min-height: 420px;
}

/* Decorative stamp in corner */
.postcard-stamp {
  position: absolute;
  top: 20px;
  right: 20px;
  width: 56px;
  height: 56px;
  background: linear-gradient(135deg, rgba(6,95,70,0.1), rgba(6,95,70,0.05));
  border: 2px dashed rgba(6,95,70,0.3);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 2;
}

.postcard-stamp .material-icons {
  color: #065f46;
  font-size: 28px;
}

.image-section {
  position: relative;
  overflow: hidden;
}

.image-section img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: transform 0.6s ease;
}

.postcard-wrapper:hover .image-section img {
  transform: scale(1.05);
}

.image-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    135deg,
    rgba(6,95,70,0.08) 0%,
    rgba(6,95,70,0) 50%
  );
  pointer-events: none;
}

.content-section {
  position: relative;
  padding: 2.5rem 2rem 2rem 2rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  background: linear-gradient(
    to bottom right,
    #ffffff 0%,
    #fafafa 100%
  );
}

.content-inner h2 {
  margin: 0 0 1rem 0;
  font-size: 1.85rem;
  font-weight: 600;
  color: #065f46;
  line-height: 1.2;
  letter-spacing: -0.02em;
}

.divider {
  width: 60px;
  height: 3px;
  background: linear-gradient(90deg, #065f46, rgba(6,95,70,0.3));
  margin-bottom: 1.25rem;
  border-radius: 2px;
}

.intro-text {
  margin: 0 0 1rem 0;
  color: rgba(0,0,0,0.75);
  font-size: 0.95rem;
  line-height: 1.6;
}

.highlight {
  margin: 0 0 1.5rem 0;
  color: rgba(0,0,0,0.65);
  font-size: 0.9rem;
  font-style: italic;
  line-height: 1.6;
  padding-left: 1rem;
  border-left: 3px solid rgba(6,95,70,0.2);
}

.postcard-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: auto;
  padding-top: 1.5rem;
  border-top: 1px dashed rgba(0,0,0,0.1);
}

.location {
  display: flex;
  align-items: center;
  gap: 6px;
  color: rgba(0,0,0,0.6);
  font-size: 0.85rem;
  font-weight: 500;
}

.location .material-icons {
  font-size: 18px;
  color: #065f46;
}

.postmark {
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 0.1em;
  color: rgba(0,0,0,0.4);
  font-family: 'Courier New', monospace;
}

/* Responsive design */
@media (max-width: 900px) {
  .postcard-frame {
    grid-template-columns: 1fr;
    min-height: auto;
  }
  
  .image-section {
    height: 280px;
  }
  
  .content-section {
    padding: 2rem 1.5rem;
  }
  
  .postcard-stamp {
    top: 12px;
    right: 12px;
    width: 48px;
    height: 48px;
  }
  
  .postcard-stamp .material-icons {
    font-size: 24px;
  }
  
  .content-inner h2 {
    font-size: 1.5rem;
  }
}

@media (max-width: 600px) {
  .introduction {
    margin: 2rem 0;
  }
  
  .postcard-footer {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.5rem;
  }
}
</style>
