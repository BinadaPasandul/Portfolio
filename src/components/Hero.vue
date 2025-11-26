<template>
  <section id="home" class="hero">
    <div class="hero-content">
      <div class="hero-text">
        <p class="greeting">Hello, I'm</p>
        <h1 class="name">
          <span class="name-line">Binada Pasandul</span>
        </h1>
        <p class="title">Full Stack Developer</p>
        <p class="description">
          I am a Full stack developer with strong backend developing skills, combining academic 
          knowledge and practical experience. I design scalable digital solutions and thrive in 
          dynamic environments. Passionate about innovation, having creative unique ideas, I 
          continuously learn new technologies and take on challenges to deliver impactful, high
          quality applications that meet user and business needs.
        </p>
        <div class="hero-buttons">
          <a href="#projects" class="btn btn-primary">View My Work</a>
          <a href="#contact" class="btn btn-secondary">Get In Touch</a>
        </div>
      </div>
      <div class="hero-image">
        <div class="image-placeholder">
          <img :src="binadaPic" alt="Binada Pasandul" class="profile-image" />
        </div>
      </div>
    </div>
    <div class="scroll-indicator">
      <span></span>
    </div>
  </section>
</template>

<script setup lang="ts">
import binadaPic from '../assets/binada.png'
</script>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 120px 2rem 2rem;
  background: linear-gradient(135deg, #0f0c29 0%, #302b63 50%, #24243e 100%);
  position: relative;
  overflow: hidden;
}

.hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: radial-gradient(circle at 20% 50%, rgba(102, 126, 234, 0.1) 0%, transparent 50%),
              radial-gradient(circle at 80% 80%, rgba(118, 75, 162, 0.1) 0%, transparent 50%);
  pointer-events: none;
}

.hero-content {
  max-width: 1200px;
  width: 100%;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  z-index: 1;
  position: relative;
}

.hero-text {
  animation: fadeInUp 0.8s ease;
}

.greeting {
  font-size: 1.2rem;
  color: #667eea;
  margin-bottom: 0.5rem;
  font-weight: 500;
}

.name {
  font-size: 4rem;
  font-weight: 700;
  color: #fff;
  margin: 0.5rem 0;
  line-height: 1.2;
}

.name-line {
  display: block;
  background: linear-gradient(135deg, #fff 0%, #667eea 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.title {
  font-size: 1.5rem;
  color: #b0b0b0;
  margin: 1rem 0;
}

.description {
  font-size: 1.1rem;
  color: #d0d0d0;
  line-height: 1.8;
  margin: 1.5rem 0 2rem;
  max-width: 500px;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.btn {
  padding: 1rem 2rem;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
  display: inline-block;
}

.btn-primary {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: #fff;
  box-shadow: 0 4px 15px rgba(102, 126, 234, 0.4);
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(102, 126, 234, 0.6);
}

.btn-secondary {
  background: transparent;
  color: #fff;
  border: 2px solid #667eea;
}

.btn-secondary:hover {
  background: rgba(102, 126, 234, 0.1);
  transform: translateY(-2px);
}

.hero-image {
  display: flex;
  justify-content: center;
  align-items: center;
  animation: fadeIn 1s ease;
}

.image-placeholder {
  width: 400px;
  height: 400px;
  border-radius: 50%;
  position: relative;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 20px 60px rgba(102, 126, 234, 0.3);
  animation: float 6s ease-in-out infinite;
  padding: 10px;
  overflow: hidden;
}

.profile-image {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
  border: 4px solid rgba(255, 255, 255, 0.2);
}

.gradient-circle {
  width: 90%;
  height: 90%;
  border-radius: 50%;
  background: linear-gradient(135deg, #0f0c29 0%, #302b63 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 4rem;
  color: #667eea;
}

.scroll-indicator {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  animation: bounce 2s infinite;
}

.scroll-indicator span {
  display: block;
  width: 30px;
  height: 50px;
  border: 2px solid #667eea;
  border-radius: 25px;
  position: relative;
}

.scroll-indicator span::before {
  content: '';
  position: absolute;
  top: 10px;
  left: 50%;
  transform: translateX(-50%);
  width: 6px;
  height: 6px;
  background: #667eea;
  border-radius: 50%;
  animation: scroll 2s infinite;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes float {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
}

@keyframes bounce {
  0%, 100% {
    transform: translateX(-50%) translateY(0);
  }
  50% {
    transform: translateX(-50%) translateY(-10px);
  }
}

@keyframes scroll {
  0% {
    opacity: 1;
    top: 10px;
  }
  100% {
    opacity: 0;
    top: 30px;
  }
}

@media (max-width: 968px) {
  .hero-content {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 3rem;
  }

  .hero-text {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .description {
    max-width: 100%;
  }

  .name {
    font-size: 3rem;
  }

  .image-placeholder {
    width: 300px;
    height: 300px;
  }
}

@media (max-width: 480px) {
  .name {
    font-size: 2.5rem;
  }

  .image-placeholder {
    width: 250px;
    height: 250px;
  }

  .btn {
    padding: 0.8rem 1.5rem;
    font-size: 0.9rem;
  }
}
</style>

