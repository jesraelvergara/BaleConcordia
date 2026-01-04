<template>
  <section class="contact-social">
    <h2>Follow us</h2>
    <p class="lead">Stay connected on social media.</p>

    <div class="social-links">
      <a class="social-link" href="https://www.facebook.com/baleconcordia1" target="_blank" rel="noopener" aria-label="Facebook page">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden>
          <path d="M22 12.07C22 6.48 17.52 2 11.93 2 6.34 2 1.86 6.48 1.86 12.07c0 4.99 3.66 9.13 8.44 9.92v-7.03H8.62V12.1h3.68V9.84c0-3.64 2.17-5.64 5.49-5.64 1.59 0 3.26.28 3.26.28v3.58h-1.83c-1.8 0-2.36 1.12-2.36 2.27v2.12h4.02l-.64 3.86h-3.38v7.03c4.78-.79 8.44-4.93 8.44-9.92z" fill="#1877F2"/>
        </svg>
        <span>Facebook</span>
      </a>

      <a class="social-link" href="https://www.instagram.com/baleconcordia" target="_blank" rel="noopener" aria-label="Instagram page">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden>
          <path d="M7 2h10a5 5 0 0 1 5 5v10a5 5 0 0 1-5 5H7a5 5 0 0 1-5-5V7a5 5 0 0 1 5-5z" stroke="#E1306C" stroke-width="1.5" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M12 8.5a3.5 3.5 0 1 0 0 7 3.5 3.5 0 0 0 0-7z" stroke="#E1306C" stroke-width="1.5" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M17.5 6.5h.01" stroke="#E1306C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
        <span>Instagram</span>
      </a>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.contact-social { margin: 2rem 0 }
.contact-social h2 { margin: 0 0 0.25rem 0; font-size: 1.2rem }
.contact-social .lead { margin: 0 0 0.75rem 0; color: rgba(0,0,0,0.65) }
.social-links { display:flex; gap: 0.75rem; align-items: center }
.social-link { display: inline-flex; gap: 8px; align-items: center; padding: 0.6rem 0.9rem; background: white; border-radius: 8px; box-shadow: 0 6px 18px rgba(18,23,28,0.04); color: inherit; text-decoration: none }
.social-link svg { display:block }
.social-link span { font-weight: 600 }
</style>
