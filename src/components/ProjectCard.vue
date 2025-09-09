<template>
  <div class="project-card">
    <template v-if="mode === 'front'">
      <!-- Show iframe if embed exists, otherwise show image -->
      <div v-if="embed" class="embed-container">
        <iframe
          :src="embed"
          width="100%"
          height="400"
          frameborder="0"
          allowfullscreen
        ></iframe>
      </div>
      <img v-else :src="image" :alt="title" class="project-image" />

      <div class="project-info">
        <h3>{{ title }}</h3>
        <p class="tools"><strong>Tools:</strong> {{ tools.join(", ") }}</p>
      </div>
    </template>

    <template v-else>
      <div class="project-info">
        <h3>{{ title }}</h3>
        <p v-html="formatDescription(description)"></p>
        <p class="tools"><strong>Tools:</strong> {{ tools.join(", ") }}</p>
        <a :href="link" target="_blank" class="github-link">View on GitHub</a>
      </div>
    </template>
  </div>
</template>

<script>
export default {
  name: "ProjectCard",
  props: ["title", "description", "link", "tools", "image", "mode", "embed"],
  methods: {
    formatDescription(desc) {
      return desc
        .replace(/- /g, "• ")
        .replace(/\n/g, "<br>");
    },
  },
};
</script>

<style scoped>
.embed-container {
  width: 100%;
  height: 400px;
  overflow: hidden;
  border-radius: 8px;
  margin-bottom: 10px;
}

.project-image {
  width: 100%;
  height: auto;
  border-radius: 8px;
}
</style>
