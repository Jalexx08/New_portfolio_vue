<template>
  <section id="contact" class="contact">
    <h2 class="section-title">Contáctame</h2>
    <div class="contact-content glass">
      <p class="cta-text">¿Tienes algún proyecto en mente o simplemente quieres saludar?</p>
      
      <div class="contact-info">
        <a href="mailto:jhon1208@gmail.com" class="contact-link">
          <span class="icon">✉️</span>
          jhon1208@gmail.com
        </a>
        <a href="tel:+573176876280" class="contact-link">
          <span class="icon">📱</span>
          +57 3176876280
        </a>
      </div>

      <div class="social-links">
        <a href="https://github.com/jalexx08" target="_blank" class="social-btn">GitHub</a>
        <a href="https://www.linkedin.com/in/jhonalexsantana/" target="_blank" class="social-btn">LinkedIn</a>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.contact-content {
  max-width: 800px;
  margin: 0 auto;
  padding: 4rem;
  text-align: center;
  
  .cta-text {
    font-size: 1.2rem;
    color: #e2e8f0;
    margin-bottom: 3rem;
  }

  .contact-info {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    align-items: center;
    margin-bottom: 3rem;

    .contact-link {
      display: flex;
      align-items: center;
      gap: 1rem;
      font-size: 1.1rem;
      color: #94a3b8;
      transition: color 0.3s ease;

      .icon {
        font-size: 1.5rem;
      }

      &:hover {
        color: #3b82f6;
      }
    }
  }

  .social-links {
    display: flex;
    justify-content: center;
    gap: 1.5rem;

    .social-btn {
      padding: 0.8rem 2rem;
      border-radius: 2rem;
      border: 1px solid rgba(255, 255, 255, 0.2);
      transition: all 0.3s ease;

      &:hover {
        background: rgba(255, 255, 255, 0.1);
        border-color: #8b5cf6;
        color: #8b5cf6;
      }
    }
  }

  @media (max-width: 768px) {
    padding: 2rem;
  }
}
</style>
