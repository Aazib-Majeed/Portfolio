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
    const headerHeight = document.querySelector(".header").offsetHeight
    const navLinks = document.querySelectorAll(".nav-links a")
    let isScrolling = false

    // -------- Snap scroll on wheel --------
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
      }, 800)
    })

    // -------- IntersectionObserver for nav highlighting --------
    const observer = new IntersectionObserver((entries) => {
      let anyActive = false

      entries.forEach(entry => {
        if (entry.isIntersecting) {
          const id = entry.target.id
          const matched = [...navLinks].some(link => link.getAttribute('href') === `#${id}`)

          if (matched) {
            navLinks.forEach(link => {
              link.classList.toggle('active', link.getAttribute('href') === `#${id}`)
            })
            anyActive = true
          }
        }
      })

      // If no section with nav link is active → clear highlights
      if (!anyActive) {
        navLinks.forEach(link => link.classList.remove('active'))
      }
    }, {
      root: null,
      rootMargin: `-${headerHeight}px 0px 0px 0px`,
      threshold: 0.6
    })

    sections.forEach(s => observer.observe(s))
  }
}
</script>



