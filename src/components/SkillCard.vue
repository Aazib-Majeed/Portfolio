<template>
  <div class="skill-card">
    <img :src="image" :alt="title" />
    <h3>{{ title }}</h3>
  </div>
</template>

<script>
export default {
  name: "SkillCard",
  props: ["title", "image"]
}
</script>
