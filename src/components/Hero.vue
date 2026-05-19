<template>
  <section id="home" class="hero">
    <div class="hero-content">
      <h2 class="greeting">¡Hola y bienvenidos! Mi nombre es</h2>
      <h1 class="name text-gradient">Jhon Santana</h1>
      <h3 class="role">Desarrollador Frontend JavaScript</h3>
      <p class="description">
        Soy un apasionado de la tecnología en constante formación como desarrollador Frontend en JavaScript. 
        Creo experiencias web dinámicas, rápidas y altamente interactivas.
      </p>
      <div class="cta-buttons">
        <a href="#projects" class="btn-primary">Ver Proyectos</a>
        <a href="/CV.pdf" class="btn-secondary glass">Descargar CV</a>
      </div>
    </div>
    <div class="hero-image">
      <div class="glow-circle"></div>
      <img src="../assets/avatar.png" alt="Avatar Jhon Santana" class="avatar glass" />
    </div>
  </section>
</template>

<style lang="scss" scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-top: 8rem;

  .hero-content {
    flex: 1;
    max-width: 600px;

    .greeting {
      font-size: 1.5rem;
      color: #94a3b8;
      margin-bottom: 0.5rem;
    }

    .name {
      font-size: 4.5rem;
      line-height: 1.1;
      margin-bottom: 1rem;
    }

    .role {
      font-size: 2rem;
      color: #e2e8f0;
      margin-bottom: 1.5rem;
    }

    .description {
      color: #94a3b8;
      font-size: 1.1rem;
      margin-bottom: 2.5rem;
    }

    .cta-buttons {
      display: flex;
      gap: 1rem;

      .btn-secondary {
        display: inline-block;
        padding: 0.8rem 2rem;
        color: white;
        border-radius: 2rem;
        font-weight: 600;
        transition: background 0.3s ease;

        &:hover {
          background: rgba(255, 255, 255, 0.1);
        }
      }
    }
  }

  .hero-image {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;

    .glow-circle {
      position: absolute;
      width: 400px;
      height: 400px;
      background: radial-gradient(circle, rgba(139,92,246,0.3) 0%, rgba(59,130,246,0) 70%);
      z-index: -1;
      animation: pulse 4s infinite alternate;
    }

    .avatar {
      width: 350px;
      height: 350px;
      object-fit: cover;
      border-radius: 50%;
      padding: 1rem;
      border: 2px solid rgba(139, 92, 246, 0.3);
    }
  }

  @media (max-width: 992px) {
    flex-direction: column;
    text-align: center;
    gap: 4rem;

    .hero-content {
      .cta-buttons {
        justify-content: center;
      }
    }
  }
}

@keyframes pulse {
  0% { transform: scale(0.95); opacity: 0.5; }
  100% { transform: scale(1.05); opacity: 1; }
}
</style>
