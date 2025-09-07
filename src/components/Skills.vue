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
import SkillCard from "./SkillCard.vue"
import htmlImg from "../assets/Skills/html.png"
import cssImg from "../assets/Skills/css.png"
import jsImg from "../assets/Skills/js.png"
import vueImg from "../assets/Skills/vue.png"
import cppImg from "../assets/Skills/Cpp.png"
import pythonImg from "../assets/Skills/Python.png"
import JavaImg from "../assets/Skills/Java.png"
import E_Img from "../assets/Skills/Embedded_Systems.png"

export default {
  name: "Skills",
  components: { SkillCard },
  data() {
    return {
      skills: [
        { title: "HTML", image: htmlImg },
        { title: "CSS", image: cssImg },
        { title: "JavaScript", image: jsImg },
        { title: "Vue.js", image: vueImg },
        { title: "C++", image: cppImg },
        { title: "Python", image: pythonImg },
        { title: "Java", image:JavaImg},
        { title: "Embedded Systems", image:E_Img}
      ]
    }
  }
}
</script>
