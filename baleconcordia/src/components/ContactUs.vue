<template>
  <section id="contact-us" class="contact-us">
    <h2>Contact Us</h2>
    <p class="lead">Reach out for bookings, questions, or collaborations.</p>

    <div class="cards">
      <div class="card postcard">
        <div class="postcard-inner">
          <div class="icon-wrapper">
            <span class="material-icons">location_on</span>
          </div>
          <div class="card-content">
            <h3>Address</h3>
            <p>1072 Purok 3, San Francisco, Concepcion, Tarlac</p>
          </div>
          <div class="postcard-stamp">
            <div class="stamp-mark"></div>
          </div>
        </div>
      </div>

      <div class="card postcard">
        <div class="postcard-inner">
          <div class="icon-wrapper">
            <span class="material-icons">phone</span>
          </div>
          <div class="card-content">
            <h3>Phone</h3>
            <p><a href="tel:00000000000">00000000000</a></p>
          </div>
          <div class="postcard-stamp">
            <div class="stamp-mark"></div>
          </div>
        </div>
      </div>

      <div class="card postcard">
        <div class="postcard-inner">
          <div class="icon-wrapper">
            <span class="material-icons">email</span>
          </div>
          <div class="card-content">
            <h3>Email</h3>
            <p><a href="mailto:baleconcordia@gmail.com">baleconcordia@gmail.com</a></p>
          </div>
          <div class="postcard-stamp">
            <div class="stamp-mark"></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.contact-us { 
  margin: 2rem 0;
  scroll-margin-top: 2rem; /* offset for smooth scroll */
}
.contact-us h2 { margin: 0 0 0.25rem 0; font-size: 1.4rem; font-weight: 700; }
.contact-us .lead { margin: 0 0 1.5rem 0; color: rgba(0,0,0,0.65) }

.cards { 
  display: grid; 
  grid-template-columns: 1fr; 
  gap: 1.5rem;
  padding: 1rem 0;
}

/* Postcard style cards */
.card.postcard {
  background: transparent;
  border: 0;
  padding: 0;
  cursor: default;
  transition: transform 0.3s ease;
}

.postcard-inner {
  position: relative;
  background: #ffffff;
  padding: 1.75rem 1.5rem 1.75rem 1.5rem;
  box-shadow: 
    0 2px 8px rgba(0,0,0,0.08),
    0 8px 20px rgba(0,0,0,0.06);
  border-radius: 2px;
  transition: all 0.3s ease;
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  min-height: 120px;
}

.card.postcard:hover .postcard-inner {
  transform: translateY(-4px);
  box-shadow: 
    0 6px 16px rgba(0,0,0,0.12),
    0 12px 32px rgba(0,0,0,0.1);
}

/* Add slight rotation for organic postcard look */
.card.postcard:nth-child(1) .postcard-inner {
  transform: rotate(-0.5deg);
}
.card.postcard:nth-child(2) .postcard-inner {
  transform: rotate(0.5deg);
}
.card.postcard:nth-child(3) .postcard-inner {
  transform: rotate(-0.3deg);
}

.card.postcard:hover .postcard-inner {
  transform: translateY(-4px) rotate(0deg) !important;
}

/* Icon styling */
.icon-wrapper {
  flex-shrink: 0;
  width: 56px;
  height: 56px;
  background: linear-gradient(135deg, rgba(6,95,70,0.1), rgba(6,95,70,0.05));
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid rgba(6,95,70,0.15);
}

.icon-wrapper .material-icons { 
  font-size: 28px; 
  color: #065f46;
}

/* Content */
.card-content {
  flex: 1;
  padding-top: 0.25rem;
}

.card-content h3 { 
  margin: 0 0 0.5rem 0; 
  font-size: 1.1rem; 
  font-weight: 600;
  color: #065f46;
  letter-spacing: -0.01em;
}

.card-content p { 
  margin: 0; 
  color: rgba(0,0,0,0.7);
  line-height: 1.5;
  font-size: 0.95rem;
}

.card-content a { 
  color: inherit; 
  text-decoration: none;
  transition: color 0.2s ease;
}

.card-content a:hover {
  color: #065f46;
}

/* Decorative postcard stamp */
.postcard-stamp {
  position: absolute;
  top: 12px;
  right: 12px;
  width: 32px;
  height: 32px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.stamp-mark {
  width: 24px;
  height: 24px;
  border: 2px dashed rgba(6,95,70,0.25);
  border-radius: 4px;
  background: linear-gradient(135deg, rgba(6,95,70,0.05), rgba(6,95,70,0.02));
}

@media (min-width: 700px) {
  .cards { 
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
  }
}

@media (max-width: 700px) {
  .cards { gap: 1rem; }
  
  .postcard-inner {
    padding: 1.5rem 1.25rem;
    min-height: 100px;
  }
  
  .icon-wrapper {
    width: 48px;
    height: 48px;
  }
  
  .icon-wrapper .material-icons {
    font-size: 24px;
  }
  
  .card-content h3 {
    font-size: 1rem;
  }
  
  .card-content p {
    font-size: 0.9rem;
  }
}
</style>
