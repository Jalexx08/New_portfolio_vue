<template>
  <nav class="navbar glass">
    <div class="logo">
      <div class="type-writer">
        <span class="text-gradient">JassDev</span>
      </div>
      <span class="cursor">_</span>
    </div>
    <ul class="nav-links">
      <li>
        <a href="#home">
          <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="git-icon"><line x1="6" y1="3" x2="6" y2="15"></line><circle cx="18" cy="6" r="3"></circle><circle cx="6" cy="18" r="3"></circle><path d="M18 9a9 9 0 0 1-9 9"></path></svg>
          main
        </a>
      </li>
      <li>
        <a href="#about">
          <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="git-icon"><line x1="6" y1="3" x2="6" y2="15"></line><circle cx="18" cy="6" r="3"></circle><circle cx="6" cy="18" r="3"></circle><path d="M18 9a9 9 0 0 1-9 9"></path></svg>
          feature/sobre-mi
        </a>
      </li>
      <li>
        <a href="#skills">
          <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="git-icon"><line x1="6" y1="3" x2="6" y2="15"></line><circle cx="18" cy="6" r="3"></circle><circle cx="6" cy="18" r="3"></circle><path d="M18 9a9 9 0 0 1-9 9"></path></svg>
          core/habilidades
        </a>
      </li>
      <li>
        <a href="#projects">
          <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="git-icon"><line x1="6" y1="3" x2="6" y2="15"></line><circle cx="18" cy="6" r="3"></circle><circle cx="6" cy="18" r="3"></circle><path d="M18 9a9 9 0 0 1-9 9"></path></svg>
          feat/proyectos
        </a>
      </li>
      <li>
        <a href="#contact">
          <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="git-icon"><line x1="6" y1="3" x2="6" y2="15"></line><circle cx="18" cy="6" r="3"></circle><circle cx="6" cy="18" r="3"></circle><path d="M18 9a9 9 0 0 1-9 9"></path></svg>
          ping/contacto
        </a>
      </li>
    </ul>
  </nav>
</template>

<script setup>
// Lógica para responsive nav
</script>

<style lang="scss" scoped>
.navbar {
  position: fixed;
  top: 1rem;
  left: 50%;
  transform: translateX(-50%);
  width: 90%;
  max-width: 1200px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  z-index: 1000;
  border-radius: 3rem;

  .logo {
    font-family: 'Fira Code', monospace;
    font-size: 1.6rem;
    font-weight: 700;
    letter-spacing: -1px;
    display: flex;
    align-items: center;

    .type-writer {
      display: inline-block;
      overflow: hidden;
      white-space: nowrap;
      width: 0;
      animation: typingLoop 5s steps(7, end) infinite;
    }

    .cursor {
      color: #8b5cf6;
      animation: blink 1s step-start infinite;
      margin-left: 2px;
    }
  }

  @keyframes typingLoop {
    0%, 10% { width: 0; }
    30%, 70% { width: 7ch; }
    90%, 100% { width: 0; }
  }

  @keyframes blink {
    50% { opacity: 0; }
  }

  .nav-links {
    display: flex;
    gap: 1.5rem;

    a {
      font-family: 'Fira Code', monospace;
      font-weight: 500;
      color: #94a3b8;
      transition: all 0.3s ease;
      font-size: 0.9rem;
      display: flex;
      align-items: center;
      gap: 0.4rem;
      padding: 0.4rem 0.6rem;
      border-radius: 0.5rem;

      .git-icon {
        color: #64748b;
        transition: all 0.3s ease;
      }

      &:hover {
        color: #f8fafc;
        background: rgba(139, 92, 246, 0.1);

        .git-icon {
          color: #f14e32; /* Git official orange/red color */
          transform: scale(1.1);
        }
      }
    }
  }

  @media (max-width: 768px) {
    .nav-links {
      display: none; // Un menú hamburguesa podría ir aquí después
    }
  }
}
</style>
