<template>
  <section id="projects" class="projects">
    <h2 class="section-title">Mis Proyectos</h2>
    
    <div class="accordion-container">
      <div 
        class="accordion-item glass" 
        v-for="(project, index) in projects" 
        :key="index"
      >
        <div class="item-number">0{{ index + 1 }}</div>
        
        <div class="item-title">
          <h3>{{ project.title }}</h3>
        </div>

        <div class="item-content">
          <div class="content-inner">
            <p class="tech text-gradient">{{ project.tech }}</p>
            <p class="desc">{{ project.description }}</p>
            <a :href="project.demo" target="_blank" class="btn-demo">
              Ver Demo 
              <span class="arrow">→</span>
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { projects } from '../data/projects.js';
</script>

<style lang="scss" scoped>
.accordion-container {
  display: flex;
  flex-direction: row;
  width: 100%;
  height: 450px;
  gap: 1rem;
  
  @media (max-width: 992px) {
    flex-direction: column;
    height: auto;
    min-height: 600px;
  }

  .accordion-item {
    flex: 1;
    position: relative;
    overflow: hidden;
    transition: all 0.6s cubic-bezier(0.25, 1, 0.5, 1);
    cursor: pointer;
    border-radius: 2rem;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 2.5rem 1.5rem;
    background: rgba(30, 41, 59, 0.4);
    
    &:hover {
      flex: 4;
      background: rgba(30, 41, 59, 0.85);
      box-shadow: 0 0 30px rgba(59, 130, 246, 0.2);
      border-color: rgba(139, 92, 246, 0.5);

      .item-content {
        opacity: 1;
        transform: translateY(0);
        visibility: visible;
        transition-delay: 0.3s;
      }
      
      .item-title h3 {
        transform: rotate(0deg);
        writing-mode: horizontal-tb;
        margin-bottom: 1.5rem;
        background: linear-gradient(90deg, #3b82f6, #8b5cf6);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
      }

      .item-number {
        opacity: 0.1;
        transform: scale(1.5) translate(-10%, 10%);
      }
    }
  }
}

.item-number {
  position: absolute;
  top: -1rem;
  right: 0;
  font-size: 8rem;
  font-weight: 900;
  color: rgba(255, 255, 255, 0.03);
  transition: all 0.6s ease;
  z-index: 0;
  pointer-events: none;
}

.item-title {
  z-index: 1;
  h3 {
    font-size: 2rem;
    color: #e2e8f0;
    margin: 0;
    transition: all 0.5s ease;
    white-space: nowrap;
    
    @media (min-width: 993px) {
      writing-mode: vertical-rl;
      transform: rotate(180deg);
    }
  }
}

.item-content {
  opacity: 0;
  visibility: hidden;
  transform: translateY(30px);
  transition: all 0.4s ease;
  z-index: 1;
  
  .content-inner {
    display: flex;
    flex-direction: column;
    gap: 0.8rem;
    /* Evita que el contenido colapse horizontalmente antes de la animación */
    min-width: 250px;
  }
  
  .tech {
    font-weight: 700;
    font-size: 0.9rem;
    letter-spacing: 2px;
    text-transform: uppercase;
  }
  
  .desc {
    color: #cbd5e1;
    font-size: 1.05rem;
    line-height: 1.6;
    margin-bottom: 1.5rem;
  }
  
  .btn-demo {
    display: inline-flex;
    align-items: center;
    gap: 0.8rem;
    padding: 0.8rem 1.8rem;
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.2);
    border-radius: 2rem;
    color: white;
    font-weight: 600;
    width: fit-content;
    transition: all 0.3s ease;
    backdrop-filter: blur(5px);
    
    .arrow {
      transition: transform 0.3s ease;
    }
    
    &:hover {
      background: linear-gradient(90deg, #3b82f6, #8b5cf6);
      border-color: transparent;
      box-shadow: 0 0 15px rgba(59, 130, 246, 0.5);
      
      .arrow {
        transform: translateX(8px);
      }
    }
  }
}
</style>
