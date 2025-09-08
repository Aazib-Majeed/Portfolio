<template>
  <section id="projects" class="projects">
    <h2>Projects</h2>

    <div class="carousel-container">
      <div class="carousel" :style="{ transform: `rotateY(${theta}deg)` }">
        <div
          v-for="(project, index) in projects"
          :key="index"
          class="memory-card"
          :class="{ flipped: flippedIndex === index, active: index === currentIndex }"
          :style="{ transform: `rotateY(${index * angle}deg) translateZ(${radius}px)` }"
          @click="flipCard(index)"
        >
          <div class="card-inner">
            <!-- Front side -->
            <div class="card-front">
              <ProjectCard
                :title="project.title"
                :description="project.description"
                :link="project.link"
                :tools="project.tools"
                :image="project.image"
                mode="front"
              />
            </div>

            <!-- Back side -->
            <div class="card-back">
              <ProjectCard
                :title="project.title"
                :description="project.description"
                :link="project.link"
                :tools="project.tools"
                :image="project.image"
                mode="back"
              />
            </div>
          </div>
        </div>
      </div>

      <!-- Controls -->
      <div class="carousel-controls">
        <button class="control-btn" @click="prevCard">
          <i class="fa-solid fa-chevron-left"></i>
        </button>
        <button class="control-btn" @click="nextCard">
          <i class="fa-solid fa-chevron-right"></i>
        </button>
      </div>
    </div>
  </section>
</template>

<script>
import ProjectCard from "./ProjectCard.vue";

const portfolioImg = "https://via.placeholder.com/400x250?text=Portfolio";
const networkingImg = "https://via.placeholder.com/400x250?text=Networking";

export default {
  name: "Projects",
  components: { ProjectCard },
  data() {
    return {
      theta: 0,
      radius: 400,
      angle: 0,
      flippedIndex: null,
      currentIndex: 0, // track which card is front
      projects: [
        {
          title: "Portfolio Website",
          description: `A fully responsive personal portfolio designed and developed from scratch to showcase my 
          projects, skills, and experience. Built with Vue.js and Vite for fast performance, and styled using 
          custom CSS with modern design principles.`,
          link: "https://github.com/yourusername/portfolio",
          tools: ["Vue.js", "Tailwind", "Vite"],
          image: portfolioImg,
        },
        {
          title: "Mini Database Engine",
          description: `A C++ project emulating a basic database engine with the following features:
          • SQL-like Command Interface
          • Table Operations (CREATE, INSERT, SELECT, UPDATE, DELETE)
          • Data Persistence with SAVE/LOAD
          • Auto-incrementing IDs and Error Handling`,
          link: "https://github.com/yourusername/database-engine",
          tools: ["C++"],
          image: networkingImg,
        },
      ],
    };
  },
  mounted() {
    this.angle = 360 / this.projects.length;
  },
  methods: {
    nextCard() {
      this.theta -= this.angle;
      this.currentIndex = (this.currentIndex + 1) % this.projects.length;
      this.flippedIndex = null; // reset flip when changing card
    },
    prevCard() {
      this.theta += this.angle;
      this.currentIndex =
        (this.currentIndex - 1 + this.projects.length) % this.projects.length;
      this.flippedIndex = null;
    },
    flipCard(index) {
      if (index === this.currentIndex) {
        this.flippedIndex = this.flippedIndex === index ? null : index;
      }
    },
  },
};
</script>

<style src="../style.css"></style>
