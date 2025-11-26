<template>
  <section id="about" class="about">
    <div class="container">
      <h2 class="section-title">
        <span class="title-number">01.</span>
        About Me
      </h2>
      <div class="about-content">
        <div class="about-text">
          <p>
            Hello! I'm a passionate developer with a strong interest in building
            innovative web applications. I'm currently seeking internship
            opportunities to expand my skills and work on meaningful projects.
          </p>
          <p>
            My journey in software development has been driven by curiosity and
            a desire to solve real-world problems. I enjoy working with modern
            technologies and am always eager to learn new frameworks and tools.
          </p>
          <p>Here are a few technologies I've been working with recently:</p>
          <ul class="tech-list">
            <li>JavaScript (ES6+)</li>
            <li>TypeScript</li>
            <li>Vue.js</li>
            <li>React</li>
            <li>Node.js</li>
            <li>Python</li>
            <li>Git & GitHub</li>
            <li>RESTful APIs</li>
          </ul>
        </div>
        <div class="about-image">
          <div class="image-wrapper">
            <div class="image-border"></div>
            <div class="image-content">
              <img :src="binadaPic" alt="Binada Pasandul" class="about-profile-image" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import binadaPic from '../assets/binada.png'
</script>

<style scoped>
.about {
  padding: 100px 2rem;
  background: #0f0c29;
  min-height: 100vh;
  display: flex;
  align-items: center;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  width: 100%;
}

.section-title {
  font-size: 2.5rem;
  color: #fff;
  margin-bottom: 3rem;
  display: flex;
  align-items: center;
  gap: 1rem;
  font-weight: 700;
}

.title-number {
  color: #667eea;
  font-family: 'Courier New', monospace;
  font-size: 1.5rem;
}

.about-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 4rem;
  align-items: start;
}

.about-text {
  color: #d0d0d0;
  line-height: 1.8;
  font-size: 1.1rem;
}

.about-text p {
  margin-bottom: 1.5rem;
}

.tech-list {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 0.5rem;
  list-style: none;
  padding: 0;
  margin-top: 1rem;
}

.tech-list li {
  position: relative;
  padding-left: 1.5rem;
  color: #b0b0b0;
}

.tech-list li::before {
  content: '▹';
  position: absolute;
  left: 0;
  color: #667eea;
}

.about-image {
  display: flex;
  justify-content: center;
  align-items: center;
}

.image-wrapper {
  position: relative;
  width: 300px;
  height: 300px;
}

.image-border {
  position: absolute;
  top: 20px;
  left: 20px;
  width: 100%;
  height: 100%;
  border: 2px solid #667eea;
  border-radius: 4px;
  transition: transform 0.3s ease;
}

.image-wrapper:hover .image-border {
  transform: translate(-10px, -10px);
}

.image-content {
  position: relative;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
  border-radius: 4px;
  overflow: hidden;
  z-index: 1;
}

.about-profile-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 4px;
}

.placeholder-content {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #667eea;
  font-size: 1.2rem;
  background: rgba(102, 126, 234, 0.1);
}

@media (max-width: 968px) {
  .about-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }

  .about-image {
    order: -1;
  }

  .image-wrapper {
    width: 250px;
    height: 250px;
  }
}
</style>

