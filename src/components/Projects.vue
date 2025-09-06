<template>
  <section id="projects" class="projects">
    <h2>Projects</h2>
    <div class="project-list">
      <ProjectCard
        v-for="(project, index) in projects"
        :key="index"
        :title="project.title"
        :description="project.description"
        :link="project.link"
      />
    </div>
  </section>
</template>

<script>
import ProjectCard from "./ProjectCard.vue"

export default {
  name: "Projects",
  components: { ProjectCard },
  data() {
    return {
      projects: [
        {
          title: "Portfolio Website",
          description: "A personal portfolio built with Vue.js and Tailwind.",
          link: "#"
        },
        {
          title: "Networking Project",
          description: "A C++ and Python project showing networking concepts.",
          link: "#"
        },
        {
          title: "Embedded Systems Project",
          description: "An ARM-based embedded project with real-time control.",
          link: "#"
        },
        {
          title: "Music Player in C++",
          description: "A CLI based Music Player coded in C++ using Linked Lists and File Handling",
          link: "#"  
        }
      ]
    }
  }
}
</script>

