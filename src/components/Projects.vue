<template>
  <section id="projects" class="projects">
    <h2>Projects</h2>
    <div class="carousel">
      <button class="nav left" @click="prevProject">&#10094;</button>
      
      <ProjectCard
        :title="projects[currentIndex].title"
        :description="projects[currentIndex].description"
        :link="projects[currentIndex].link"
        :tools="projects[currentIndex].tools"
        :image="projects[currentIndex].image"
      />
      
      <button class="nav right" @click="nextProject">&#10095;</button>
    </div>
  </section>
</template>

<script>
import ProjectCard from "./ProjectCard.vue"
const portfolioImg = "https://via.placeholder.com/400x250?text=Portfolio"
const networkingImg = "https://via.placeholder.com/400x250?text=Networking"
const embeddedImg = "https://via.placeholder.com/400x250?text=Embedded"
const musicImg = "https://via.placeholder.com/400x250?text=Music+Player"


export default {
  name: "Projects",
  components: { ProjectCard },
  data() {
    return {
      currentIndex: 0,
projects: [
  {
    title: "Portfolio Website",
    description: `A fully responsive personal portfolio designed and developed from scratch to showcase my 
    projects, skills, and experience. Built with Vue.js and Vite for fast performance, and styled using 
    custom CSS with modern design principles.This project demonstrates my ability to create clean, 
    user-friendly, and visually appealing web applications while applying concepts like component-based development,
    responsive design, and deployment pipelines.`,
    link: "https://github.com/yourusername/portfolio",
    tools: ["Vue.js", "Tailwind", "Vite"],
    image: portfolioImg
  },
  {
    title: "Mini Database Engine",
    description: `A C++ project emulating a basic database engine with the following features:
- SQL-like Command Interface: Familiar syntax for database operations
- Data Types: Support for INT and TEXT data types
- Table Operations: CREATE TABLE, INSERT, SELECT, UPDATE, DELETE
- Conditional Queries: WHERE clause support with comparison operators (=, !=, >, <, >=, <=)
- Data Persistence: SAVE and LOAD commands for database serialization
- Auto-incrementing IDs: Automatic row ID assignment
- Error Handling: Robust validation and error reporting
- User-friendly Interface: Formatted output and HELP command.`,
    link: "https://github.com/yourusername/database-engine",
    tools: ["C++"],
    image: networkingImg
  }
]

    }
  },
  methods: {
    nextProject() {
      this.currentIndex = (this.currentIndex + 1) % this.projects.length
    },
    prevProject() {
      this.currentIndex =
        (this.currentIndex - 1 + this.projects.length) % this.projects.length
    }
  }
}
</script>

<style src="../style.css"></style>

