<template>
  <footer class="site-footer">
    <div class="footer-content">
      <div class="footer-grid">
        <!-- Brand Section -->
        <div class="footer-brand">
          <div class="brand-icon">
            <span class="material-icons">nature</span>
          </div>
          <div class="brand-text">
            <strong>Bale Concordia</strong>
            <span class="subtitle">Cabins & Resort</span>
          </div>
        </div>

        <!-- Quick Links -->
        <div class="footer-section">
          <h3>Quick Links</h3>
          <ul class="footer-links">
            <li><a href="#photo-gallery" @click="scrollToSection">Gallery</a></li>
            <li><a href="#contact-us" @click="scrollToSection">Contact</a></li>
            <li><a href="#location" @click="scrollToSection">Location</a></li>
          </ul>
        </div>

        <!-- Contact Info -->
        <div class="footer-section">
          <h3>Get in Touch</h3>
          <ul class="footer-info">
            <li>
              <span class="material-icons">place</span>
              <span>Concepcion, Tarlac</span>
            </li>
            <li>
              <span class="material-icons">email</span>
              <span>baleconcordia@gmail.com</span>
            </li>
          </ul>
        </div>
      </div>

      <!-- Divider -->
      <div class="footer-divider"></div>

      <!-- Copyright Section -->
      <div class="footer-bottom">
        <div class="copyright">© {{ year }} Bale Concordia. All rights reserved.</div>
        <div class="footer-accent"></div>
      </div>
    </div>
  </footer>
</template>

<script setup>
const year = new Date().getFullYear()

function scrollToSection(event) {
  event.preventDefault()
  const targetId = event.currentTarget.getAttribute('href').substring(1)
  const targetElement = document.getElementById(targetId)
  
  if (targetElement) {
    targetElement.scrollIntoView({
      behavior: 'smooth',
      block: 'start'
    })
  }
}
</script>

<style scoped>
.site-footer {
  background: linear-gradient(135deg, #065f46 0%, #0a7a56 100%);
  color: #ffffff;
  margin-top: 4rem;
  position: relative;
  overflow: hidden;
}

/* Decorative pattern overlay */
.site-footer::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image: 
    radial-gradient(circle at 20% 50%, rgba(255,255,255,0.03) 0%, transparent 50%),
    radial-gradient(circle at 80% 80%, rgba(255,255,255,0.02) 0%, transparent 50%);
  pointer-events: none;
}

.footer-content {
  position: relative;
  padding: 3rem 2rem 2rem 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.footer-grid {
  display: grid;
  grid-template-columns: 1.5fr 1fr 1fr;
  gap: 3rem;
  margin-bottom: 2.5rem;
}

/* Brand Section */
.footer-brand {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.brand-icon {
  width: 56px;
  height: 56px;
  background: rgba(255,255,255,0.15);
  backdrop-filter: blur(10px);
  border-radius: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid rgba(255,255,255,0.2);
  flex-shrink: 0;
}

.brand-icon .material-icons {
  font-size: 32px;
  color: #ffffff;
}

.brand-text {
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
}

.brand-text strong {
  font-size: 1.5rem;
  font-weight: 700;
  color: #ffffff;
  letter-spacing: -0.02em;
}

.brand-text .subtitle {
  font-size: 0.9rem;
  color: rgba(255,255,255,0.8);
  text-transform: uppercase;
  letter-spacing: 0.05em;
  font-weight: 500;
}

/* Footer Sections */
.footer-section h3 {
  font-size: 1rem;
  font-weight: 600;
  margin: 0 0 1rem 0;
  color: rgba(255,255,255,0.95);
  letter-spacing: -0.01em;
}

.footer-links,
.footer-info {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.footer-links a {
  color: rgba(255,255,255,0.8);
  text-decoration: none;
  font-size: 0.95rem;
  transition: all 0.2s ease;
  display: inline-block;
  cursor: pointer;
}

.footer-links a:hover {
  color: #ffffff;
  transform: translateX(4px);
}

.footer-info li {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: rgba(255,255,255,0.8);
  font-size: 0.9rem;
}

.footer-info .material-icons {
  font-size: 18px;
  color: rgba(255,255,255,0.7);
}

/* Divider */
.footer-divider {
  height: 1px;
  background: linear-gradient(
    90deg,
    transparent 0%,
    rgba(255,255,255,0.2) 50%,
    transparent 100%
  );
  margin: 2rem 0 1.5rem 0;
}

/* Bottom Section */
.footer-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
}

.copyright {
  font-size: 0.9rem;
  color: rgba(255,255,255,0.7);
  font-weight: 400;
}

.footer-accent {
  width: 80px;
  height: 3px;
  background: linear-gradient(90deg, rgba(255,255,255,0.4), transparent);
  border-radius: 2px;
}

/* Responsive Design */
@media (max-width: 900px) {
  .footer-grid {
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
  }
  
  .footer-brand {
    grid-column: 1 / -1;
  }
}

@media (max-width: 600px) {
  .footer-content {
    padding: 2.5rem 1.5rem 1.5rem 1.5rem;
  }
  
  .footer-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .footer-brand {
    grid-column: auto;
  }
  
  .brand-icon {
    width: 48px;
    height: 48px;
  }
  
  .brand-icon .material-icons {
    font-size: 28px;
  }
  
  .brand-text strong {
    font-size: 1.3rem;
  }
  
  .footer-bottom {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .footer-accent {
    width: 60px;
  }
}
</style>
