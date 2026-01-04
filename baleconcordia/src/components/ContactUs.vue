<template>
  <section class="contact-us">
    <h2>Contact Us</h2>
    <p class="lead">Reach out for bookings, questions, or collaborations.</p>

    <div class="cards">
      <div class="card">
        <span class="material-icons">location_on</span>
        <div>
          <h3>Address</h3>
          <p>San Francisco Concepcion, Tarlac</p>
        </div>
      </div>

      <div class="card">
        <span class="material-icons">phone</span>
        <div>
          <h3>Phone</h3>
          <p><a href="tel:00000000000">00000000000</a></p>
        </div>
      </div>

      <div class="card">
        <span class="material-icons">email</span>
        <div>
          <h3>Email</h3>
          <p><a href="mailto:baleconcordia@gmail.com">baleconcordia@gmail.com</a></p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.contact-us { margin: 2rem 0; }
.contact-us h2 { margin: 0 0 0.25rem 0; font-size: 1.4rem; font-weight: 700; }
.contact-us .lead { margin: 0 0 1rem 0; color: rgba(0,0,0,0.65) }
.cards { display: grid; grid-template-columns: 1fr; gap: 0.75rem }
.card { display: flex; gap: 0.75rem; align-items: center; padding: 1rem; background: white; border-radius: 8px; box-shadow: 0 6px 18px rgba(18,23,28,0.04) }
.card .material-icons { font-size: 28px; color: #065f46 }
.card h3 { margin: 0; font-size: 1rem; font-weight: 700; }
.card p { margin: 0.2rem 0 0 0; color: rgba(0,0,0,0.7) }
.card a { color: inherit; text-decoration: none }

@media (min-width: 700px) {
  .cards { grid-template-columns: repeat(3, 1fr) }
}
</style>
