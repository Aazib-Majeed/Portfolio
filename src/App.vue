<template>
  <div class="container">
    <Header />
    <About />
    <Skills />
    <Projects />
    <Contact />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import About from './components/About.vue'
import Skills from './components/Skills.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'

export default {
  name: "App",
  components: {
    Header,
    About,
    Skills,
    Projects,
    Contact,
    Footer
  },

  mounted() {
    const sections = document.querySelectorAll("section")
    let isScrolling = false

    window.addEventListener("wheel", (e) => {
      if (isScrolling) return
      isScrolling = true

      const current = Math.round(window.scrollY / window.innerHeight)

      let targetIndex = current
      if (e.deltaY > 0 && current < sections.length - 1) {
        targetIndex++ // scroll down
      } else if (e.deltaY < 0 && current > 0) {
        targetIndex-- // scroll up
      }

      window.scrollTo({
        top: sections[targetIndex].offsetTop,
        behavior: "smooth",
      })

      setTimeout(() => {
        isScrolling = false
      }, 800) // debounce time
    })
  }
}
</script>
