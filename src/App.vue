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
    const sections = document.querySelectorAll("section");
    const navLinks = document.querySelectorAll(".header nav a");
    let isScrolling = false;

    // Smooth section snap on scroll
    window.addEventListener("wheel", (e) => {
      if (isScrolling) return;
      isScrolling = true;

      const current = Math.round(window.scrollY / window.innerHeight);
      let targetIndex = current;

      if (e.deltaY > 0 && current < sections.length - 1) {
        targetIndex++;
      } else if (e.deltaY < 0 && current > 0) {
        targetIndex--;
      }

      window.scrollTo({
        top: sections[targetIndex].offsetTop,
        behavior: "smooth",
      });

      setTimeout(() => {
        isScrolling = false;
      }, 800);
    });

    // Active nav link on scroll
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            navLinks.forEach((link) => {
              link.classList.remove("active");
              if (link.getAttribute("href") === `#${entry.target.id}`) {
                link.classList.add("active");
              }
            });
          }
        });
      },
      { threshold: 0.6 }
    );

    sections.forEach((section) => observer.observe(section));
  }
};
</script>
