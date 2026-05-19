<template>
  <section id="about" class="about">
    <h2 class="section-title">Sobre mí</h2>
    <div class="about-container glass">
      <div class="text-content">
        <p>
          Mi formación actual como ingeniero electrónico, en la que cada día me capacito más tanto personal como profesionalmente, ha forjado mi fuerte interés por la tecnología. Esto me ha impulsado a desarrollar habilidades como Frontend Developer.
        </p>
        <p>
          Mi objetivo a largo plazo es seguir dominando nuevas herramientas y consolidarme como un Frontend Developer avanzado. Próximamente, quiero expandir mis conocimientos hacia el desarrollo de aplicaciones móviles multiplataforma con tecnologías como Ionic y Flutter.
        </p>
      </div>
      <div class="stats">
        <div class="stat-item">
          <span class="number text-gradient">+2</span>
          <span class="label">Años de Estudio</span>
        </div>
        <div class="stat-item">
          <span class="number text-gradient">+{{ projects.length }}</span>
          <span class="label">Proyectos Realizados</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { projects } from '../data/projects.js';
</script>

<style lang="scss" scoped>
.about-container {
  display: flex;
  gap: 3rem;
  padding: 3rem;
  align-items: center;

  .text-content {
    flex: 2;
    p {
      color: #cbd5e1;
      font-size: 1.1rem;
      margin-bottom: 1.5rem;
      
      &:last-child {
        margin-bottom: 0;
      }
    }
  }

  .stats {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 2rem;

    .stat-item {
      text-align: center;
      
      .number {
        display: block;
        font-size: 3.5rem;
        font-weight: 800;
        line-height: 1;
        margin-bottom: 0.5rem;
      }
      
      .label {
        color: #94a3b8;
        font-weight: 500;
        text-transform: uppercase;
        letter-spacing: 1px;
        font-size: 0.9rem;
      }
    }
  }

  @media (max-width: 768px) {
    flex-direction: column;
    padding: 2rem;
  }
}
</style>
