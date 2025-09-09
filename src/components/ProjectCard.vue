<template>
  <div class="project-card">
    <template v-if="mode === 'front'">
      <img :src="image" :alt="title" class="project-image" />
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
  props: ["title", "description", "link", "tools", "image", "mode"],
  methods: {
    formatDescription(desc) {
      return desc
        .replace(/- /g, "• ")
        .replace(/\n/g, "<br>");
    },
  },
};
</script>

<style src="../style.css"></style>
