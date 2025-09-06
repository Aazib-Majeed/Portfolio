<template>
  <section id="skills" class="skills">
    <h2>Skills</h2>
    <div class="skills-grid">
      <SkillCard
        v-for="(skill, index) in skills"
        :key="index"
        :title="skill.title"
        :image="skill.image"
      />
    </div>
  </section>
</template>

<script>
import SkillCard from "./SkillCard.vue"  // ✅ Import your SkillCard component
import htmlImg from "../assets/Skills/html.png"
import cssImg from "../assets/Skills/css.png"
import jsImg from "../assets/Skills/js.png"
import vueImg from "../assets/Skills/vue.png"


export default {
  name: "Skills",
  components: { SkillCard },   // ✅ Register it here
  data() {
    return {
      skills: [
        { title: "HTML", image: htmlImg },
        { title: "CSS", image: cssImg },
        { title: "JavaScript", image: jsImg },
        { title: "Vue.js", image: vueImg }
      ]
    }
  }
}
</script>

