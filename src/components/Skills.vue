<template>
  <section id="skills" class="skills">
    <h2 class="section-title">Habilidades</h2>
    <div class="skills-wrapper">
      
      <!-- Hard Skills - Animated Bars -->
      <div class="skill-category hard-skills glass">
        <h3>Hard Skills</h3>
        <div class="skill-bars">
          <div class="skill-bar-container" v-for="skill in hardSkills" :key="skill.name">
            <div class="skill-info">
              <span class="skill-name">{{ skill.name }}</span>
              <span class="skill-percent">{{ skill.level }}%</span>
            </div>
            <div class="progress-bg">
              <div class="progress-fill text-gradient-bg" :style="{ width: skill.level + '%' }"></div>
            </div>
          </div>
        </div>
      </div>

      <!-- Soft Skills - Floating Cards -->
      <div class="skill-category soft-skills glass">
        <h3>Soft Skills</h3>
        <div class="floating-cards">
          <div class="soft-card" v-for="(skill, index) in softSkills" :key="index" :style="{ animationDelay: `${index * 0.2}s` }">
            <div class="card-inner">
              <span class="skill-icon">{{ skill.icon }}</span>
              <span class="skill-text">{{ skill.name }}</span>
            </div>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
const hardSkills = [
  { name: 'JavaScript', level: 90 },
  { name: 'Angular', level: 85 },
  { name: 'Vue 3', level: 80 },
  { name: 'React', level: 75 },
  { name: 'NodeJs', level: 70 },
  { name: 'HTML5 & CSS3', level: 95 },
  { name: 'Sass/Less/Stylus', level: 85 },
  { name: 'Git/GitHub', level: 80 }
];

const softSkills = [
  { name: 'Responsable', icon: '🎯' },
  { name: 'Trabajo en equipo', icon: '🤝' },
  { name: 'Manejo del tiempo', icon: '⏳' },
  { name: 'Autodidacta', icon: '📚' },
  { name: 'Pensamiento crítico', icon: '🧠' },
  { name: 'Resolución de problemas', icon: '🛠️' }
];
</script>

<style lang="scss" scoped>
.skills-wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;

  @media (max-width: 992px) {
    grid-template-columns: 1fr;
  }

  .skill-category {
    padding: 2.5rem;
    display: flex;
    flex-direction: column;
    height: 100%;
    
    h3 {
      font-size: 1.8rem;
      margin-bottom: 2.5rem;
      color: #e2e8f0;
      text-align: center;
      position: relative;
      display: inline-block;
      left: 50%;
      transform: translateX(-50%);

      &::after {
        content: '';
        position: absolute;
        bottom: -10px;
        left: 0;
        width: 100%;
        height: 2px;
        background: linear-gradient(90deg, #3b82f6, #8b5cf6);
      }
    }
  }

  /* Hard Skills Bars */
  .skill-bars {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;

    .skill-bar-container {
      width: 100%;

      .skill-info {
        display: flex;
        justify-content: space-between;
        margin-bottom: 0.5rem;
        font-weight: 500;
        
        .skill-name {
          color: #f8fafc;
        }
        
        .skill-percent {
          color: #a78bfa;
        }
      }

      .progress-bg {
        width: 100%;
        height: 10px;
        background: rgba(255, 255, 255, 0.1);
        border-radius: 10px;
        overflow: hidden;

        .progress-fill {
          height: 100%;
          border-radius: 10px;
          background: linear-gradient(90deg, #3b82f6, #8b5cf6);
          box-shadow: 0 0 10px rgba(139, 92, 246, 0.5);
          width: 0; /* Fallback */
          animation: fillBar 1.5s ease-out forwards;
        }
      }
    }
  }

  /* Soft Skills Cards */
  .floating-cards {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    grid-template-rows: repeat(3, auto);
    gap: 1.5rem;
    flex: 1;
    align-content: space-evenly;
    justify-content: center;

    /* Pyramid shape layout */
    .soft-card:nth-child(1) { grid-column: 3 / span 2; grid-row: 1; }
    .soft-card:nth-child(2) { grid-column: 2 / span 2; grid-row: 2; }
    .soft-card:nth-child(3) { grid-column: 4 / span 2; grid-row: 2; }
    .soft-card:nth-child(4) { grid-column: 1 / span 2; grid-row: 3; }
    .soft-card:nth-child(5) { grid-column: 3 / span 2; grid-row: 3; }
    .soft-card:nth-child(6) { grid-column: 5 / span 2; grid-row: 3; }

    @media (max-width: 600px) {
      grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
      .soft-card:nth-child(n) {
        grid-column: auto;
        grid-row: auto;
      }
    }

    .soft-card {
      background: rgba(30, 41, 59, 0.4);
      border: 1px solid rgba(139, 92, 246, 0.2);
      border-radius: 1rem;
      padding: 1.5rem 1rem;
      text-align: center;
      transition: all 0.3s ease;
      animation: float 4s ease-in-out infinite;

      &:hover {
        transform: translateY(-10px) scale(1.05);
        box-shadow: 0 10px 20px rgba(59, 130, 246, 0.2), 0 0 15px rgba(139, 92, 246, 0.3);
        border-color: rgba(59, 130, 246, 0.5);
        background: rgba(30, 41, 59, 0.8);
      }

      .card-inner {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 0.8rem;

        .skill-icon {
          font-size: 2.5rem;
          filter: drop-shadow(0 0 5px rgba(139, 92, 246, 0.4));
        }

        .skill-text {
          font-size: 0.9rem;
          color: #cbd5e1;
          font-weight: 500;
          line-height: 1.2;
        }
      }
    }
  }
}

@keyframes fillBar {
  from { width: 0; }
}

@keyframes float {
  0% { transform: translateY(0px); }
  50% { transform: translateY(-10px); }
  100% { transform: translateY(0px); }
}
</style>
