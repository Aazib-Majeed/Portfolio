<template>
  <div class="project-card">
    <img :src="image" :alt="title" class="project-image" />
    <div class="project-info">
      <h3>{{ title }}</h3>
      <p v-html="formatDescription(description)"></p>

      <p class="tools">
        <strong>Tools:</strong> {{ tools.join(", ") }}
      </p>
      <a :href="link" target="_blank" class="github-link">View on GitHub</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProjectCard",
  props: ["title", "description", "link", "tools", "image"],
  methods: {
    formatDescription(desc) {
      return desc
        .replace(/- /g, "• ")   // turn "- " into bullets
        .replace(/\n/g, "<br>") // keep line breaks
    }
  }
}
</script>


<style src="../style.css"></style>
