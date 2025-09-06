<template>
  <div class="card">
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
    <a :href="link" target="_blank">View Project</a>
  </div>
</template>

<script>
export default {
  name: "ProjectCard",
  props: ["title", "description", "link"]
}
</script>
