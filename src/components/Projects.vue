<template>
  <section id="projects" class="projects">
    <div class="container">
      <h2 class="section-title">
        <span class="title-number">03.</span>
        Personal Projects
      </h2>

      <div class="projects-grid">
        <div
          v-for="project in projects"
          :key="project.id"
          class="project-card"
        >
          <div class="project-image">
            <img
              v-if="project.image"
              :src="project.image"
              alt="Project Image"
              class="img-fill"
            />
            <div v-else class="image-placeholder">
              <span>Project Image</span>
            </div>

            <!-- Overlay -->
            <div class="project-overlay">
              <!-- GitHub Button -->
              <a
                :href="project.github"
                target="_blank"
                class="project-link"
                title="View on GitHub"
              >
                <svg viewBox="0 0 24 24" fill="currentColor">
                  <path
                    d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
                  />
                </svg>
              </a>

              <!-- Live Demo Button -->
              <a
                v-if="project.live"
                :href="project.live"
                target="_blank"
                class="project-link"
                title="View Live Demo"
              >
                <svg viewBox="0 0 24 24" fill="currentColor">
                  <path
                    d="M12 2a10 10 0 100 20 10 10 0 000-20zm-1 14v-4H7l6-6v4h4l-6 6z"
                  />
                </svg>
              </a>
            </div>
          </div>

          <div class="project-content">
            <h3 class="project-title">{{ project.title }}</h3>
            <p class="project-description">{{ project.description }}</p>

            <div class="project-tech">
              <span
                v-for="tech in project.technologies"
                :key="tech"
                class="tech-tag"
              >
                {{ tech }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import snazzyPic from '@/assets/snazzy2.jpeg'
import bidifyPic from '@/assets/bidify.jpeg'
import pulsePic from '@/assets/pulse1.jpeg'
import travellaPic from '@/assets/travella1.jpeg'
import wedinPic from '@/assets/wedin.jpeg'
import portfolioPic from '@/assets/portfolio1.jpeg'
import bookLedgerPic from '@/assets/libra.jpg' // <-- add image

interface Project {
  id: number
  title: string
  description: string
  technologies: string[]
  github: string
  live?: string
  image?: string
}

const projects: Project[] = [
  {
    id: 1,
    title: 'Snazzy – The Smart Shoe Store',
    description:
      'A full-stack e-commerce platform with authentication, live chat, Stripe payments and admin dashboards.',
    technologies: ['React.js', 'Node.js', 'MongoDB', 'Express'],
    github: 'https://github.com/BinadaPasandul/snazzy/tree/new',
    image: snazzyPic
  },
  {
    id: 2,
    title: 'Bidify – Online Bidding System',
    description:
      'A full-stack auction system where sellers list items and buyers place bids with delivery support.',
    technologies: ['Java', 'JSP/Servlet', 'SQL', 'Tomcat'],
    github: 'https://github.com/BinadaPasandul/Bidify',
    image: bidifyPic
  },
    {
    id: 6,
    title: 'Book Ledger',
    description:
      'A full-stack Library Management System with JWT authentication, CRUD operations and role-based access.',
    technologies: ['React', 'TypeScript', '.NET Core Web API', 'SQLite', 'JWT'],
    github: 'https://github.com/BinadaPasandul/LibrarySystem',
    image: bookLedgerPic
  },
  {
    id: 3,
    title: 'Pulse',
    description:
      'A wellness tracking mobile app with habit tracking, water intake and gym routines.',
    technologies: ['Kotlin', 'Shared Preferences', 'Figma'],
    github: 'https://github.com/BinadaPasandul/Pulse-Mobile-app',
    image: pulsePic
  },
  
  {
    id: 4,
    title: 'Travella',
    description:
      'A mobile app to store travel memories with journals, photos and custom entries.',
    technologies: ['Kotlin', 'Shared Preferences', 'Figma'],
    github: 'https://github.com/BinadaPasandul/Travella',
    image: travellaPic
  },
  {
    id: 5,
    title: 'Wed.In',
    description:
      'A wedding hotel reservation system with booking, hotel listing and admin management features.',
    technologies: ['HTML', 'CSS', 'JavaScript', 'PHP'],
    github: 'https://github.com',
    image: wedinPic
  },

  {
    id: 7,
    title: 'Portfolio Website',
    description:
      'A modern personal portfolio showcasing projects, skills and contact details.',
    technologies: ['Vue.js', 'TypeScript', 'Vite', 'CSS3'],
    github: 'https://github.com/BinadaPasandul/Portfolio',
    live: 'https://binadapasandul-portfolio.vercel.app/',
    image: portfolioPic
  }
]
</script>

<style scoped>
.projects {
  padding: 100px 2rem;
  background: #0f0c29;
  min-height: 100vh;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
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

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
  gap: 2rem;
}

.project-card {
  background: #1a1a2e;
  border-radius: 12px;
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border: 1px solid rgba(102, 126, 234, 0.2);
}

.project-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(102, 126, 234, 0.3);
  border-color: #667eea;
}

.project-image {
  position: relative;
  height: 250px;
  background: linear-gradient(135deg, #667eea, #764ba2);
}

.project-overlay {
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 2rem;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.project-link {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: rgba(102, 126, 234, 0.3);
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: 0.3s;
}

.project-link:hover {
  background: #667eea;
  transform: scale(1.1);
}

.project-content {
  padding: 1.5rem;
}

.project-title {
  color: #fff;
  font-size: 1.4rem;
  margin-bottom: 0.8rem;
}

.project-description {
  color: #b0b0b0;
  font-size: 0.95rem;
  margin-bottom: 1.2rem;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tech-tag {
  background: rgba(102, 126, 234, 0.2);
  color: #667eea;
  padding: 0.3rem 0.8rem;
  border-radius: 4px;
  font-size: 0.8rem;
}

.img-fill {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
